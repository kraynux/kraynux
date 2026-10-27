# Architektura projektu — Clean Architecture

**Języki:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Ten dokument wyjaśnia, jak zorganizowany jest projekt, dlaczego wybrano taką organizację i co zawiera każdy folder. Jest przeznaczony zarówno dla odwiedzających, którzy chcą zrozumieć działanie aplikacji, jak i dla programistów, którzy chcą ją współtworzyć lub utrzymywać.

Aplikacja stosuje **Clean Architecture**: rdzeń oprogramowania jest odizolowany od szczegółów technicznych, interfejsów użytkownika i zależności zewnętrznych. Takie rozdzielenie ułatwia czytanie, testowanie, utrzymanie i rozwijanie projektu.

---

## 1. Zasada ogólna

Aplikacja jest podzielona na warstwy, z których każda ma ściśle określoną rolę.

Główna idea jest prosta:

```text
Interfejs zleca akcję.
Aplikacja orkiestruje tę akcję.
Domena stosuje reguły biznesowe.
Porty określają, czego potrzebuje aplikacja.
Infrastruktura dostarcza konkretne implementacje.
```

Dzięki temu najważniejsza logika projektu nie zależy bezpośrednio:

- od terminala;
- od interfejsu graficznego;
- od bazy danych;
- od sieci;
- od systemu plików;
- od zewnętrznej biblioteki;
- od narzędzia systemowego.

Ta niezależność pozwala wymienić część oprogramowania bez przepisywania całej reszty.

---

## 2. Widok ogólny

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, cykl życia i wstrzykiwanie zależności
        ├── core/             Przekrojowe możliwości, enumy i wyjątki
        ├── domain/           Czysta logika biznesowa
        ├── application/      Przypadki użycia: commands i queries
        ├── infrastructure/   Backendy, przechowywanie, eksporty, logi, sondy systemowe…
        ├── ports/            Kontrakty Protocol / ABC
        ├── interfaces/       CLI i TUI
        ├── plugins/          Wbudowane rozszerzenia
        └── shared/           Parsowanie, sieć, formatowanie i narzędzia przekrojowe
```

---

## 3. Schemat zależności

Zależności muszą zawsze iść w tym samym kierunku:

```text
interfaces
    ↓
application
    ↓
domain
    ↑
ports
    ↑
