# Procedura rozwoju — [PROJECT_NAME]

**Języki:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Pole | Wartość |
|---|---|
| Projekt | [PROJECT_NAME] |
| Wersja docelowa | [TARGET_VERSION] |
| Odpowiedzialny | [IMIĘ_NAZWISKO] |
| Data utworzenia | [RRRR-MM-DD] |
| Ostatnia aktualizacja | [RRRR-MM-DD] |
| Status ogólny | Szkic / W toku / Zatwierdzony / W produkcji |
| Środowisko docelowe | [Linux / Debian / Serwer / Stacja robocza] |
| Główny język | [Python / Bash / Lua / Inny] |
| Repozytorium | [URL_LUB_ŚCIEŻKA] |

## Zasady przekrojowe

- [ ] Żaden kod nie jest pisany przed zatwierdzeniem planu końcowego.
- [ ] Każda ważna decyzja jest dokumentowana.
- [ ] Każda anomalia jest rejestrowana.
- [ ] Każda poprawka jest testowana.
- [ ] Każda zmiana zachowania jest dokumentowana.
- [ ] Kopie zapasowe są wykonywane przed każdą interwencją w produkcji.
- [ ] AI analizuje i proponuje; człowiek decyduje, zatwierdza i wdraża.
- [ ] Kod pozostaje zgodny z dokumentacją końcową.

## Ogólne śledzenie faz

| Faza | Wykonawca | Główny rezultat | Status | Data zatwierdzenia |
|---:|---|---|---|---|
| 1 | Człowiek | Potrzeby i koncepcja | [ ] | [RRRR-MM-DD] |
| 2 | Człowiek | Szkic architektury i plan wstępny | [ ] | [RRRR-MM-DD] |
| 3 | AI | Analiza, efekty uboczne, plan końcowy | [ ] | [RRRR-MM-DD] |
| 4 | Człowiek | Zakodowany rdzeń projektu | [ ] | [RRRR-MM-DD] |
| 5 | AI | Audyt kodu, poprawki i testy | [ ] | [RRRR-MM-DD] |
| 6 | Człowiek | Rzeczywiste testy w produkcji | [ ] | [RRRR-MM-DD] |
| 7 | AI | Plan poprawek i kodowanie końcowe | [ ] | [RRRR-MM-DD] |
| 8 | Człowiek | Testy końcowe | [ ] | [RRRR-MM-DD] |
| 9 | Człowiek | Szkic dokumentacji | [ ] | [RRRR-MM-DD] |
| 10 | AI | Dokumentacja końcowa | [ ] | [RRRR-MM-DD] |
| 11 | Człowiek | Wdrożenie produkcyjne | [ ] | [RRRR-MM-DD] |

---

# Faza 1 — Refleksja, potrzeby, użytkowanie i koncepcja

**Wykonawca: Człowiek**  
**Cel:** określić problem, użytkowników, rzeczywiste użytkowanie, ograniczenia i granice projektu.

## 1. Problem wyjściowy

- Zidentyfikowany problem: [DO UZUPEŁNIENIA]
- Obecna sytuacja: [DO UZUPEŁNIENIA]
- Konsekwencja problemu: [DO UZUPEŁNIENIA]
- Cel projektu: [DO UZUPEŁNIENIA]

## 2. Użytkownicy docelowi

| Użytkownik | Główna potrzeba | Poziom techniczny | Planowane użycie |
|---|---|---|---|
| [Użytkownik 1] | [DO UZUPEŁNIENIA] | [Początkujący / Techniczny / Ekspert] | [DO UZUPEŁNIENIA] |
| [Użytkownik 2] | [DO UZUPEŁNIENIA] | [Początkujący / Techniczny / Ekspert] | [DO UZUPEŁNIENIA] |

## 3. Scenariusze użycia

### Scenariusz nominalny

