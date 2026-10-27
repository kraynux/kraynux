# Entwicklungsverfahren — [PROJECT_NAME]

**Sprachen:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Feld | Wert |
|---|---|
| Projekt | [PROJECT_NAME] |
| Zielversion | [TARGET_VERSION] |
| Verantwortlich | [NAME] |
| Erstellungsdatum | [JJJJ-MM-TT] |
| Letzte Aktualisierung | [JJJJ-MM-TT] |
| Gesamtstatus | Entwurf / In Arbeit / Validiert / In Produktion |
| Zielumgebung | [Linux / Debian / Server / Arbeitsplatz] |
| Hauptsprache | [Python / Bash / Lua / Andere] |
| Repository | [URL_ODER_PFAD] |

## Übergreifende Regeln

- [ ] Vor der Validierung des endgültigen Plans wird kein Code geschrieben.
- [ ] Jede wichtige Entscheidung wird dokumentiert.
- [ ] Jede Anomalie wird erfasst.
- [ ] Jede Korrektur wird getestet.
- [ ] Jede Verhaltensänderung wird dokumentiert.
- [ ] Vor jedem Eingriff in der Produktion werden Backups erstellt.
- [ ] Die KI analysiert und schlägt vor; der Mensch entscheidet, validiert und rollt aus.
- [ ] Der Code bleibt mit der endgültigen Dokumentation abgestimmt.

## Gesamtübersicht der Phasen

| Phase | Akteur | Hauptergebnis | Status | Validierungsdatum |
|---:|---|---|---|---|
| 1 | Mensch | Bedarf und Konzeption | [ ] | [JJJJ-MM-TT] |
| 2 | Mensch | Architekturentwurf und vorläufiger Plan | [ ] | [JJJJ-MM-TT] |
| 3 | KI | Analyse, Nebenwirkungen, endgültiger Plan | [ ] | [JJJJ-MM-TT] |
| 4 | Mensch | Projektkern programmiert | [ ] | [JJJJ-MM-TT] |
| 5 | KI | Code-Audit, Korrekturen und Tests | [ ] | [JJJJ-MM-TT] |
| 6 | Mensch | Reale Tests in der Produktion | [ ] | [JJJJ-MM-TT] |
| 7 | KI | Korrekturplan und finale Programmierung | [ ] | [JJJJ-MM-TT] |
| 8 | Mensch | Abschlusstests | [ ] | [JJJJ-MM-TT] |
| 9 | Mensch | Dokumentationsentwurf | [ ] | [JJJJ-MM-TT] |
| 10 | KI | Endgültige Dokumentation | [ ] | [JJJJ-MM-TT] |
| 11 | Mensch | Produktivsetzung | [ ] | [JJJJ-MM-TT] |

---

# Phase 1 — Überlegung, Bedarf, Nutzung und Konzeption

**Akteur: Mensch**  
**Ziel:** das Problem, die Benutzer, die reale Nutzung, die Einschränkungen und die Grenzen des Projekts festlegen.

## 1. Ausgangsproblem

- Erkanntes Problem: [AUSZUFÜLLEN]
- Aktuelle Situation: [AUSZUFÜLLEN]
- Folge des Problems: [AUSZUFÜLLEN]
- Projektziel: [AUSZUFÜLLEN]

## 2. Zielbenutzer

| Benutzer | Hauptbedarf | Technisches Niveau | Vorgesehene Nutzung |
|---|---|---|---|
| [Benutzer 1] | [AUSZUFÜLLEN] | [Einsteiger / Technisch / Experte] | [AUSZUFÜLLEN] |
| [Benutzer 2] | [AUSZUFÜLLEN] | [Einsteiger / Technisch / Experte] | [AUSZUFÜLLEN] |

## 3. Nutzungsszenarien

### Normalszenario

- Kontext: [AUSZUFÜLLEN]
- Aktion des Benutzers: [AUSZUFÜLLEN]
- Erwartetes Ergebnis: [AUSZUFÜLLEN]

### Grenzfallszenario

- Kontext: [AUSZUFÜLLEN]
- Aktion des Benutzers: [AUSZUFÜLLEN]
- Erwartetes Ergebnis: [AUSZUFÜLLEN]

### Fehlerszenario

- Kontext: [AUSZUFÜLLEN]
- Aktion des Benutzers: [AUSZUFÜLLEN]
- Erwartetes Ergebnis: [AUSZUFÜLLEN]