infrastructure
```

W praktyce:

- `interfaces/` może wywoływać `application/`.
- `application/` może wywoływać `domain/` i używać kontraktów zdefiniowanych w `ports/`.
- `domain/` nie zależy ani od `application/`, ani od `infrastructure/`, ani od `interfaces/`.
- `infrastructure/` implementuje kontrakty zdefiniowane w `ports/`.
- `app/` składa warstwy i dostarcza potrzebne zależności.

Zasada podstawowa:

> Domena nigdy nie zna infrastruktury.  
> Infrastruktura zna porty, ale domena nie zna infrastruktury.

---

## 4. Folder `app/`

### Rola

Folder `app/` jest **punktem montażu** aplikacji.

Zawiera:

- uruchamianie aplikacji;
- cykl życia;
- kontener wstrzykiwania zależności;
- tworzenie obiektów potrzebnych do działania;
- wybór konkretnych implementacji;
- inicjalizację konfiguracji;
- połączenia między warstwami.

### Przykładowe odpowiedzialności

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Plik | Rola |
|---|---|
| `bootstrap.py` | Uruchamia aplikację i wybiera interfejs do załadowania |
| `container.py` | Tworzy i łączy zależności |
| `lifecycle.py` | Zarządza uruchamianiem, zatrzymywaniem i sprzątaniem |

### Zasada

`app/` nie zawiera logiki biznesowej.

Nie decyduje:

- czym jest reguła biznesowa;
- jak należy obliczyć daną wartość;
- jak należy przeanalizować żądanie;
- jak należy wyeksportować plik.

Jedynie składa istniejące komponenty.

---

## 5. Folder `core/`

### Rola

Folder `core/` zawiera **przekrojowe słownictwo** projektu.

Grupuje elementy współdzielone przez kilka warstw, które same w sobie nie są regułami biznesowymi.

Może zawierać:

- możliwości (capabilities);
- wyliczenia;
- stałe;
- wyjątki przekrojowe;
- wspólne typy;
- informacje o platformie;
- definicje poziomów lub stanów.

### Przykład

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Plik | Rola |
|---|---|
| `capabilities.py` | Opisuje możliwości dostępne lub możliwe do włączenia |
| `constants.py` | Zawiera stałe projektu |
| `enums.py` | Definiuje możliwe stany, typy lub poziomy |
| `exceptions.py` | Definiuje błędy przekrojowe |

### Zasada

`core/` musi pozostać lekki i stabilny.

Nie może zawierać:

- złożonej logiki biznesowej;
- wywołań sieciowych;
- dostępu do dysku;
- kodu interfejsu użytkownika;
- bezpośredniej zależności od bibliotek zewnętrznych.

---

## 6. Folder `domain/`

### Rola

Folder `domain/` to **serce projektu**.

Zawiera czystą logikę biznesową: reguły, pojęcia i obliczenia, które naprawdę określają, co robi aplikacja.

Może zawierać:

- encje;
- value objects;
- polityki;
- reguły biznesowe;
- serwisy domenowe;
- obliczenia;
- walidacje biznesowe;
- biznesowe modele danych.

### Przykład

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Element | Rola |
|---|---|
| Encja | Obiekt biznesowy mający tożsamość |
| Value object | Niezmienna i zwalidowana wartość |
| Polityka | Reguła biznesowa wielokrotnego użytku |
| Serwis domenowy | Logika biznesowa, która nie należy do pojedynczej encji |

### Ścisłe zasady

Folder `domain/`:

- nie korzysta z dysku;
- nie wykonuje wywołań sieciowych;
- nie uruchamia poleceń systemowych;
- nie łączy się z bazą danych;
- nie importuje interfejsu użytkownika;
- nie importuje infrastruktury;
- nie zależy od zewnętrznej biblioteki technicznej, jeśli można tego uniknąć.

Domenę musi dać się przetestować bez serwera, bez plików, bez sieci i bez interfejsu.

---

## 7. Folder `application/`

### Rola

Folder `application/` orkiestruje przypadki użycia.

Odpowiada na pytanie:

> „Co się dzieje, gdy użytkownik zleca tę akcję?”

Zawiera:

- commands;
- queries;
- przypadki użycia;
- orkiestratory;
- handlery akcji;
- koordynację między domeną a portami.

### Rozróżnienie commands / queries

| Typ | Cel | Zmienia dane |
|---|---|---|
| Command | Wykonać akcję | Tak |
| Query | Odczytać lub obliczyć informację | Nie |

Przykłady:

| Command | Query |
|---|---|
| Zastosować konfigurację | Odczytać bieżącą konfigurację |
| Uruchomić analizę | Pobrać wynik analizy |
| Wyeksportować raport | Wyświetlić listę dostępnych elementów |
| Wyczyścić dane | Przejrzeć historię |

### Przykład

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Zasada

`application/` nie zawiera:

- wyświetlania w terminalu;
- interfejsu Textual;
- poleceń Rich;
- bezpośredniego dostępu do bazy danych;
- bezpośrednich wywołań narzędzi zewnętrznych.

Koordynuje, ale nie implementuje szczegółów technicznych.

---

## 8. Folder `ports/`

### Rola

Folder `ports/` definiuje **kontrakty** oczekiwane przez aplikację.

Port opisuje, **czego potrzebuje aplikacja**, nie narzucając sposobu implementacji.

Zazwyczaj zawiera:

- definicje `Protocol`;
- klasy abstrakcyjne `ABC`;
- interfejsy repozytoriów;
- interfejsy eksportu;
- interfejsy sond;
- interfejsy usług zewnętrznych;
- interfejsy przechowywania.

### Przykład

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Rola |
|---|---|
| `Repository` | Odczyt lub zapis danych |
| `Exporter` | Wytworzenie wyniku w danym formacie |
| `Probe` | Zebranie informacji systemowej lub sieciowej |
| `Storage` | Zarządzanie backendem trwałego przechowywania |

### Przykład koncepcyjny

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Ten kontrakt mówi:

> „Aplikacja potrzebuje obiektu zdolnego do wyeksportowania raportu.”

Nie mówi:

- czy eksport będzie w Markdown;
- czy eksport będzie w JSON;
- czy plik zostanie zapisany lokalnie;
- czy eksport zostanie wysłany przez sieć.

Te wybory należą do `infrastructure/`.

### Zasada

Porty to kontrakty, a nie implementacje.

Nie mogą zawierać:

- złożonej logiki biznesowej;
- dostępu do dysku;
- wywołań sieciowych;
- konkretnych implementacji;
- bezpośredniej zależności od bibliotek zewnętrznych.

---

## 9. Folder `infrastructure/`

### Rola

Folder `infrastructure/` zawiera **konkretne implementacje** portów.

To warstwa, która komunikuje się ze światem zewnętrznym.

Może zawierać:

- dostęp do plików;
- dostęp do bazy danych;
- eksporty do Markdown, JSON, CSV lub innych formatów;
- logowanie;
- wywołania sieciowe;
- sondy systemowe;
- kontrolowane uruchamianie narzędzi zewnętrznych;
- adaptery do bibliotek zewnętrznych;
- implementacje repozytoriów;
- implementacje przechowywania.

### Przykład

```text
infrastructure/
├── storage/
│   ├── sqlite_repository.py
│   └── json_file_repository.py
├── export/
│   ├── markdown_exporter.py
│   └── json_exporter.py
├── system/
│   ├── process_probe.py
│   └── filesystem_probe.py
└── logging/
    └── structured_logger.py