- Kontekst: [DO UZUPEŁNIENIA]
- Działanie użytkownika: [DO UZUPEŁNIENIA]
- Oczekiwany wynik: [DO UZUPEŁNIENIA]

### Scenariusz graniczny

- Kontekst: [DO UZUPEŁNIENIA]
- Działanie użytkownika: [DO UZUPEŁNIENIA]
- Oczekiwany wynik: [DO UZUPEŁNIENIA]

### Scenariusz błędu

- Kontekst: [DO UZUPEŁNIENIA]
- Działanie użytkownika: [DO UZUPEŁNIENIA]
- Oczekiwany wynik: [DO UZUPEŁNIENIA]

### Scenariusz zabroniony lub niebezpieczny

- Kontekst: [DO UZUPEŁNIENIA]
- Oczekiwane zachowanie: [Odmowa / Ostrzeżenie / Blokada / Zapis w logach]
- Uzasadnienie: [DO UZUPEŁNIENIA]

## 4. Funkcje

### Obowiązkowe

- [ ] [Funkcja 1]
- [ ] [Funkcja 2]
- [ ] [Funkcja 3]

### Przydatne, ale możliwe do odłożenia

- [ ] [Funkcja 1]
- [ ] [Funkcja 2]

### Opcjonalne

- [ ] [Funkcja 1]

### Wykluczone

- [ ] [Wykluczona funkcja]
- Uzasadnienie: [DO UZUPEŁNIENIA]

## 5. Ograniczenia

| Obszar | Ograniczenie | Priorytet |
|---|---|---|
| System | [Linux / Debian / Wersja] | [Wysoki / Średni / Niski] |
| Język | [Python / Bash / Lua] | [Wysoki / Średni / Niski] |
| Zależności | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Wydajność | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Bezpieczeństwo | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Kompatybilność | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Utrzymanie | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Wdrożenie | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |

## 6. Zidentyfikowane ryzyka

| Ryzyko | Wpływ | Prawdopodobieństwo | Środek zapobiegawczy |
|---|---|---|---|
| [Ryzyko 1] | [Niski / Średni / Wysoki] | [Niskie / Średnie / Wysokie] | [DO UZUPEŁNIENIA] |
| [Ryzyko 2] | [Niski / Średni / Wysoki] | [Niskie / Średnie / Wysokie] | [DO UZUPEŁNIENIA] |

## 7. Podjęte decyzje

| ID | Decyzja | Uzasadnienie | Data |
|---:|---|---|---|
| D-001 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [RRRR-MM-DD] |
| D-002 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [RRRR-MM-DD] |

## 8. Otwarte pytania

- [ ] [Pytanie 1]
- [ ] [Pytanie 2]

## Zatwierdzenie fazy 1

- [ ] Problem jest jasno sformułowany.
- [ ] Użytkownicy są zidentyfikowani.
- [ ] Główne scenariusze użycia są opisane.
- [ ] Funkcje obowiązkowe są wymienione.
- [ ] Granice projektu są jasno określone.
- [ ] Ograniczenia techniczne są znane.
- [ ] Główne ryzyka są zidentyfikowane.

**Status:** [ ] Szkic / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 2 — Szkic, główne komponenty i plan rozwoju

**Wykonawca: Człowiek**  
**Cel:** przekształcić potrzeby w logiczną architekturę i wykonalny plan rozwoju.

## 1. Główne komponenty

| Komponent | Odpowiedzialność | Nie może | Priorytet |
|---|---|---|---|
| Interfejs / CLI | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Rdzeń biznesowy | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Konfiguracja | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Modele danych | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Usługi | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Przechowywanie | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Eksport | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Logi | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Bezpieczeństwo | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| Testy | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |

## 2. Główny przepływ

```text
[Dane wejściowe użytkownika]
    → [Interfejs]
    → [Walidacja]
    → [Rdzeń biznesowy]
    → [Usługi / Moduły]
    → [Wynik]
    → [Wyjście / Przechowywanie / Logi]
```