### Verbotenes oder gefährliches Szenario

- Kontext: [AUSZUFÜLLEN]
- Erwartetes Verhalten: [Ablehnung / Warnung / Blockierung / Protokollierung]
- Begründung: [AUSZUFÜLLEN]

## 4. Funktionen

### Pflicht

- [ ] [Funktion 1]
- [ ] [Funktion 2]
- [ ] [Funktion 3]

### Nützlich, aber verschiebbar

- [ ] [Funktion 1]
- [ ] [Funktion 2]

### Optional

- [ ] [Funktion 1]

### Ausgeschlossen

- [ ] [Ausgeschlossene Funktion]
- Begründung: [AUSZUFÜLLEN]

## 5. Einschränkungen

| Bereich | Einschränkung | Priorität |
|---|---|---|
| System | [Linux / Debian / Version] | [Hoch / Mittel / Niedrig] |
| Sprache | [Python / Bash / Lua] | [Hoch / Mittel / Niedrig] |
| Abhängigkeiten | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Leistung | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Sicherheit | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Kompatibilität | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Wartung | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Bereitstellung | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |

## 6. Erkannte Risiken

| Risiko | Auswirkung | Wahrscheinlichkeit | Vorbeugende Maßnahme |
|---|---|---|---|
| [Risiko 1] | [Niedrig / Mittel / Hoch] | [Niedrig / Mittel / Hoch] | [AUSZUFÜLLEN] |
| [Risiko 2] | [Niedrig / Mittel / Hoch] | [Niedrig / Mittel / Hoch] | [AUSZUFÜLLEN] |

## 7. Getroffene Entscheidungen

| ID | Entscheidung | Begründung | Datum |
|---:|---|---|---|
| D-001 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [JJJJ-MM-TT] |
| D-002 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [JJJJ-MM-TT] |

## 8. Offene Fragen

- [ ] [Frage 1]
- [ ] [Frage 2]

## Validierung von Phase 1

- [ ] Das Problem ist klar formuliert.
- [ ] Die Benutzer sind identifiziert.
- [ ] Die wichtigsten Nutzungsszenarien sind beschrieben.
- [ ] Die Pflichtfunktionen sind aufgelistet.
- [ ] Die Projektgrenzen sind explizit.
- [ ] Die technischen Einschränkungen sind bekannt.
- [ ] Die Hauptrisiken sind identifiziert.

**Status:** [ ] Entwurf / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 2 — Entwurf, Hauptkomponenten und Entwicklungsplan

**Akteur: Mensch**  
**Ziel:** den Bedarf in eine logische Architektur und einen umsetzbaren Entwicklungsplan überführen.

## 1. Hauptkomponenten

| Komponente | Zuständigkeit | Darf nicht | Priorität |
|---|---|---|---|
| Oberfläche / CLI | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Fachlicher Kern | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Konfiguration | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Datenmodelle | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Dienste | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Speicherung | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Export | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Logs | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Sicherheit | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| Tests | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |

## 2. Hauptablauf

```text
[Benutzereingabe]
    → [Oberfläche]
    → [Validierung]
    → [Fachlicher Kern]
    → [Dienste / Module]
    → [Ergebnis]
    → [Ausgabe / Speicherung / Logs]
```

## 3. Geplante Module

| Modul | Rolle | Abhängigkeiten | Priorität |
|---|---|---|---|
| [module_1] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| [module_2] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |
| [module_3] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Hoch / Mittel / Niedrig] |

## 4. Vorläufige Verzeichnisstruktur

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

## 5. Geplante Abhängigkeiten

| Abhängigkeit | Verwendung | Mindestversion | Begründung |
|---|---|---|---|
| [Abhängigkeit 1] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |
| [Abhängigkeit 2] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |

## 6. Aufteilung der Entwicklung

| Phase | Inhalt | Priorität | Schätzung |
|---:|---|---|---|
| 1 | Grundlagen: Struktur, Konfiguration, Fehler, Logs | [Hoch / Mittel] | [Dauer] |
| 2 | Modelle und Verträge | [Hoch / Mittel] | [Dauer] |
| 3 | Fachlicher Kern | [Hoch / Mittel] | [Dauer] |
| 4 | Oberfläche / CLI | [Hoch / Mittel] | [Dauer] |
| 5 | Speicherung / Export | [Hoch / Mittel] | [Dauer] |
| 6 | Tests | [Hoch / Mittel] | [Dauer] |
| 7 | Dokumentation und Paketierung | [Hoch / Mittel] | [Dauer] |