```

| Element | Rola |
|---|---|
| `sqlite_repository.py` | Implementuje repozytorium z SQLite |
| `json_file_repository.py` | Implementuje repozytorium z plikami JSON |
| `markdown_exporter.py` | Eksportuje raport do Markdown |
| `json_exporter.py` | Eksportuje raport do JSON |
| `process_probe.py` | Zbiera informacje o procesach |
| `filesystem_probe.py` | Zbiera informacje o systemie plików |
| `structured_logger.py` | Generuje ustrukturyzowane logi |

### Zasada

`infrastructure/` to jedyna warstwa uprawniona do bezpośredniego dostępu do:

- systemu plików;
- sieci;
- SQLite;
- bibliotek zewnętrznych;
- narzędzi systemowych;
- podprocesów, gdy są potrzebne i kontrolowane.

Ta centralizacja ułatwia:

- testy;
- audyt bezpieczeństwa;
- wymianę backendu;
- ograniczanie efektów ubocznych.

---

## 10. Folder `interfaces/`

### Rola

Folder `interfaces/` zawiera punkty wejścia widoczne dla użytkownika.

Wyraźnie rozdziela:

- CLI;
- TUI;
- ewentualne przyszłe interfejsy webowe lub API.

### Struktura

```text
interfaces/
├── cli/
│   ├── main.py
│   ├── commands/
│   └── rendering/
└── tui/
    ├── app.py
    ├── screens/
    └── widgets/
```

| Interfejs | Technologia | Rola |
|---|---|---|
| `cli/` | Rich | Interfejs wiersza poleceń |
| `tui/` | Textual | Interaktywny interfejs w terminalu |

### CLI

CLI to interfejs wiersza poleceń.

Pozwala:

- uruchomić aplikację;
- wykonać określoną akcję;
- wyświetlić wynik;
- zautomatyzować zadanie;
- włączyć narzędzie do skryptu;
- korzystać z aplikacji zdalnie przez SSH.

### TUI

TUI to interaktywny interfejs w terminalu.

Pozwala:

- poruszać się między funkcjami;
- wyświetlać informacje;
- wykonywać akcje;
- przeglądać wyniki;
- korzystać z aplikacji bez zapamiętywania wszystkich poleceń.

### Zasada

Interfejsy nie zawierają logiki biznesowej.

One:

- przyjmują intencję użytkownika;
- wywołują przypadek użycia w `application/`;
- wyświetlają wynik;
- tłumaczą błędy na zrozumiałe komunikaty.

Nie mogą:

- bezpośrednio wywoływać infrastruktury;
- uruchamiać podprocesów;
- bezpośrednio korzystać z plików;
- zawierać reguł biznesowych;
- powielać logiki z `application/`.

---

## 11. Folder `plugins/`

### Rola

Folder `plugins/` jest zarezerwowany dla **wbudowanych rozszerzeń**.

Pozwala dodawać funkcje bez obciążania rdzenia projektu.

Plugin może na przykład:

- dodać format eksportu;
- dodać sondę;
- dodać polecenie;
- dodać ekran TUI;
- dodać integrację zewnętrzną;
- dodać opcjonalną możliwość.

### Zasada

Plugin musi przestrzegać tych samych reguł co reszta projektu:

- nie omija portów;
- nie modyfikuje bezpośrednio domeny;
- udostępnia swoje funkcje przez jasne kontrakty;
- można go wyłączyć bez psucia aplikacji.

### Możliwa struktura

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Zasada

Plugin to rozszerzenie, a nie tylne drzwi.

Musi respektować ogólną architekturę i nie może tworzyć cyklicznych zależności z rdzeniem projektu.

---

## 12. Folder `shared/`

### Rola

Folder `shared/` zawiera narzędzia przekrojowe, które nie należą ani do domeny, ani do aplikacji, ani do infrastruktury.

Grupuje generyczne funkcje wielokrotnego użytku.

Może zawierać:

- parsowanie;
- narzędzia sieciowe;
- formatowanie;
- przetwarzanie tekstu;
- pomocniki do dat;
- pomocniki do ścieżek;
- generyczne narzędzia walidacji;
- pomocniki serializacji.

### Przykład

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Folder | Rola |
|---|---|
| `parsing/` | Analiza tekstu, JSON, YAML lub innych formatów |
| `network/` | Generyczne narzędzia sieciowe |
| `formatting/` | Formatowanie wartości, dat, rozmiarów lub tabel |
| `utils/` | Przekrojowe funkcje pomocnicze |

### Zasada

`shared/` nie może stać się folderem na wszystko.

Narzędzie trafia do `shared/` tylko wtedy, gdy jest:

- wielokrotnego użytku;
- generyczne;
- niezależne od konkretnego przypadku użycia;
- przydatne dla kilku warstw.

---

## 13. Podsumowanie odpowiedzialności

| Folder | Główna rola | Może zależeć od | Nie może zależeć od |
|---|---|---|---|
| `app/` | Złożyć i uruchomić aplikację | Wszystkich warstw | — |
| `core/` | Słownictwo, stałe, enumy i wyjątki | `shared/` w razie potrzeby | `infrastructure/`, `interfaces/` |
| `domain/` | Czysta logika biznesowa | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Orkiestrować przypadki użycia | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Definiować kontrakty | `domain/` w razie potrzeby | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Implementować porty i komunikować się ze światem zewnętrznym | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Komunikować się z użytkownikiem | `application/`, `core/` | `infrastructure/` bezpośrednio |
| `plugins/` | Dodawać rozszerzenia | Zależnie od typu rozszerzenia | Omijania architektury |
| `shared/` | Narzędzia przekrojowe | Żadnej warstwy biznesowej | Specyficznej logiki biznesowej |

---

## 14. Przykład przepływu akcji

Weźmy użytkownika, który zleca eksport raportu do Markdown.

```text
1. Użytkownik uruchamia polecenie CLI.