## 3. Planowane moduły

| Moduł | Rola | Zależności | Priorytet |
|---|---|---|---|
| [module_1] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| [module_2] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |
| [module_3] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Wysoki / Średni / Niski] |

## 4. Wstępna struktura katalogów

```text
[PROJECT_NAME]/
├── src/
│   └── [project_name]/
│       ├── __init__.py
│       ├── config.py
│       ├── exceptions.py
│       ├── logging.py
│       ├── models/
│       ├── core/
│       ├── services/
│       └── cli/
├── tests/
│   ├── unit/
│   └── integration/
├── docs/
├── scripts/
└── CHANGELOG.md
```

## 5. Planowane zależności

| Zależność | Zastosowanie | Minimalna wersja | Uzasadnienie |
|---|---|---|---|
| [Zależność 1] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |
| [Zależność 2] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |

## 6. Podział prac rozwojowych

| Faza | Zawartość | Priorytet | Szacunek |
|---:|---|---|---|
| 1 | Podstawy: struktura, konfiguracja, błędy, logi | [Wysoki / Średni] | [Czas] |
| 2 | Modele i kontrakty | [Wysoki / Średni] | [Czas] |
| 3 | Rdzeń biznesowy | [Wysoki / Średni] | [Czas] |
| 4 | Interfejs / CLI | [Wysoki / Średni] | [Czas] |
| 5 | Przechowywanie / eksport | [Wysoki / Średni] | [Czas] |
| 6 | Testy | [Wysoki / Średni] | [Czas] |
| 7 | Dokumentacja i pakowanie | [Wysoki / Średni] | [Czas] |

## Zatwierdzenie fazy 2

- [ ] Główne komponenty są zidentyfikowane.
- [ ] Każdy moduł ma jasną odpowiedzialność.
- [ ] Główne przepływy są opisane.
- [ ] Wstępna struktura katalogów jest określona.
- [ ] Główne zależności są zidentyfikowane.
- [ ] Kolejność prac jest określona.
- [ ] Żadne prace rozwojowe nie zostały rozpoczęte.

**Status:** [ ] Szkic / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 3 — Analiza AI, efekty uboczne i plan końcowy

**Wykonawca: AI**  
**Cel:** przeanalizować dokumenty przygotowane przez człowieka, zidentyfikować ryzyka i opracować wykonalny plan końcowy.

## 1. Przeanalizowane dokumenty

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Inny dokument]

## 2. Prompt analizy AI

```text
Przeanalizuj ten projekt bez pisania kodu.

1. Wykryj niespójności.
2. Wykryj brakujące funkcje.
3. Wykryj źle umiejscowione odpowiedzialności.
4. Zidentyfikuj możliwe efekty uboczne.
5. Zidentyfikuj przypadki awarii.
6. Zidentyfikuj ryzyka bezpieczeństwa.
7. Zidentyfikuj problemy z kompatybilnością.
8. Zaproponuj solidniejszą strukturę projektu.
9. Zaproponuj końcowy plan rozwoju.
10. Wskaż punkty, które muszą pozostać w gestii człowieka.
```

## 3. Wykryte niespójności

| ID | Opis | Wpływ | Propozycja | Decyzja człowieka |
|---:|---|---|---|---|
| A-001 | [DO UZUPEŁNIENIA] | [Niski / Średni / Wysoki] | [DO UZUPEŁNIENIA] | [Przyjęta / Odrzucona / Odłożona] |
| A-002 | [DO UZUPEŁNIENIA] | [Niski / Średni / Wysoki] | [DO UZUPEŁNIENIA] | [Przyjęta / Odrzucona / Odłożona] |

## 4. Zidentyfikowane efekty uboczne