## Validierung von Phase 2

- [ ] Die Hauptkomponenten sind identifiziert.
- [ ] Jedes Modul hat eine klare Zuständigkeit.
- [ ] Die Hauptabläufe sind beschrieben.
- [ ] Die vorläufige Verzeichnisstruktur ist festgelegt.
- [ ] Die wichtigsten Abhängigkeiten sind identifiziert.
- [ ] Die Entwicklungsreihenfolge ist festgelegt.
- [ ] Es wurde noch keine Entwicklung begonnen.

**Status:** [ ] Entwurf / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 3 — KI-Analyse, Nebenwirkungen und endgültiger Plan

**Akteur: KI**  
**Ziel:** die vom Menschen erstellten Dokumente analysieren, Risiken erkennen und einen umsetzbaren endgültigen Plan erstellen.

## 1. Analysierte Dokumente

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Anderes Dokument]

## 2. KI-Analyse-Prompt

```text
Analysiere dieses Projekt, ohne Code zu schreiben.

1. Erkenne Inkonsistenzen.
2. Erkenne fehlende Funktionen.
3. Erkenne falsch platzierte Zuständigkeiten.
4. Identifiziere mögliche Nebenwirkungen.
5. Identifiziere Fehlerfälle.
6. Identifiziere Sicherheitsrisiken.
7. Identifiziere Kompatibilitätsprobleme.
8. Schlage eine robustere Projektstruktur vor.
9. Schlage einen endgültigen Entwicklungsplan vor.
10. Nenne die Punkte, die der menschlichen Entscheidung vorbehalten bleiben müssen.
```

## 3. Erkannte Inkonsistenzen

| ID | Beschreibung | Auswirkung | Vorschlag | Menschliche Entscheidung |
|---:|---|---|---|---|
| A-001 | [AUSZUFÜLLEN] | [Niedrig / Mittel / Hoch] | [AUSZUFÜLLEN] | [Angenommen / Abgelehnt / Verschoben] |
| A-002 | [AUSZUFÜLLEN] | [Niedrig / Mittel / Hoch] | [AUSZUFÜLLEN] | [Angenommen / Abgelehnt / Verschoben] |

## 4. Erkannte Nebenwirkungen

| ID | Nebenwirkung | Auslöser | Auswirkung | Vorbeugung | Status |
|---:|---|---|---|---|---|
| SE-001 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Niedrig / Mittel / Hoch] | [AUSZUFÜLLEN] | [Offen / Behandelt / Akzeptiert] |
| SE-002 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Niedrig / Mittel / Hoch] | [AUSZUFÜLLEN] | [Offen / Behandelt / Akzeptiert] |

## 5. Vorherzusehende Fehlerfälle

| Fall | Erwartetes Verhalten | Erwartete Meldung / erwarteter Log | Zugehöriger Test |
|---|---|---|---|
| Fehlende Datei | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |
| Zugriff verweigert | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |
| Netzwerk nicht verfügbar | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |
| Ungültige Eingabe | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |
| Abbruch durch den Benutzer | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |
| Beschädigte Daten | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] |

## 6. Sicherheitsrisiken

| Risiko | Szenario | Maßnahme | Priorität |
|---|---|---|---|
| [Risiko 1] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [P0 / P1 / P2] |
| [Risiko 2] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [P0 / P1 / P2] |

## 7. Endgültiger Entwicklungsplan

| Phase | Ziel | Ergebnisse | Abschlusskriterien | Abhängigkeiten |
|---:|---|---|---|---|
| 1 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Keine] |
| 2 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Phase 1] |
| 3 | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Phase 2] |

## Validierung von Phase 3

- [ ] Die Inkonsistenzen sind behandelt oder dokumentiert.
- [ ] Die Nebenwirkungen sind identifiziert.
- [ ] Die Fehlerfälle sind vorhergesehen.
- [ ] Die Sicherheitsrisiken sind behandelt.
- [ ] Der endgültige Plan ist vom Menschen validiert.
- [ ] Die endgültigen Entscheidungen sind festgehalten.

**Status:** [ ] Entwurf / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 4 — Programmierung des Projektkerns

