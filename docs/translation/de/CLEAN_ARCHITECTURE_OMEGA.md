# Projektarchitektur — Clean Architecture

**Sprachen:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Dieses Dokument erklärt, wie das Projekt organisiert ist, warum diese Organisation gewählt wurde und was jeder Ordner enthält. Es richtet sich sowohl an Besucher, die verstehen möchten, wie die Anwendung funktioniert, als auch an Entwickler, die zum Projekt beitragen oder es warten möchten.

Die Anwendung folgt einer **Clean Architecture**: Der Kern der Software ist von technischen Details, Benutzeroberflächen und externen Abhängigkeiten isoliert. Diese Trennung macht das Projekt leichter lesbar, testbar, wartbar und erweiterbar.

---

## 1. Grundprinzip

Die Anwendung ist in Schichten aufgeteilt, von denen jede eine klar umrissene Rolle hat.

Die zentrale Idee ist einfach:

```text
Die Oberfläche fordert eine Aktion an.
Die Anwendung orchestriert diese Aktion.
Die Domäne wendet die Geschäftsregeln an.
Die Ports definieren, was die Anwendung braucht.
Die Infrastruktur liefert die konkreten Implementierungen.
```

Dadurch hängt die wichtige Logik des Projekts nicht direkt ab:

- vom Terminal;
- von der grafischen Oberfläche;
- von einer Datenbank;
- vom Netzwerk;
- vom Dateisystem;
- von einer externen Bibliothek;
- von einem Systemwerkzeug.

Diese Unabhängigkeit ermöglicht es, einen Teil der Software zu ersetzen, ohne den ganzen Rest neu zu schreiben.

---

## 2. Überblick

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, Lebenszyklus und Dependency Injection
        ├── core/             Querschnittliche Fähigkeiten, Enums und Ausnahmen
        ├── domain/           Reine Geschäftslogik
        ├── application/      Anwendungsfälle: Commands und Queries
        ├── infrastructure/   Backends, Speicherung, Exporte, Logs, Systemsonden…
        ├── ports/            Protocol- / ABC-Verträge
        ├── interfaces/       CLI und TUI
        ├── plugins/          Integrierte Erweiterungen
        └── shared/           Parsing, Netzwerk, Formatierung und querschnittliche Hilfsmittel