| ID | Efekt uboczny | Wyzwalacz | Wpływ | Zapobieganie | Status |
|---:|---|---|---|---|---|
| SE-001 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Niski / Średni / Wysoki] | [DO UZUPEŁNIENIA] | [Otwarty / Obsłużony / Zaakceptowany] |
| SE-002 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Niski / Średni / Wysoki] | [DO UZUPEŁNIENIA] | [Otwarty / Obsłużony / Zaakceptowany] |

## 5. Przypadki awarii do przewidzenia

| Przypadek | Oczekiwane zachowanie | Oczekiwany komunikat / log | Powiązany test |
|---|---|---|---|
| Brak pliku | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |
| Odmowa dostępu | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |
| Sieć niedostępna | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |
| Nieprawidłowe dane wejściowe | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |
| Przerwanie przez użytkownika | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |
| Uszkodzone dane | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] |

## 6. Ryzyka bezpieczeństwa

| Ryzyko | Scenariusz | Środek | Priorytet |
|---|---|---|---|
| [Ryzyko 1] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [P0 / P1 / P2] |
| [Ryzyko 2] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [P0 / P1 / P2] |

## 7. Końcowy plan rozwoju

| Faza | Cel | Rezultaty | Kryteria ukończenia | Zależności |
|---:|---|---|---|---|
| 1 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Brak] |
| 2 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Faza 1] |
| 3 | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Faza 2] |

## Zatwierdzenie fazy 3

- [ ] Niespójności są obsłużone lub udokumentowane.
- [ ] Efekty uboczne są zidentyfikowane.
- [ ] Przypadki awarii są przewidziane.
- [ ] Ryzyka bezpieczeństwa są obsłużone.
- [ ] Plan końcowy jest zatwierdzony przez człowieka.
- [ ] Ostateczne decyzje są zapisane.

**Status:** [ ] Szkic / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 4 — Kodowanie rdzenia projektu

**Wykonawca: Człowiek**  
**Cel:** opracować rdzeń funkcjonalny bez dodawania funkcji spoza zakresu.

## 1. Zakres kodowania

- [ ] Struktura projektu
- [ ] Środowisko wirtualne
- [ ] Zależności
- [ ] Konfiguracja
- [ ] Modele danych
- [ ] Wyjątki
- [ ] Logowanie
- [ ] Usługi biznesowe
- [ ] Rdzeń biznesowy
- [ ] Testy jednostkowe
- [ ] CLI / interfejs
- [ ] Integracja

## 2. Kolejność implementacji

| Kolejność | Element | Plik / moduł | Status | Commit |
|---:|---|---|---|---|
| 1 | [Element] | [ścieżka] | [ ] | [hash] |
| 2 | [Element] | [ścieżka] | [ ] | [hash] |
| 3 | [Element] | [ścieżka] | [ ] | [hash] |

## 3. Zasady commitów

- Jeden commit = jedna intencja.
- Nie mieszać funkcji, poprawki i refaktoryzacji.
- Zalecany komunikat:

```text
[type]: [krótki opis]

[type] = feat, fix, refactor, test, docs, chore
```

Przykład:

```text
feat: dodaj wczytywanie i walidację konfiguracji
```

## 4. Testy początkowe

| Test | Cel | Polecenie | Oczekiwany wynik | Status |
|---|---|---|---|---|
| [Test 1] | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [ ] |
| [Test 2] | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [ ] |

## Zatwierdzenie fazy 4

- [ ] Rdzeń biznesowy działa.
- [ ] Główne dane wejściowe są walidowane.
- [ ] Główne błędy są obsługiwane.
- [ ] Testy jednostkowe przechodzą.
- [ ] Projekt uruchamia się w trybie podstawowym.
- [ ] Nie dodano żadnej funkcji spoza zakresu.

**Status:** [ ] W toku / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 5 — Analiza kodu, poprawki i testy przez AI

**Wykonawca: AI**  
**Cel:** wykryć defekty, efekty uboczne i ryzyka przed rzeczywistymi testami.