**Akteur: Mensch**  
**Ziel:** den funktionalen Kern entwickeln, ohne Funktionen außerhalb des Umfangs hinzuzufügen.

## 1. Umfang der Programmierung

- [ ] Projektstruktur
- [ ] Virtuelle Umgebung
- [ ] Abhängigkeiten
- [ ] Konfiguration
- [ ] Datenmodelle
- [ ] Ausnahmen
- [ ] Logging
- [ ] Fachliche Dienste
- [ ] Fachlicher Kern
- [ ] Unit-Tests
- [ ] CLI / Oberfläche
- [ ] Integration

## 2. Reihenfolge der Umsetzung

| Reihenfolge | Element | Datei / Modul | Status | Commit |
|---:|---|---|---|---|
| 1 | [Element] | [Pfad] | [ ] | [hash] |
| 2 | [Element] | [Pfad] | [ ] | [hash] |
| 3 | [Element] | [Pfad] | [ ] | [hash] |

## 3. Commit-Regeln

- Ein Commit = eine einzige Absicht.
- Funktion, Korrektur und Refactoring nicht vermischen.
- Empfohlene Nachricht:

```text
[type]: [kurze Beschreibung]

[type] = feat, fix, refactor, test, docs, chore
```

Beispiel:

```text
feat: Laden und Validieren der Konfiguration hinzufügen
```

## 4. Erste Tests

| Test | Ziel | Befehl | Erwartetes Ergebnis | Status |
|---|---|---|---|---|
| [Test 1] | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [ ] |
| [Test 2] | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [ ] |

## Validierung von Phase 4

- [ ] Der fachliche Kern funktioniert.
- [ ] Die wichtigsten Eingaben werden validiert.
- [ ] Die wichtigsten Fehler werden behandelt.
- [ ] Die Unit-Tests bestehen.
- [ ] Das Projekt startet im Basismodus.
- [ ] Es wurde keine Funktion außerhalb des Umfangs hinzugefügt.

**Status:** [ ] In Arbeit / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 5 — Code-Analyse, Korrektur und Tests durch die KI

**Akteur: KI**  
**Ziel:** Fehler, Nebenwirkungen und Risiken vor den realen Tests erkennen.

## 1. KI-Audit-Prompt

```text
Analysiere den Code, ohne ihn komplett neu zu schreiben.

1. Prüfe die Übereinstimmung mit dem Entwicklungsplan.
2. Erkenne wahrscheinliche Bugs.
3. Erkenne Nebenwirkungen.
4. Erkenne Ressourcenlecks.
5. Erkenne nicht behandelte Fehler.
6. Erkenne nicht validierte Eingaben.
7. Erkenne Sicherheitsprobleme.
8. Erkenne Leistungsprobleme.
9. Erkenne toten Code.
10. Erkenne falsch platzierte Zuständigkeiten.
11. Schlage gezielte Korrekturen vor.
12. Schlage fehlende Tests vor.
```

## 2. Audit-Ergebnisse

| ID | Datei / Funktion | Feststellung | Schweregrad | Vorgeschlagene Korrektur | Status |
|---:|---|---|---|---|---|
| C-001 | [Pfad] | [AUSZUFÜLLEN] | [Kritisch / Schwer / Gering] | [AUSZUFÜLLEN] | [Offen / Korrigiert / Validiert] |
| C-002 | [Pfad] | [AUSZUFÜLLEN] | [Kritisch / Schwer / Gering] | [AUSZUFÜLLEN] | [Offen / Korrigiert / Validiert] |

## 3. Hinzugefügte Tests

| Test | Ziel | Testdatei | Status |
|---|---|---|---|
| [Test 1] | [AUSZUFÜLLEN] | [Pfad] | [ ] |
| [Test 2] | [AUSZUFÜLLEN] | [Pfad] | [ ] |

## Validierung von Phase 5

- [ ] Die kritischen Bugs sind behoben.
- [ ] Die Nebenwirkungen sind behandelt oder dokumentiert.
- [ ] Die Unit-Tests bestehen.
- [ ] Die Integrationstests bestehen.
- [ ] Der Code entspricht dem endgültigen Plan.
- [ ] Die Korrekturen wurden schrittweise angewendet.

**Status:** [ ] In Arbeit / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 6 — Reale Untersuchung und Tests in der Produktion