2. interfaces/cli/
   Odbiera polecenie i jego opcje.

3. interfaces/cli/
   Wywołuje odpowiedni przypadek użycia w application/.

4. application/
   Waliduje intencję i przygotowuje akcję.

5. application/
   Używa domeny do zbudowania lub zwalidowania raportu.

6. application/
   Zleca eksport przez port ReportExporter.

7. infrastructure/
   Dostarcza implementację MarkdownExporter.

8. infrastructure/
   Zapisuje plik Markdown na dysku.

9. interfaces/cli/
   Wyświetla wynik użytkownikowi.
```

Uproszczony schemat:

```text
CLI
 ↓
Application
 ↓
Domain
 ↓
Port Exporter
 ↓
Infrastructure Markdown
 ↓
Plik Markdown
```

---

## 15. Dlaczego taka architektura?

### Czytelność

Każdy folder ma jedną rolę, co ułatwia znalezienie miejsca, w którym trzeba dodać lub poprawić funkcję.

### Testowalność

Domenę można testować bez interfejsu, bez bazy danych i bez dostępu do sieci.

### Łatwość utrzymania

Zmiana interfejsu, sposobu przechowywania lub narzędzia zewnętrznego nie może wymagać przepisywania logiki biznesowej.

### Bezpieczeństwo

Wrażliwe operacje — pliki, sieć, podprocesy, bazy danych — są skupione w `infrastructure/`. Ułatwia to audyt i kontrolę.

### Rozwijalność

Można dodać:

- nowy interfejs;
- nowy format eksportu;
- nowy backend przechowywania;
- nowy plugin;
- nową sondę systemową;

bez modyfikowania rdzenia biznesowego.

### Przenośność

Aplikacja może ewoluować w stronę innych środowisk, systemów lub sposobów interakcji, nie będąc przywiązana do konkretnej technologii.

---

## 16. Zasady do zapamiętania

- Domena jest czysta.
- Aplikacja orkiestruje.
- Porty deklarują potrzeby.
- Infrastruktura implementuje.
- Interfejsy wyświetlają i zbierają.
- `app/` składa całość.
- `core/` i `shared/` dostarczają przekrojowe słownictwo i narzędzia.
- Pluginy rozszerzają bez omijania architektury.

W jednym zdaniu:

> **Aplikacja oddziela to, co robi, od tego, jak to robi, i od tego, jak użytkownik z niej korzysta.**