## 1. Prompt audytu AI

```text
Przeanalizuj kod bez przepisywania go w całości.

1. Sprawdź zgodność z planem rozwoju.
2. Wykryj prawdopodobne błędy.
3. Wykryj efekty uboczne.
4. Wykryj wycieki zasobów.
5. Wykryj nieobsłużone błędy.
6. Wykryj niezwalidowane dane wejściowe.
7. Wykryj problemy bezpieczeństwa.
8. Wykryj problemy z wydajnością.
9. Wykryj martwy kod.
10. Wykryj źle umiejscowione odpowiedzialności.
11. Zaproponuj punktowe poprawki.
12. Zaproponuj brakujące testy.
```

## 2. Wyniki audytu

| ID | Plik / funkcja | Ustalenie | Waga | Proponowana poprawka | Status |
|---:|---|---|---|---|---|
| C-001 | [ścieżka] | [DO UZUPEŁNIENIA] | [Krytyczna / Poważna / Drobna] | [DO UZUPEŁNIENIA] | [Otwarty / Poprawiony / Zatwierdzony] |
| C-002 | [ścieżka] | [DO UZUPEŁNIENIA] | [Krytyczna / Poważna / Drobna] | [DO UZUPEŁNIENIA] | [Otwarty / Poprawiony / Zatwierdzony] |

## 3. Dodane testy

| Test | Cel | Plik testowy | Status |
|---|---|---|---|
| [Test 1] | [DO UZUPEŁNIENIA] | [ścieżka] | [ ] |
| [Test 2] | [DO UZUPEŁNIENIA] | [ścieżka] | [ ] |

## Zatwierdzenie fazy 5

- [ ] Błędy krytyczne są poprawione.
- [ ] Efekty uboczne są obsłużone lub udokumentowane.
- [ ] Testy jednostkowe przechodzą.
- [ ] Testy integracyjne przechodzą.
- [ ] Kod jest zgodny z planem końcowym.
- [ ] Poprawki zostały wprowadzone stopniowo.

**Status:** [ ] W toku / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 6 — Badanie w rzeczywistych warunkach i testy w produkcji

**Wykonawca: Człowiek**  
**Cel:** zweryfikować oprogramowanie w rzeczywistych warunkach i zarejestrować wszystkie anomalie.

## 1. Środowisko testowe

| Element | Wartość |
|---|---|
| Maszyna | [DO UZUPEŁNIENIA] |
| System | [DO UZUPEŁNIENIA] |
| Wersja oprogramowania | [DO UZUPEŁNIENIA] |
| Środowisko | [Kontrolowana produkcja / Preprodukcja / Rzeczywisty serwer] |
| Kopia zapasowa wykonana | [Tak / Nie] |
| Data kopii zapasowej | [RRRR-MM-DD] |
| Metoda wycofania | [DO UZUPEŁNIENIA] |

## 2. Przetestowane scenariusze

| ID | Scenariusz | Polecenie | Oczekiwany wynik | Uzyskany wynik | Status |
|---:|---|---|---|---|---|
| T-001 | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [OK / KO / Częściowo] |
| T-002 | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [OK / KO / Częściowo] |

## 3. Siatka obserwacji

| Obszar | Obserwowany element | Wynik | Komentarz |
|---|---|---|---|
| Funkcjonalny | Oczekiwana funkcja | [OK / KO] | [DO UZUPEŁNIENIA] |
| Interfejs | Czytelność poleceń | [OK / KO] | [DO UZUPEŁNIENIA] |
| Wydajność | Czas wykonania | [OK / KO] | [DO UZUPEŁNIENIA] |
| Stabilność | Brak nieoczekiwanej awarii | [OK / KO] | [DO UZUPEŁNIENIA] |
| Błędy | Zrozumiałość komunikatów | [OK / KO] | [DO UZUPEŁNIENIA] |
| Logi | Jakość i użyteczność | [OK / KO] | [DO UZUPEŁNIENIA] |
| Bezpieczeństwo | Bezpieczne zachowanie | [OK / KO] | [DO UZUPEŁNIENIA] |
| Kompatybilność | Działanie na rzeczywistym celu | [OK / KO] | [DO UZUPEŁNIENIA] |
| Estetyka | Czytelność wyników | [OK / KO] | [DO UZUPEŁNIENIA] |
| Rzeczywiste użycie | Płynność pracy | [OK / KO] | [DO UZUPEŁNIENIA] |