**Akteur: Mensch**  
**Ziel:** die Software unter realen Bedingungen validieren und alle Anomalien erfassen.

## 1. Testumgebung

| Element | Wert |
|---|---|
| Maschine | [AUSZUFÜLLEN] |
| System | [AUSZUFÜLLEN] |
| Softwareversion | [AUSZUFÜLLEN] |
| Umgebung | [Kontrollierte Produktion / Vorproduktion / Realer Server] |
| Backup durchgeführt | [Ja / Nein] |
| Backup-Datum | [JJJJ-MM-TT] |
| Rollback-Methode | [AUSZUFÜLLEN] |

## 2. Getestete Szenarien

| ID | Szenario | Befehl | Erwartetes Ergebnis | Tatsächliches Ergebnis | Status |
|---:|---|---|---|---|---|
| T-001 | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [OK / KO / Teilweise] |
| T-002 | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [OK / KO / Teilweise] |

## 3. Beobachtungsraster

| Bereich | Beobachtetes Element | Ergebnis | Kommentar |
|---|---|---|---|
| Funktional | Erwartete Funktion | [OK / KO] | [AUSZUFÜLLEN] |
| Oberfläche | Klarheit der Befehle | [OK / KO] | [AUSZUFÜLLEN] |
| Leistung | Ausführungszeit | [OK / KO] | [AUSZUFÜLLEN] |
| Stabilität | Kein unerwarteter Absturz | [OK / KO] | [AUSZUFÜLLEN] |
| Fehler | Verständlichkeit der Meldungen | [OK / KO] | [AUSZUFÜLLEN] |
| Logs | Qualität und Nutzen | [OK / KO] | [AUSZUFÜLLEN] |
| Sicherheit | Sicheres Verhalten | [OK / KO] | [AUSZUFÜLLEN] |
| Kompatibilität | Funktion auf dem realen Ziel | [OK / KO] | [AUSZUFÜLLEN] |
| Ästhetik | Lesbarkeit der Ausgaben | [OK / KO] | [AUSZUFÜLLEN] |
| Reale Nutzung | Flüssigkeit des Arbeitsablaufs | [OK / KO] | [AUSZUFÜLLEN] |

## 4. Anomalieprotokoll

| ID | Datum | Schweregrad | Beschreibung | Logs | Hypothese | Vorgeschlagene Korrektur | Status |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [JJJJ-MM-TT] | [Kritisch / Schwer / Gering / Ästhetisch] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Offen / Korrigiert / Validiert] |
| BUG-002 | [JJJJ-MM-TT] | [Kritisch / Schwer / Gering / Ästhetisch] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [Offen / Korrigiert / Validiert] |

## Validierung von Phase 6

- [ ] Alle kritischen Szenarien wurden getestet.
- [ ] Die Bugs sind erfasst.
- [ ] Die Bedienbarkeitsprobleme sind erfasst.
- [ ] Die ästhetischen Probleme sind erfasst.
- [ ] Kein kritischer blockierender Bug wird ignoriert.

**Status:** [ ] In Arbeit / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 7 — Verbesserungsplan, Korrekturen und finale Programmierung

**Akteur: KI**  
**Ziel:** Anomalien in priorisierte Korrekturen umwandeln und dann die nötigen Codeänderungen anwenden.

## 1. Prompt zur Analyse der Anomalien

```text
Hier ist das Protokoll der Produktionstests.

1. Ordne die Anomalien nach Schweregrad.
2. Gruppiere zusammenhängende Anomalien.
3. Identifiziere die wahrscheinlichen Ursachen.
4. Schlage für jede Anomalie eine minimale Korrektur vor.
5. Nenne die Regressionsrisiken.
6. Schlage hinzuzufügende Tests vor.
7. Schlage Verbesserungen der Bedienbarkeit vor.
8. Schlage ästhetische Verbesserungen vor.
9. Ändere nur das Nötige.
10. Bewahre das validierte Verhalten.
```

## 2. Priorisierung der Anomalien

| Priorität | Typ | Betroffene Anomalien | Behandlung |
|---|---|---|---|
| P0 | Absturz, Datenverlust, Sicherheitslücke | [BUG-XXX] | Sofortige Korrektur |
| P1 | Fehlerhafte Funktion | [BUG-XXX] | Korrektur vor der finalen Validierung |
| P2 | Schlechte Benutzererfahrung | [BUG-XXX] | Korrektur, wenn vertretbar |
| P3 | Ästhetik, Meldung, Format | [BUG-XXX] | Korrektur oder Verschiebung |
| P4 | Künftige Verbesserung | [BUG-XXX] | Backlog |