```

---

## 3. Abhängigkeitsdiagramm

Abhängigkeiten müssen immer in dieselbe Richtung zeigen:

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

In der Praxis:

- `interfaces/` darf `application/` aufrufen.
- `application/` darf `domain/` aufrufen und die in `ports/` definierten Verträge verwenden.
- `domain/` hängt weder von `application/` noch von `infrastructure/` noch von `interfaces/` ab.
- `infrastructure/` implementiert die in `ports/` definierten Verträge.
- `app/` setzt die Schichten zusammen und stellt die benötigten Abhängigkeiten bereit.

Grundregel:

> Die Domäne kennt die Infrastruktur niemals.  
> Die Infrastruktur kennt die Ports, aber die Domäne kennt die Infrastruktur nicht.

---

## 4. Der Ordner `app/`

### Rolle

Der Ordner `app/` ist der **Montagepunkt** der Anwendung.

Er enthält:

- den Start der Anwendung;
- den Lebenszyklus;
- den Dependency-Injection-Container;
- den Aufbau der für den Betrieb nötigen Objekte;
- die Auswahl der konkreten Implementierungen;
- die Initialisierung der Konfiguration;
- die Verbindung zwischen den Schichten.

### Beispiele für Zuständigkeiten

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Datei | Rolle |
|---|---|
| `bootstrap.py` | Startet die Anwendung und wählt die zu startende Oberfläche |
| `container.py` | Erzeugt und verdrahtet die Abhängigkeiten |
| `lifecycle.py` | Verwaltet Start, Beenden und Aufräumen |

### Regel

`app/` enthält keine Geschäftslogik.

Er entscheidet nicht:

- was eine Geschäftsregel ist;
- wie ein Wert berechnet werden muss;
- wie eine Anfrage analysiert werden muss;
- wie eine Datei exportiert werden muss.

Er setzt nur die vorhandenen Komponenten zusammen.

---

## 5. Der Ordner `core/`

### Rolle

Der Ordner `core/` enthält das **querschnittliche Vokabular** des Projekts.

Er bündelt Elemente, die von mehreren Schichten geteilt werden, aber selbst keine Geschäftsregeln sind.

Er kann enthalten:

- Fähigkeiten;
- Aufzählungen;
- Konstanten;
- querschnittliche Ausnahmen;
- gemeinsame Typen;
- Plattforminformationen;
- Definitionen von Stufen oder Zuständen.

### Beispiel

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Datei | Rolle |
|---|---|
| `capabilities.py` | Beschreibt verfügbare oder aktivierbare Fähigkeiten |
| `constants.py` | Enthält die Konstanten des Projekts |
| `enums.py` | Definiert mögliche Zustände, Typen oder Stufen |
| `exceptions.py` | Definiert querschnittliche Fehler |

### Regel

`core/` muss schlank und stabil bleiben.

Er darf nicht enthalten:

- komplexe Geschäftslogik;
- Netzwerkaufrufe;
- Festplattenzugriffe;
- Code der Benutzeroberfläche;
- direkte Abhängigkeiten von externen Bibliotheken.

---

## 6. Der Ordner `domain/`

### Rolle

Der Ordner `domain/` ist das **Herz des Projekts**.

Er enthält die reine Geschäftslogik: die Regeln, Konzepte und Berechnungen, die wirklich festlegen, was die Anwendung tut.

Er kann enthalten:

- Entitäten;
- Value Objects;
- Richtlinien (Policies);
- Geschäftsregeln;
- Domänendienste;
- Berechnungen;
- fachliche Validierungen;
- fachliche Datenmodelle.

### Beispiel

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Element | Rolle |
|---|---|
| Entität | Geschäftsobjekt mit Identität |
| Value Object | Unveränderlicher und validierter Wert |
| Policy | Wiederverwendbare Geschäftsregel |
| Domänendienst | Geschäftslogik, die nicht zu einer einzelnen Entität gehört |

### Strenge Regeln

Der Ordner `domain/`:

- greift nicht auf die Festplatte zu;
- führt keine Netzwerkaufrufe aus;
- führt keine Systembefehle aus;
- greift auf keine Datenbank zu;
- importiert nicht die Benutzeroberfläche;
- importiert nicht die Infrastruktur;
- hängt nicht von einer externen technischen Bibliothek ab, wenn sich das vermeiden lässt.

Die Domäne muss ohne Server, ohne Dateien, ohne Netzwerk und ohne Oberfläche testbar sein.

---

## 7. Der Ordner `application/`

### Rolle

Der Ordner `application/` orchestriert die Anwendungsfälle.

Er beantwortet die Frage:

> „Was passiert, wenn der Benutzer diese Aktion anfordert?“

Er enthält:

- die Commands;
- die Queries;
- die Anwendungsfälle;
- die Orchestratoren;
- die Aktions-Handler;
- die Koordination zwischen Domäne und Ports.

### Unterscheidung Commands / Queries

| Typ | Ziel | Ändert Daten |
|---|---|---|
| Command | Eine Aktion ausführen | Ja |
| Query | Eine Information lesen oder berechnen | Nein |

Beispiele:

| Command | Query |
|---|---|
| Eine Konfiguration anwenden | Die aktuelle Konfiguration lesen |
| Eine Analyse starten | Das Ergebnis einer Analyse abrufen |
| Einen Bericht exportieren | Verfügbare Elemente auflisten |
| Daten bereinigen | Einen Verlauf einsehen |

### Beispiel

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Regel

`application/` enthält nicht:

- Terminalausgaben;
- eine Textual-Oberfläche;
- Rich-Befehle;
- direkten Datenbankzugriff;
- direkte Aufrufe externer Werkzeuge.

Er koordiniert, implementiert aber keine technischen Details.

---

## 8. Der Ordner `ports/`

### Rolle

Der Ordner `ports/` definiert die von der Anwendung erwarteten **Verträge**.

Ein Port beschreibt, **was die Anwendung braucht**, ohne vorzuschreiben, wie es umgesetzt werden muss.

Er enthält in der Regel:

- `Protocol`-Definitionen;
- abstrakte `ABC`-Klassen;
- Repository-Schnittstellen;
- Export-Schnittstellen;
- Sonden-Schnittstellen;
- Schnittstellen zu externen Diensten;
- Speicher-Schnittstellen.

### Beispiel

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Rolle |
|---|---|
| `Repository` | Daten lesen oder speichern |
| `Exporter` | Eine Ausgabe in einem bestimmten Format erzeugen |
| `Probe` | Eine System- oder Netzwerkinformation sammeln |
| `Storage` | Ein Persistenz-Backend verwalten |

### Konzeptionelles Beispiel

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Dieser Vertrag sagt:

> „Die Anwendung braucht ein Objekt, das einen Bericht exportieren kann.“

Er sagt nicht:

- ob der Export in Markdown erfolgt;
- ob der Export in JSON erfolgt;
- ob die Datei lokal geschrieben wird;
- ob der Export über das Netzwerk gesendet wird.

Diese Entscheidungen gehören zu `infrastructure/`.

### Regel

Ports sind Verträge, keine Implementierungen.

Sie dürfen nicht enthalten:

- komplexe Geschäftslogik;
- Festplattenzugriffe;
- Netzwerkaufrufe;
- konkrete Implementierungen;
- direkte Abhängigkeiten von externen Bibliotheken.

---

## 9. Der Ordner `infrastructure/`

### Rolle

Der Ordner `infrastructure/` enthält die **konkreten Implementierungen** der Ports.

Es ist die Schicht, die mit der Außenwelt kommuniziert.

Er kann enthalten:

- Dateizugriffe;
- Datenbankzugriffe;
- Exporte in Markdown, JSON, CSV oder andere Formate;
- Logging;
- Netzwerkaufrufe;
- Systemsonden;
- kontrollierte Ausführung externer Werkzeuge;
- Adapter für Drittanbieter-Bibliotheken;
- Repository-Implementierungen;
- Speicher-Implementierungen.

### Beispiel

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

| Element | Rolle |
|---|---|
| `sqlite_repository.py` | Implementiert ein Repository mit SQLite |
| `json_file_repository.py` | Implementiert ein Repository mit JSON-Dateien |
| `markdown_exporter.py` | Exportiert einen Bericht in Markdown |
| `json_exporter.py` | Exportiert einen Bericht in JSON |
| `process_probe.py` | Sammelt Informationen über Prozesse |
| `filesystem_probe.py` | Sammelt Informationen über das Dateisystem |
| `structured_logger.py` | Erzeugt strukturierte Logs |

### Regel

`infrastructure/` ist die einzige Schicht, die direkt zugreifen darf auf:

- das Dateisystem;
- das Netzwerk;
- SQLite;
- externe Bibliotheken;
- Systemwerkzeuge;
- Unterprozesse, wenn sie nötig und kontrolliert sind.

Diese Bündelung erleichtert:

- das Testen;
- das Sicherheitsaudit;
- den Austausch eines Backends;
- die Begrenzung von Nebenwirkungen.

---

## 10. Der Ordner `interfaces/`

### Rolle

Der Ordner `interfaces/` enthält die für den Benutzer sichtbaren Einstiegspunkte.

Er trennt klar:

- die CLI;
- die TUI;
- mögliche künftige Web- oder API-Oberflächen.

### Struktur

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

| Oberfläche | Technologie | Rolle |
|---|---|---|
| `cli/` | Rich | Kommandozeilenoberfläche |
| `tui/` | Textual | Interaktive Terminaloberfläche |

### CLI

Die CLI ist die Kommandozeilenoberfläche.

Sie ermöglicht:

- die Anwendung zu starten;
- eine bestimmte Aktion auszuführen;
- ein Ergebnis anzuzeigen;
- eine Aufgabe zu automatisieren;
- das Werkzeug in ein Skript einzubinden;
- die Anwendung per SSH aus der Ferne zu nutzen.

### TUI

Die TUI ist die interaktive Terminaloberfläche.

Sie ermöglicht:

- zwischen den Funktionen zu navigieren;
- Informationen anzuzeigen;
- Aktionen auszuführen;
- Ergebnisse einzusehen;
- die Anwendung zu nutzen, ohne sich alle Befehle merken zu müssen.

### Regel

Oberflächen enthalten keine Geschäftslogik.

Sie:

- nehmen eine Absicht des Benutzers entgegen;
- rufen einen Anwendungsfall in `application/` auf;
- zeigen das Ergebnis an;
- übersetzen Fehler in verständliche Meldungen.

Sie dürfen nicht:

- die Infrastruktur direkt aufrufen;
- Unterprozesse ausführen;
- direkt auf Dateien zugreifen;
- Geschäftsregeln enthalten;
- die Logik von `application/` duplizieren.

---

## 11. Der Ordner `plugins/`

### Rolle

Der Ordner `plugins/` ist für **integrierte Erweiterungen** reserviert.

Er ermöglicht es, Funktionen hinzuzufügen, ohne den Kern des Projekts zu überladen.

Ein Plugin kann zum Beispiel:

- ein Exportformat hinzufügen;
- eine Sonde hinzufügen;
- einen Befehl hinzufügen;
- einen TUI-Bildschirm hinzufügen;
- eine externe Integration hinzufügen;
- eine optionale Fähigkeit hinzufügen.

### Prinzip

Ein Plugin muss dieselben Regeln einhalten wie der Rest des Projekts:

- es umgeht die Ports nicht;
- es ändert die Domäne nicht direkt;
- es stellt seine Funktionen über klare Verträge bereit;
- es bleibt deaktivierbar, ohne die Anwendung zu beschädigen.

### Mögliche Struktur

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Regel

Ein Plugin ist eine Erweiterung, keine Hintertür.

Es muss die Gesamtarchitektur einhalten und darf keine zirkulären Abhängigkeiten zum Kern des Projekts erzeugen.

---

## 12. Der Ordner `shared/`

### Rolle

Der Ordner `shared/` enthält querschnittliche Hilfsmittel, die weder zur Domäne noch zur Anwendung noch zur Infrastruktur gehören.

Er bündelt wiederverwendbare generische Funktionen.

Er kann enthalten:

- Parsing;
- Netzwerk-Hilfsmittel;
- Formatierung;
- Textverarbeitung;
- Datums-Hilfsfunktionen;
- Pfad-Hilfsfunktionen;
- generische Validierungshilfen;
- Serialisierungs-Hilfsfunktionen.

### Beispiel

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Ordner | Rolle |
|---|---|
| `parsing/` | Analyse von Text, JSON, YAML oder anderen Formaten |
| `network/` | Generische Netzwerk-Hilfsmittel |
| `formatting/` | Formatierung von Werten, Daten, Größen oder Tabellen |
| `utils/` | Querschnittliche Hilfsfunktionen |

### Regel

`shared/` darf nicht zur Rumpelkammer werden.

Ein Hilfsmittel gehört nur dann nach `shared/`, wenn es:

- wiederverwendbar ist;
- generisch ist;
- unabhängig von einem bestimmten Anwendungsfall ist;
- für mehrere Schichten nützlich ist.

---

## 13. Übersicht der Zuständigkeiten

| Ordner | Hauptrolle | Darf abhängen von | Darf nicht abhängen von |
|---|---|---|---|
| `app/` | Anwendung zusammensetzen und starten | Allen Schichten | — |
| `core/` | Vokabular, Konstanten, Enums und Ausnahmen | `shared/` bei Bedarf | `infrastructure/`, `interfaces/` |
| `domain/` | Reine Geschäftslogik | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Anwendungsfälle orchestrieren | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Verträge definieren | `domain/` bei Bedarf | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Ports implementieren und mit der Außenwelt kommunizieren | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Mit dem Benutzer interagieren | `application/`, `core/` | `infrastructure/` direkt |
| `plugins/` | Erweiterungen hinzufügen | Je nach Art der Erweiterung | Umgehung der Architektur |
| `shared/` | Querschnittliche Hilfsmittel | Keiner fachlichen Schicht | Spezifischer Geschäftslogik |

---

## 14. Beispiel für den Ablauf einer Aktion

Nehmen wir einen Benutzer, der den Export eines Berichts in Markdown anfordert.

```text
1. Der Benutzer startet einen CLI-Befehl.