## 4. Dziennik anomalii

| ID | Data | Waga | Opis | Logi | Hipoteza | Proponowana poprawka | Status |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [RRRR-MM-DD] | [Krytyczna / Poważna / Drobna / Estetyczna] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Otwarty / Poprawiony / Zatwierdzony] |
| BUG-002 | [RRRR-MM-DD] | [Krytyczna / Poważna / Drobna / Estetyczna] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [Otwarty / Poprawiony / Zatwierdzony] |

## Zatwierdzenie fazy 6

- [ ] Wszystkie krytyczne scenariusze zostały przetestowane.
- [ ] Błędy są zarejestrowane.
- [ ] Problemy z ergonomią są zarejestrowane.
- [ ] Problemy estetyczne są zarejestrowane.
- [ ] Żaden krytyczny błąd blokujący nie jest ignorowany.

**Status:** [ ] W toku / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 7 — Plan ulepszeń, poprawki i kodowanie końcowe

**Wykonawca: AI**  
**Cel:** przekształcić anomalie w uszeregowane poprawki, a następnie wprowadzić niezbędne zmiany w kodzie.

## 1. Prompt analizy anomalii

```text
Oto dziennik testów produkcyjnych.

1. Uszereguj anomalie według wagi.
2. Pogrupuj powiązane anomalie.
3. Zidentyfikuj prawdopodobne przyczyny.
4. Zaproponuj minimalną poprawkę dla każdej anomalii.
5. Wskaż ryzyka regresji.
6. Zaproponuj testy do dodania.
7. Zaproponuj ulepszenia ergonomii.
8. Zaproponuj ulepszenia estetyczne.
9. Zmieniaj tylko to, co konieczne.
10. Zachowaj zatwierdzone zachowania.
```

## 2. Priorytetyzacja anomalii

| Priorytet | Typ | Dotknięte anomalie | Postępowanie |
|---|---|---|---|
| P0 | Awaria, utrata danych, podatność | [BUG-XXX] | Natychmiastowa poprawka |
| P1 | Nieprawidłowa funkcja | [BUG-XXX] | Poprawka przed zatwierdzeniem końcowym |
| P2 | Złe doświadczenie użytkownika | [BUG-XXX] | Poprawka, jeśli rozsądna |
| P3 | Estetyka, komunikat, format | [BUG-XXX] | Poprawka lub odroczenie |
| P4 | Przyszłe ulepszenie | [BUG-XXX] | Backlog |

## 3. Wprowadzone poprawki

| ID | Anomalia | Poprawka | Zmienione pliki | Dodane testy | Ryzyko regresji | Status |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [DO UZUPEŁNIENIA] | [ścieżka] | [ścieżka] | [Niskie / Średnie / Wysokie] | [Wprowadzona / Zatwierdzona] |
| FIX-002 | [BUG-XXX] | [DO UZUPEŁNIENIA] | [ścieżka] | [ścieżka] | [Niskie / Średnie / Wysokie] | [Wprowadzona / Zatwierdzona] |

## Zatwierdzenie fazy 7

- [ ] Każda anomalia ma jasny status.
- [ ] Poprawki są wprowadzane według priorytetu.
- [ ] Testy nieregresji przechodzą.
- [ ] Zatwierdzone zachowania są zachowane.
- [ ] Każda poprawka jest udokumentowana.