## 3. Angewendete Korrekturen

| ID | Anomalie | Korrektur | Geänderte Dateien | Hinzugefügte Tests | Regressionsrisiko | Status |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [AUSZUFÜLLEN] | [Pfad] | [Pfad] | [Niedrig / Mittel / Hoch] | [Angewendet / Validiert] |
| FIX-002 | [BUG-XXX] | [AUSZUFÜLLEN] | [Pfad] | [Pfad] | [Niedrig / Mittel / Hoch] | [Angewendet / Validiert] |

## Validierung von Phase 7

- [ ] Jede Anomalie hat einen klaren Status.
- [ ] Die Korrekturen werden nach Priorität angewendet.
- [ ] Die Nicht-Regressionstests bestehen.
- [ ] Das validierte Verhalten bleibt erhalten.
- [ ] Jede Korrektur ist dokumentiert.

**Status:** [ ] In Arbeit / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 8 — Abschlusstests

**Akteur: Mensch**  
**Ziel:** den Release-Kandidaten vor der endgültigen Dokumentation und der stabilen Produktivsetzung validieren.

## 1. Validierungstests

| Test | Ziel | Befehl | Erwartetes Ergebnis | Tatsächliches Ergebnis | Status |
|---|---|---|---|---|---|
| Normalszenario | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |
| Fehlerszenario | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |
| CLI-Optionen | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |
| Konfiguration | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |
| Berechtigungen | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |
| Abbruch | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |
| Nicht-Regression | [AUSZUFÜLLEN] | [Befehl] | [AUSZUFÜLLEN] | [AUSZUFÜLLEN] | [ ] |

## 2. Abschlusscheckliste

- [ ] Das Projekt startet korrekt.
- [ ] Die Hauptbefehle funktionieren.
- [ ] Die Fehler sind verständlich.
- [ ] Die Logs sind auswertbar.
- [ ] Es ist kein kritischer Bug vorhanden.
- [ ] Es wurde keine Regression festgestellt.
- [ ] Die Leistung ist akzeptabel.
- [ ] Die Sicherheit entspricht den Anforderungen.
- [ ] Die Version ist identifizierbar.
- [ ] Ein Rollback ist möglich.

## Validierung von Phase 8

**Entscheidung:** [ ] Release-Kandidat / [ ] Zurück zur Korrektur  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 9 — Dokumentationsentwurf

**Akteur: Mensch**  
**Ziel:** die Software so dokumentieren, wie sie tatsächlich funktioniert.

## 1. Zu erstellende Dokumente

| Dokument | Ziel | Status |
|---|---|---|
| `README.md` | Vorstellung und Schnellstart | [ ] |
| `USER_GUIDE.md` | Ausführliche, verständliche Nutzung | [ ] |
| `TECHNICAL_GUIDE.md` | Architektur und interne Funktionsweise | [ ] |
| `DEVELOPER_GUIDE.md` | Umgebung, Tests, Konventionen | [ ] |
| `INSTALLATION.md` | Voraussetzungen und Installation | [ ] |
| `SECURITY.md` | Risiken, Berechtigungen, bewährte Praktiken | [ ] |
| `TROUBLESHOOTING.md` | Häufige Fehler und Lösungen | [ ] |
| `CHANGELOG.md` | Versionsverlauf | [ ] |

## 2. Zu prüfende Inhalte

- [ ] Jeder Befehl ist dokumentiert.
- [ ] Jede Option ist dokumentiert.
- [ ] Jede Konfigurationsdatei ist dokumentiert.
- [ ] Jede Abhängigkeit ist dokumentiert.
- [ ] Jeder häufige Fehler ist erklärt.
- [ ] Die Grenzen sind explizit.
- [ ] Die Beispiele sind testbar.

## Validierung von Phase 9

**Status:** [ ] Entwurf / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 10 — Aufbereitung und endgültige Dokumentation

**Akteur: KI**  
**Ziel:** die Dokumentation vervollständigen, strukturieren und vereinheitlichen, ohne Verhalten zu erfinden, das im Code nicht vorhanden ist.