2. interfaces/cli/
   Nimmt den Befehl und seine Optionen entgegen.

3. interfaces/cli/
   Ruft den passenden Anwendungsfall in application/ auf.

4. application/
   Validiert die Absicht und bereitet die Aktion vor.

5. application/
   Nutzt die Domäne, um den Bericht zu erstellen oder zu validieren.

6. application/
   Fordert über den Port ReportExporter einen Export an.

7. infrastructure/
   Liefert die Implementierung MarkdownExporter.

8. infrastructure/
   Schreibt die Markdown-Datei auf die Festplatte.

9. interfaces/cli/
   Zeigt dem Benutzer das Ergebnis an.
```

Vereinfachtes Schema:

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
Markdown-Datei
```

---

## 15. Warum diese Architektur?

### Lesbarkeit

Jeder Ordner hat eine einzige Rolle, wodurch man leichter findet, wo eine Funktion hinzugefügt oder korrigiert werden muss.

### Testbarkeit

Die Domäne kann ohne Oberfläche, ohne Datenbank und ohne Netzwerkzugriff getestet werden.

### Wartbarkeit

Eine Änderung an der Oberfläche, an der Speicherung oder an einem externen Werkzeug darf kein Neuschreiben der Geschäftslogik erfordern.

### Sicherheit

Sensible Zugriffe — Dateien, Netzwerk, Unterprozesse, Datenbanken — sind in `infrastructure/` gebündelt. Das erleichtert Audit und Kontrolle.

### Erweiterbarkeit

Man kann hinzufügen:

- eine neue Oberfläche;
- ein neues Exportformat;
- ein neues Speicher-Backend;
- ein neues Plugin;
- eine neue Systemsonde;

ohne den fachlichen Kern zu verändern.

### Portabilität

Die Anwendung kann sich zu anderen Umgebungen, Systemen oder Interaktionsformen weiterentwickeln, ohne an eine bestimmte Technologie gebunden zu sein.

---

## 16. Regeln zum Merken

- Die Domäne ist rein.
- Die Anwendung orchestriert.
- Die Ports deklarieren die Bedürfnisse.
- Die Infrastruktur implementiert.
- Die Oberflächen zeigen an und nehmen entgegen.
- `app/` setzt zusammen.
- `core/` und `shared/` liefern das querschnittliche Vokabular und die Hilfsmittel.
- Plugins erweitern, ohne die Architektur zu umgehen.

In einem Satz:

> **Die Anwendung trennt, was sie tut, wie sie es tut und wie der Benutzer sie verwendet.**