**Status:** [ ] W toku / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 8 — Testy końcowe

**Wykonawca: Człowiek**  
**Cel:** zatwierdzić wersję kandydującą przed dokumentacją końcową i stabilnym wdrożeniem produkcyjnym.

## 1. Testy walidacyjne

| Test | Cel | Polecenie | Oczekiwany wynik | Uzyskany wynik | Status |
|---|---|---|---|---|---|
| Scenariusz nominalny | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |
| Scenariusz błędu | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |
| Opcje CLI | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |
| Konfiguracja | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |
| Uprawnienia | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |
| Przerwanie | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |
| Nieregresja | [DO UZUPEŁNIENIA] | [polecenie] | [DO UZUPEŁNIENIA] | [DO UZUPEŁNIENIA] | [ ] |

## 2. Lista kontrolna końcowa

- [ ] Projekt uruchamia się poprawnie.
- [ ] Główne polecenia działają.
- [ ] Błędy są zrozumiałe.
- [ ] Logi nadają się do analizy.
- [ ] Nie występuje żaden błąd krytyczny.
- [ ] Nie wykryto żadnej regresji.
- [ ] Wydajność jest akceptowalna.
- [ ] Bezpieczeństwo spełnia wymagania.
- [ ] Wersja jest identyfikowalna.
- [ ] Wycofanie zmian jest możliwe.

## Zatwierdzenie fazy 8

**Decyzja:** [ ] Wersja kandydująca / [ ] Powrót do poprawek  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 9 — Szkic dokumentacji

**Wykonawca: Człowiek**  
**Cel:** udokumentować oprogramowanie tak, jak rzeczywiście działa.

## 1. Dokumenty do przygotowania

| Dokument | Cel | Status |
|---|---|---|
| `README.md` | Prezentacja i szybki start | [ ] |
| `USER_GUIDE.md` | Szczegółowe i przystępne użycie | [ ] |
| `TECHNICAL_GUIDE.md` | Architektura i działanie wewnętrzne | [ ] |
| `DEVELOPER_GUIDE.md` | Środowisko, testy, konwencje | [ ] |
| `INSTALLATION.md` | Wymagania i instalacja | [ ] |
| `SECURITY.md` | Ryzyka, uprawnienia, dobre praktyki | [ ] |
| `TROUBLESHOOTING.md` | Częste błędy i rozwiązania | [ ] |
| `CHANGELOG.md` | Historia wersji | [ ] |

## 2. Treści do sprawdzenia

- [ ] Każde polecenie jest udokumentowane.
- [ ] Każda opcja jest udokumentowana.
- [ ] Każdy plik konfiguracyjny jest udokumentowany.
- [ ] Każda zależność jest udokumentowana.
- [ ] Każdy częsty błąd jest wyjaśniony.
- [ ] Ograniczenia są jasno określone.
- [ ] Przykłady dają się przetestować.

## Zatwierdzenie fazy 9

**Status:** [ ] Szkic / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 10 — Formatowanie i dokumentacja końcowa

**Wykonawca: AI**  
**Cel:** uzupełnić, uporządkować i ujednolicić dokumentację bez wymyślania zachowań nieobecnych w kodzie.

## 1. Prompt uzupełniania dokumentacji

```text
Oto szkice dokumentacji.

1. Sprawdź spójność z rzeczywistym kodem.
2. Wykryj nieudokumentowane funkcje.
3. Wykryj nieudokumentowane opcje CLI.
4. Wykryj niewyjaśnione komunikaty błędów.
5. Wykryj brakujące zależności.
6. Wykryj brakujące kroki instalacji.
7. Wykryj niespójności między dokumentami.
8. Popraw strukturę i czytelność.
9. Uzupełnij brakujące sekcje.
10. Nie zmieniaj żadnego opisanego zachowania bez dowodu w kodzie.
```

## 2. Kontrole dokumentacji