## 1. Prompt zur Vervollständigung der Dokumentation

```text
Hier sind die Entwürfe der Dokumentation.

1. Prüfe die Übereinstimmung mit dem tatsächlichen Code.
2. Erkenne nicht dokumentierte Funktionen.
3. Erkenne nicht dokumentierte CLI-Optionen.
4. Erkenne nicht erklärte Fehlermeldungen.
5. Erkenne fehlende Abhängigkeiten.
6. Erkenne fehlende Installationsschritte.
7. Erkenne Widersprüche zwischen Dokumenten.
8. Verbessere Struktur und Lesbarkeit.
9. Vervollständige fehlende Abschnitte.
10. Ändere kein beschriebenes Verhalten ohne Nachweis im Code.
```

## 2. Prüfungen der Dokumentation

| Prüfung | Status | Kommentar |
|---|---|---|
| Übereinstimmung mit dem Code | [ ] | [AUSZUFÜLLEN] |
| Befehle dokumentiert | [ ] | [AUSZUFÜLLEN] |
| Optionen dokumentiert | [ ] | [AUSZUFÜLLEN] |
| Exit-Codes dokumentiert | [ ] | [AUSZUFÜLLEN] |
| Konfiguration dokumentiert | [ ] | [AUSZUFÜLLEN] |
| Abhängigkeiten dokumentiert | [ ] | [AUSZUFÜLLEN] |
| Häufige Fehler dokumentiert | [ ] | [AUSZUFÜLLEN] |
| Testbare Beispiele | [ ] | [AUSZUFÜLLEN] |
| Vereinheitlichte Struktur | [ ] | [AUSZUFÜLLEN] |

## Validierung von Phase 10

**Status:** [ ] Entwurf / [ ] Validiert  
**Validiert von:** [NAME]  
**Datum:** [JJJJ-MM-TT]

---

# Phase 11 — Endgültige Produktivsetzung

**Akteur: Mensch**  
**Ziel:** die validierte, dokumentierte und getestete Version ausrollen.

## 1. Vorbereitung

- [ ] Version in Phase 8 validiert.
- [ ] Endgültige Dokumentation in Phase 10 validiert.
- [ ] Backup der bestehenden Umgebung durchgeführt.
- [ ] Rollback-Verfahren verfügbar.
- [ ] Versions-Tag erstellt.

Befehle:

```bash
git tag -a v[VERSION] -m "Stabile Version [VERSION]"
git push origin v[VERSION]
```

## 2. Paketierung

```bash
python -m build
```

Prüfung:

```bash
sha256sum dist/*
```

## 3. Bereitstellung

| Schritt | Befehl / Aktion | Status | Kommentar |
|---:|---|---|---|
| 1 | Backup | [ ] | [AUSZUFÜLLEN] |
| 2 | Getaggte Version ausrollen | [ ] | [AUSZUFÜLLEN] |
| 3 | Dienst prüfen | [ ] | [AUSZUFÜLLEN] |
| 4 | Logs prüfen | [ ] | [AUSZUFÜLLEN] |
| 5 | Hauptbefehl testen | [ ] | [AUSZUFÜLLEN] |
| 6 | Ausgerollte Version dokumentieren | [ ] | [AUSZUFÜLLEN] |

## 4. Prüfungen nach der Bereitstellung

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] Der Dienst ist aktiv.
- [ ] In den Logs erscheint kein kritischer Fehler.
- [ ] Der Hauptbefehl antwortet.
- [ ] Die ausgerollte Version entspricht dem validierten Tag.
- [ ] Der Rollback ist dokumentiert und testbar.

## Endgültige Validierung

| Feld | Wert |
|---|---|
| Ausgerollte Version | [VERSION] |
| Datum der Produktivsetzung | [JJJJ-MM-TT] |
| Umgebung | [AUSZUFÜLLEN] |
| Verantwortlich | [NAME] |
| Rollback getestet | [Ja / Nein] |
| Endstatus | [In Produktion / Fehlschlag / Rollback] |

---

# Änderungsverlauf des Dokuments

| Datum | Version | Autor | Änderung |
|---|---|---|---|
| [JJJJ-MM-TT] | 0.1 | [NAME] | Erstellung der Vorlage |
| [JJJJ-MM-TT] | [VERSION] | [NAME] | [AUSZUFÜLLEN] |