| Kontrola | Status | Komentarz |
|---|---|---|
| Spójność z kodem | [ ] | [DO UZUPEŁNIENIA] |
| Polecenia udokumentowane | [ ] | [DO UZUPEŁNIENIA] |
| Opcje udokumentowane | [ ] | [DO UZUPEŁNIENIA] |
| Kody wyjścia udokumentowane | [ ] | [DO UZUPEŁNIENIA] |
| Konfiguracja udokumentowana | [ ] | [DO UZUPEŁNIENIA] |
| Zależności udokumentowane | [ ] | [DO UZUPEŁNIENIA] |
| Częste błędy udokumentowane | [ ] | [DO UZUPEŁNIENIA] |
| Przykłady do przetestowania | [ ] | [DO UZUPEŁNIENIA] |
| Ujednolicona struktura | [ ] | [DO UZUPEŁNIENIA] |

## Zatwierdzenie fazy 10

**Status:** [ ] Szkic / [ ] Zatwierdzony  
**Zatwierdził:** [IMIĘ_NAZWISKO]  
**Data:** [RRRR-MM-DD]

---

# Faza 11 — Końcowe wdrożenie produkcyjne

**Wykonawca: Człowiek**  
**Cel:** wdrożyć wersję zatwierdzoną, udokumentowaną i przetestowaną.

## 1. Przygotowanie

- [ ] Wersja zatwierdzona w fazie 8.
- [ ] Dokumentacja końcowa zatwierdzona w fazie 10.
- [ ] Kopia zapasowa istniejącego środowiska wykonana.
- [ ] Procedura wycofania dostępna.
- [ ] Tag wersji utworzony.

Polecenia:

```bash
git tag -a v[VERSION] -m "Wersja stabilna [VERSION]"
git push origin v[VERSION]
```

## 2. Pakowanie

```bash
python -m build
```

Weryfikacja:

```bash
sha256sum dist/*
```

## 3. Wdrożenie

| Krok | Polecenie / działanie | Status | Komentarz |
|---:|---|---|---|
| 1 | Kopia zapasowa | [ ] | [DO UZUPEŁNIENIA] |
| 2 | Wdrożenie otagowanej wersji | [ ] | [DO UZUPEŁNIENIA] |
| 3 | Sprawdzenie usługi | [ ] | [DO UZUPEŁNIENIA] |
| 4 | Sprawdzenie logów | [ ] | [DO UZUPEŁNIENIA] |
| 5 | Test głównego polecenia | [ ] | [DO UZUPEŁNIENIA] |
| 6 | Udokumentowanie wdrożonej wersji | [ ] | [DO UZUPEŁNIENIA] |

## 4. Kontrole po wdrożeniu

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] Usługa jest aktywna.
- [ ] W logach nie pojawia się żaden błąd krytyczny.
- [ ] Główne polecenie odpowiada.
- [ ] Wdrożona wersja odpowiada zatwierdzonemu tagowi.
- [ ] Wycofanie jest udokumentowane i możliwe do przetestowania.

## Zatwierdzenie końcowe

| Pole | Wartość |
|---|---|
| Wdrożona wersja | [VERSION] |
| Data wdrożenia produkcyjnego | [RRRR-MM-DD] |
| Środowisko | [DO UZUPEŁNIENIA] |
| Odpowiedzialny | [IMIĘ_NAZWISKO] |
| Wycofanie przetestowane | [Tak / Nie] |
| Status końcowy | [W produkcji / Niepowodzenie / Wycofanie] |

---

# Historia zmian dokumentu

| Data | Wersja | Autor | Zmiana |
|---|---|---|---|
| [RRRR-MM-DD] | 0.1 | [IMIĘ_NAZWISKO] | Utworzenie szablonu |
| [RRRR-MM-DD] | [VERSION] | [IMIĘ_NAZWISKO] | [DO UZUPEŁNIENIA] |
