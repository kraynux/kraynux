# Ontwikkelprocedure — [PROJECT_NAME]

**Talen:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Veld | Waarde |
|---|---|
| Project | [PROJECT_NAME] |
| Doelversie | [TARGET_VERSION] |
| Verantwoordelijke | [NAAM] |
| Aanmaakdatum | [JJJJ-MM-DD] |
| Laatste bijwerking | [JJJJ-MM-DD] |
| Algemene status | Concept / In uitvoering / Gevalideerd / In productie |
| Doelomgeving | [Linux / Debian / Server / Werkstation] |
| Hoofdtaal | [Python / Bash / Lua / Anders] |
| Repository | [URL_OF_PAD] |

## Overkoepelende regels

- [ ] Er wordt geen code geschreven vóór de validatie van het definitieve plan.
- [ ] Elke belangrijke beslissing wordt gedocumenteerd.
- [ ] Elke anomalie wordt vastgelegd.
- [ ] Elke correctie wordt getest.
- [ ] Elke gedragswijziging wordt gedocumenteerd.
- [ ] Back-ups worden gemaakt vóór elke ingreep in productie.
- [ ] De AI analyseert en stelt voor; de mens beslist, valideert en rolt uit.
- [ ] De code blijft in lijn met de definitieve documentatie.

## Algemene opvolging van de fasen

| Fase | Actor | Belangrijkste resultaat | Status | Validatiedatum |
|---:|---|---|---|---|
| 1 | Mens | Behoeften en ontwerp | [ ] | [JJJJ-MM-DD] |
| 2 | Mens | Architectuurschets en voorlopig plan | [ ] | [JJJJ-MM-DD] |
| 3 | AI | Analyse, neveneffecten, definitief plan | [ ] | [JJJJ-MM-DD] |
| 4 | Mens | Kern van het project gecodeerd | [ ] | [JJJJ-MM-DD] |
| 5 | AI | Code-audit, correcties en tests | [ ] | [JJJJ-MM-DD] |
| 6 | Mens | Echte tests in productie | [ ] | [JJJJ-MM-DD] |
| 7 | AI | Correctieplan en definitieve codering | [ ] | [JJJJ-MM-DD] |
| 8 | Mens | Eindtests | [ ] | [JJJJ-MM-DD] |
| 9 | Mens | Concept van de documentatie | [ ] | [JJJJ-MM-DD] |
| 10 | AI | Definitieve documentatie | [ ] | [JJJJ-MM-DD] |
| 11 | Mens | Ingebruikname in productie | [ ] | [JJJJ-MM-DD] |

---

# Fase 1 — Reflectie, behoeften, gebruik en ontwerp

**Actor: Mens**  
**Doel:** het probleem, de gebruikers, het echte gebruik, de beperkingen en de grenzen van het project vastleggen.

## 1. Oorspronkelijk probleem

- Vastgesteld probleem: [IN TE VULLEN]
- Huidige situatie: [IN TE VULLEN]
- Gevolg van het probleem: [IN TE VULLEN]
- Doel van het project: [IN TE VULLEN]

## 2. Doelgebruikers

| Gebruiker | Belangrijkste behoefte | Technisch niveau | Beoogd gebruik |
|---|---|---|---|
| [Gebruiker 1] | [IN TE VULLEN] | [Beginner / Technisch / Expert] | [IN TE VULLEN] |
| [Gebruiker 2] | [IN TE VULLEN] | [Beginner / Technisch / Expert] | [IN TE VULLEN] |

## 3. Gebruiksscenario's

### Nominaal scenario

- Context: [IN TE VULLEN]
- Actie van de gebruiker: [IN TE VULLEN]
- Verwacht resultaat: [IN TE VULLEN]

### Grensscenario

- Context: [IN TE VULLEN]
- Actie van de gebruiker: [IN TE VULLEN]
- Verwacht resultaat: [IN TE VULLEN]

### Foutscenario

- Context: [IN TE VULLEN]
- Actie van de gebruiker: [IN TE VULLEN]
- Verwacht resultaat: [IN TE VULLEN]

### Verboden of gevaarlijk scenario

- Context: [IN TE VULLEN]
- Verwacht gedrag: [Weigering / Waarschuwing / Blokkering / Logging]
- Rechtvaardiging: [IN TE VULLEN]

## 4. Functies

### Verplicht

- [ ] [Functie 1]
- [ ] [Functie 2]
- [ ] [Functie 3]

### Nuttig maar uitstelbaar

- [ ] [Functie 1]
- [ ] [Functie 2]

### Optioneel

- [ ] [Functie 1]

### Uitgesloten

- [ ] [Uitgesloten functie]
- Rechtvaardiging: [IN TE VULLEN]

## 5. Beperkingen

| Domein | Beperking | Prioriteit |
|---|---|---|
| Systeem | [Linux / Debian / Versie] | [Hoog / Middel / Laag] |
| Taal | [Python / Bash / Lua] | [Hoog / Middel / Laag] |
| Afhankelijkheden | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Prestaties | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Beveiliging | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Compatibiliteit | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Onderhoud | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Uitrol | [IN TE VULLEN] | [Hoog / Middel / Laag] |

## 6. Vastgestelde risico's

| Risico | Impact | Waarschijnlijkheid | Preventieve maatregel |
|---|---|---|---|
| [Risico 1] | [Laag / Middel / Hoog] | [Laag / Middel / Hoog] | [IN TE VULLEN] |
| [Risico 2] | [Laag / Middel / Hoog] | [Laag / Middel / Hoog] | [IN TE VULLEN] |

## 7. Genomen beslissingen

| ID | Beslissing | Rechtvaardiging | Datum |
|---:|---|---|---|
| D-001 | [IN TE VULLEN] | [IN TE VULLEN] | [JJJJ-MM-DD] |
| D-002 | [IN TE VULLEN] | [IN TE VULLEN] | [JJJJ-MM-DD] |

## 8. Open vragen

- [ ] [Vraag 1]
- [ ] [Vraag 2]

## Validatie van fase 1

- [ ] Het probleem is duidelijk geformuleerd.
- [ ] De gebruikers zijn geïdentificeerd.
- [ ] De belangrijkste gebruiksscenario's zijn beschreven.
- [ ] De verplichte functies zijn opgesomd.
- [ ] De grenzen van het project zijn expliciet.
- [ ] De technische beperkingen zijn bekend.
- [ ] De belangrijkste risico's zijn geïdentificeerd.

**Status:** [ ] Concept / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 2 — Schets, hoofdcomponenten en ontwikkelplan

**Actor: Mens**  
**Doel:** de behoeften omzetten in een logische architectuur en een uitvoerbaar ontwikkelplan.

## 1. Hoofdcomponenten

| Component | Verantwoordelijkheid | Mag niet | Prioriteit |
|---|---|---|---|
| Interface / CLI | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Bedrijfskern | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Configuratie | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Datamodellen | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Services | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Opslag | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Export | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Logs | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Beveiliging | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| Tests | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |

## 2. Hoofdflow

```text
[Invoer van de gebruiker]
    → [Interface]
    → [Validatie]
    → [Bedrijfskern]
    → [Services / Modules]
    → [Resultaat]
    → [Uitvoer / Opslag / Logs]
```

## 3. Geplande modules

| Module | Rol | Afhankelijkheden | Prioriteit |
|---|---|---|---|
| [module_1] | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| [module_2] | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |
| [module_3] | [IN TE VULLEN] | [IN TE VULLEN] | [Hoog / Middel / Laag] |

## 4. Voorlopige mappenstructuur

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

## 5. Geplande afhankelijkheden

| Afhankelijkheid | Gebruik | Minimale versie | Rechtvaardiging |
|---|---|---|---|
| [Afhankelijkheid 1] | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |
| [Afhankelijkheid 2] | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |

## 6. Opdeling van de ontwikkeling

| Fase | Inhoud | Prioriteit | Schatting |
|---:|---|---|---|
| 1 | Basis: structuur, configuratie, fouten, logs | [Hoog / Middel] | [Duur] |
| 2 | Modellen en contracten | [Hoog / Middel] | [Duur] |
| 3 | Bedrijfskern | [Hoog / Middel] | [Duur] |
| 4 | Interface / CLI | [Hoog / Middel] | [Duur] |
| 5 | Opslag / export | [Hoog / Middel] | [Duur] |
| 6 | Tests | [Hoog / Middel] | [Duur] |
| 7 | Documentatie en packaging | [Hoog / Middel] | [Duur] |

## Validatie van fase 2

- [ ] De hoofdcomponenten zijn geïdentificeerd.
- [ ] Elke module heeft een duidelijke verantwoordelijkheid.
- [ ] De belangrijkste flows zijn beschreven.
- [ ] De voorlopige mappenstructuur is vastgelegd.
- [ ] De belangrijkste afhankelijkheden zijn geïdentificeerd.
- [ ] De ontwikkelvolgorde is vastgelegd.
- [ ] Er is nog geen ontwikkeling gestart.

**Status:** [ ] Concept / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 3 — AI-analyse, neveneffecten en definitief plan

**Actor: AI**  
**Doel:** de door de mens opgestelde documenten analyseren, de risico's vaststellen en een uitvoerbaar definitief plan opstellen.

## 1. Geanalyseerde documenten

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Ander document]

## 2. AI-analyseprompt

```text
Analyseer dit project zonder code te schrijven.

1. Spoor de inconsistenties op.
2. Spoor de ontbrekende functies op.
3. Spoor de verkeerd geplaatste verantwoordelijkheden op.
4. Identificeer mogelijke neveneffecten.
5. Identificeer de foutgevallen.
6. Identificeer de beveiligingsrisico's.
7. Identificeer compatibiliteitsproblemen.
8. Stel een robuustere projectstructuur voor.
9. Stel een definitief ontwikkelplan voor.
10. Geef aan welke punten onder menselijke beslissing moeten blijven.
```

## 3. Opgespoorde inconsistenties

| ID | Beschrijving | Impact | Voorstel | Menselijke beslissing |
|---:|---|---|---|---|
| A-001 | [IN TE VULLEN] | [Laag / Middel / Hoog] | [IN TE VULLEN] | [Aanvaard / Geweigerd / Uitgesteld] |
| A-002 | [IN TE VULLEN] | [Laag / Middel / Hoog] | [IN TE VULLEN] | [Aanvaard / Geweigerd / Uitgesteld] |

## 4. Vastgestelde neveneffecten

| ID | Neveneffect | Trigger | Impact | Preventie | Status |
|---:|---|---|---|---|---|
| SE-001 | [IN TE VULLEN] | [IN TE VULLEN] | [Laag / Middel / Hoog] | [IN TE VULLEN] | [Open / Behandeld / Aanvaard] |
| SE-002 | [IN TE VULLEN] | [IN TE VULLEN] | [Laag / Middel / Hoog] | [IN TE VULLEN] | [Open / Behandeld / Aanvaard] |

## 5. Te voorziene foutgevallen

| Geval | Verwacht gedrag | Verwachte melding / log | Bijbehorende test |
|---|---|---|---|
| Ontbrekend bestand | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |
| Toegang geweigerd | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |
| Netwerk niet beschikbaar | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |
| Ongeldige invoer | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |
| Onderbreking door de gebruiker | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |
| Beschadigde gegevens | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] |

## 6. Beveiligingsrisico's

| Risico | Scenario | Maatregel | Prioriteit |
|---|---|---|---|
| [Risico 1] | [IN TE VULLEN] | [IN TE VULLEN] | [P0 / P1 / P2] |
| [Risico 2] | [IN TE VULLEN] | [IN TE VULLEN] | [P0 / P1 / P2] |

## 7. Definitief ontwikkelplan

| Fase | Doel | Resultaten | Afrondingscriteria | Afhankelijkheden |
|---:|---|---|---|---|
| 1 | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [Geen] |
| 2 | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [Fase 1] |
| 3 | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [Fase 2] |

## Validatie van fase 3

- [ ] De inconsistenties zijn behandeld of gedocumenteerd.
- [ ] De neveneffecten zijn geïdentificeerd.
- [ ] De foutgevallen zijn voorzien.
- [ ] De beveiligingsrisico's zijn behandeld.
- [ ] Het definitieve plan is door de mens gevalideerd.
- [ ] De definitieve beslissingen zijn vastgelegd.

**Status:** [ ] Concept / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 4 — Codering van de projectkern

**Actor: Mens**  
**Doel:** de functionele kern ontwikkelen zonder functies buiten de scope toe te voegen.

## 1. Scope van de codering

- [ ] Projectstructuur
- [ ] Virtuele omgeving
- [ ] Afhankelijkheden
- [ ] Configuratie
- [ ] Datamodellen
- [ ] Exceptions
- [ ] Logging
- [ ] Bedrijfsservices
- [ ] Bedrijfskern
- [ ] Unittests
- [ ] CLI / interface
- [ ] Integratie

## 2. Volgorde van implementatie

| Volgorde | Element | Bestand / module | Status | Commit |
|---:|---|---|---|---|
| 1 | [Element] | [pad] | [ ] | [hash] |
| 2 | [Element] | [pad] | [ ] | [hash] |
| 3 | [Element] | [pad] | [ ] | [hash] |

## 3. Commitregels

- Eén commit = één enkele bedoeling.
- Functie, correctie en refactoring niet mengen.
- Aanbevolen bericht:

```text
[type]: [korte beschrijving]

[type] = feat, fix, refactor, test, docs, chore
```

Voorbeeld:

```text
feat: laden en valideren van de configuratie toevoegen
```

## 4. Eerste tests

| Test | Doel | Commando | Verwacht resultaat | Status |
|---|---|---|---|---|
| [Test 1] | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [ ] |
| [Test 2] | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [ ] |

## Validatie van fase 4

- [ ] De bedrijfskern werkt.
- [ ] De belangrijkste invoer wordt gevalideerd.
- [ ] De belangrijkste fouten worden afgehandeld.
- [ ] De unittests slagen.
- [ ] Het project start in basismodus.
- [ ] Er is geen functie buiten de scope toegevoegd.

**Status:** [ ] In uitvoering / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 5 — Code-analyse, correctie en tests door de AI

**Actor: AI**  
**Doel:** gebreken, neveneffecten en risico's opsporen vóór de echte tests.

## 1. AI-auditprompt

```text
Analyseer de code zonder hem volledig te herschrijven.

1. Controleer de conformiteit met het ontwikkelplan.
2. Spoor waarschijnlijke bugs op.
3. Spoor neveneffecten op.
4. Spoor resourcelekken op.
5. Spoor niet-afgehandelde fouten op.
6. Spoor niet-gevalideerde invoer op.
7. Spoor beveiligingsproblemen op.
8. Spoor prestatieproblemen op.
9. Spoor dode code op.
10. Spoor verkeerd geplaatste verantwoordelijkheden op.
11. Stel gerichte correcties voor.
12. Stel ontbrekende tests voor.
```

## 2. Resultaten van de audit

| ID | Bestand / functie | Vaststelling | Ernst | Voorgestelde correctie | Status |
|---:|---|---|---|---|---|
| C-001 | [pad] | [IN TE VULLEN] | [Kritiek / Ernstig / Gering] | [IN TE VULLEN] | [Open / Gecorrigeerd / Gevalideerd] |
| C-002 | [pad] | [IN TE VULLEN] | [Kritiek / Ernstig / Gering] | [IN TE VULLEN] | [Open / Gecorrigeerd / Gevalideerd] |

## 3. Toegevoegde tests

| Test | Doel | Testbestand | Status |
|---|---|---|---|
| [Test 1] | [IN TE VULLEN] | [pad] | [ ] |
| [Test 2] | [IN TE VULLEN] | [pad] | [ ] |

## Validatie van fase 5

- [ ] De kritieke bugs zijn gecorrigeerd.
- [ ] De neveneffecten zijn behandeld of gedocumenteerd.
- [ ] De unittests slagen.
- [ ] De integratietests slagen.
- [ ] De code is conform het definitieve plan.
- [ ] De correcties zijn stapsgewijs toegepast.

**Status:** [ ] In uitvoering / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 6 — Praktijkstudie en tests in productie

**Actor: Mens**  
**Doel:** de software onder echte omstandigheden valideren en alle anomalieën vastleggen.

## 1. Testomgeving

| Element | Waarde |
|---|---|
| Machine | [IN TE VULLEN] |
| Systeem | [IN TE VULLEN] |
| Softwareversie | [IN TE VULLEN] |
| Omgeving | [Gecontroleerde productie / Preproductie / Echte server] |
| Back-up gemaakt | [Ja / Nee] |
| Datum van de back-up | [JJJJ-MM-DD] |
| Rollbackmethode | [IN TE VULLEN] |

## 2. Geteste scenario's

| ID | Scenario | Commando | Verwacht resultaat | Verkregen resultaat | Status |
|---:|---|---|---|---|---|
| T-001 | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [OK / KO / Gedeeltelijk] |
| T-002 | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [OK / KO / Gedeeltelijk] |

## 3. Observatieraster

| Domein | Geobserveerd element | Resultaat | Opmerking |
|---|---|---|---|
| Functioneel | Verwachte functie | [OK / KO] | [IN TE VULLEN] |
| Interface | Duidelijkheid van de commando's | [OK / KO] | [IN TE VULLEN] |
| Prestaties | Uitvoeringstijd | [OK / KO] | [IN TE VULLEN] |
| Stabiliteit | Geen onverwachte crash | [OK / KO] | [IN TE VULLEN] |
| Fouten | Begrijpelijkheid van de meldingen | [OK / KO] | [IN TE VULLEN] |
| Logs | Kwaliteit en nut | [OK / KO] | [IN TE VULLEN] |
| Beveiliging | Veilig gedrag | [OK / KO] | [IN TE VULLEN] |
| Compatibiliteit | Werking op het echte doel | [OK / KO] | [IN TE VULLEN] |
| Esthetiek | Leesbaarheid van de uitvoer | [OK / KO] | [IN TE VULLEN] |
| Echt gebruik | Vlotheid van de workflow | [OK / KO] | [IN TE VULLEN] |

## 4. Anomalieënlogboek

| ID | Datum | Ernst | Beschrijving | Logs | Hypothese | Voorgestelde correctie | Status |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [JJJJ-MM-DD] | [Kritiek / Ernstig / Gering / Esthetisch] | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [Open / Gecorrigeerd / Gevalideerd] |
| BUG-002 | [JJJJ-MM-DD] | [Kritiek / Ernstig / Gering / Esthetisch] | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [IN TE VULLEN] | [Open / Gecorrigeerd / Gevalideerd] |

## Validatie van fase 6

- [ ] Alle kritieke scenario's zijn getest.
- [ ] De bugs zijn vastgelegd.
- [ ] De gebruiksvriendelijkheidsproblemen zijn vastgelegd.
- [ ] De esthetische problemen zijn vastgelegd.
- [ ] Geen enkele kritieke blokkerende bug wordt genegeerd.

**Status:** [ ] In uitvoering / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 7 — Verbeterplan, correcties en definitieve codering

**Actor: AI**  
**Doel:** anomalieën omzetten in geprioriteerde correcties en daarna de nodige codewijzigingen toepassen.

## 1. Prompt voor de analyse van anomalieën

```text
Hier is het logboek van de productietests.

1. Rangschik de anomalieën op ernst.
2. Groepeer samenhangende anomalieën.
3. Identificeer de waarschijnlijke oorzaken.
4. Stel voor elke anomalie een minimale correctie voor.
5. Geef de regressierisico's aan.
6. Stel toe te voegen tests voor.
7. Stel verbeteringen in gebruiksvriendelijkheid voor.
8. Stel esthetische verbeteringen voor.
9. Wijzig alleen wat nodig is.
10. Behoud het gevalideerde gedrag.
```

## 2. Prioritering van de anomalieën

| Prioriteit | Type | Betrokken anomalieën | Behandeling |
|---|---|---|---|
| P0 | Crash, gegevensverlies, kwetsbaarheid | [BUG-XXX] | Onmiddellijke correctie |
| P1 | Onjuiste functie | [BUG-XXX] | Correctie vóór de eindvalidatie |
| P2 | Slechte gebruikerservaring | [BUG-XXX] | Correctie indien redelijk |
| P3 | Esthetiek, melding, formaat | [BUG-XXX] | Correctie of uitstel |
| P4 | Toekomstige verbetering | [BUG-XXX] | Backlog |

## 3. Toegepaste correcties

| ID | Anomalie | Correctie | Gewijzigde bestanden | Toegevoegde tests | Regressierisico | Status |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [IN TE VULLEN] | [pad] | [pad] | [Laag / Middel / Hoog] | [Toegepast / Gevalideerd] |
| FIX-002 | [BUG-XXX] | [IN TE VULLEN] | [pad] | [pad] | [Laag / Middel / Hoog] | [Toegepast / Gevalideerd] |

## Validatie van fase 7

- [ ] Elke anomalie heeft een duidelijke status.
- [ ] De correcties worden volgens prioriteit toegepast.
- [ ] De non-regressietests slagen.
- [ ] Het gevalideerde gedrag blijft behouden.
- [ ] Elke correctie is gedocumenteerd.

**Status:** [ ] In uitvoering / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 8 — Eindtests

**Actor: Mens**  
**Doel:** de kandidaat-release valideren vóór de definitieve documentatie en de stabiele ingebruikname in productie.

## 1. Validatietests

| Test | Doel | Commando | Verwacht resultaat | Verkregen resultaat | Status |
|---|---|---|---|---|---|
| Nominaal scenario | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |
| Foutscenario | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |
| CLI-opties | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |
| Configuratie | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |
| Rechten | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |
| Onderbreking | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |
| Non-regressie | [IN TE VULLEN] | [commando] | [IN TE VULLEN] | [IN TE VULLEN] | [ ] |

## 2. Eindchecklist

- [ ] Het project start correct.
- [ ] De belangrijkste commando's werken.
- [ ] De fouten zijn begrijpelijk.
- [ ] De logs zijn bruikbaar.
- [ ] Er is geen kritieke bug aanwezig.
- [ ] Er is geen regressie vastgesteld.
- [ ] De prestaties zijn aanvaardbaar.
- [ ] De beveiliging voldoet aan de eisen.
- [ ] De versie is identificeerbaar.
- [ ] Een rollback is mogelijk.

## Validatie van fase 8

**Beslissing:** [ ] Kandidaat-release / [ ] Terug naar correctie  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 9 — Concept van de documentatie

**Actor: Mens**  
**Doel:** de software documenteren zoals hij werkelijk werkt.

## 1. Op te stellen documenten

| Document | Doel | Status |
|---|---|---|
| `README.md` | Voorstelling en snelle start | [ ] |
| `USER_GUIDE.md` | Gedetailleerd en toegankelijk gebruik | [ ] |
| `TECHNICAL_GUIDE.md` | Architectuur en interne werking | [ ] |
| `DEVELOPER_GUIDE.md` | Omgeving, tests, conventies | [ ] |
| `INSTALLATION.md` | Vereisten en installatie | [ ] |
| `SECURITY.md` | Risico's, rechten, goede praktijken | [ ] |
| `TROUBLESHOOTING.md` | Veelvoorkomende fouten en oplossingen | [ ] |
| `CHANGELOG.md` | Versiegeschiedenis | [ ] |

## 2. Te controleren inhoud

- [ ] Elk commando is gedocumenteerd.
- [ ] Elke optie is gedocumenteerd.
- [ ] Elk configuratiebestand is gedocumenteerd.
- [ ] Elke afhankelijkheid is gedocumenteerd.
- [ ] Elke veelvoorkomende fout is uitgelegd.
- [ ] De beperkingen zijn expliciet.
- [ ] De voorbeelden zijn testbaar.

## Validatie van fase 9

**Status:** [ ] Concept / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 10 — Opmaak en definitieve documentatie

**Actor: AI**  
**Doel:** de documentatie aanvullen, structureren en harmoniseren zonder gedrag te verzinnen dat niet in de code zit.

## 1. Prompt voor het aanvullen van de documentatie

```text
Hier zijn de concepten van de documentatie.

1. Controleer de samenhang met de echte code.
2. Spoor niet-gedocumenteerde functies op.
3. Spoor niet-gedocumenteerde CLI-opties op.
4. Spoor niet-uitgelegde foutmeldingen op.
5. Spoor ontbrekende afhankelijkheden op.
6. Spoor ontbrekende installatiestappen op.
7. Spoor inconsistenties tussen documenten op.
8. Verbeter de structuur en de leesbaarheid.
9. Vul ontbrekende secties aan.
10. Wijzig geen beschreven gedrag zonder bewijs in de code.
```

## 2. Controles van de documentatie

| Controle | Status | Opmerking |
|---|---|---|
| Samenhang met de code | [ ] | [IN TE VULLEN] |
| Commando's gedocumenteerd | [ ] | [IN TE VULLEN] |
| Opties gedocumenteerd | [ ] | [IN TE VULLEN] |
| Exitcodes gedocumenteerd | [ ] | [IN TE VULLEN] |
| Configuratie gedocumenteerd | [ ] | [IN TE VULLEN] |
| Afhankelijkheden gedocumenteerd | [ ] | [IN TE VULLEN] |
| Veelvoorkomende fouten gedocumenteerd | [ ] | [IN TE VULLEN] |
| Testbare voorbeelden | [ ] | [IN TE VULLEN] |
| Geharmoniseerde structuur | [ ] | [IN TE VULLEN] |

## Validatie van fase 10

**Status:** [ ] Concept / [ ] Gevalideerd  
**Gevalideerd door:** [NAAM]  
**Datum:** [JJJJ-MM-DD]

---

# Fase 11 — Definitieve ingebruikname in productie

**Actor: Mens**  
**Doel:** de gevalideerde, gedocumenteerde en geteste versie uitrollen.

## 1. Voorbereiding

- [ ] Versie gevalideerd in fase 8.
- [ ] Definitieve documentatie gevalideerd in fase 10.
- [ ] Back-up van de bestaande omgeving gemaakt.
- [ ] Rollbackprocedure beschikbaar.
- [ ] Versietag aangemaakt.

Commando's:

```bash
git tag -a v[VERSION] -m "Stabiele versie [VERSION]"
git push origin v[VERSION]
```

## 2. Packaging

```bash
python -m build
```

Controle:

```bash
sha256sum dist/*
```

## 3. Uitrol

| Stap | Commando / actie | Status | Opmerking |
|---:|---|---|---|
| 1 | Back-up | [ ] | [IN TE VULLEN] |
| 2 | De getagde versie uitrollen | [ ] | [IN TE VULLEN] |
| 3 | De service controleren | [ ] | [IN TE VULLEN] |
| 4 | De logs controleren | [ ] | [IN TE VULLEN] |
| 5 | Het hoofdcommando testen | [ ] | [IN TE VULLEN] |
| 6 | De uitgerolde versie documenteren | [ ] | [IN TE VULLEN] |

## 4. Controles na de uitrol

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] De service is actief.
- [ ] Er verschijnt geen kritieke fout in de logs.
- [ ] Het hoofdcommando reageert.
- [ ] De uitgerolde versie komt overeen met de gevalideerde tag.
- [ ] De rollback is gedocumenteerd en testbaar.

## Eindvalidatie

| Veld | Waarde |
|---|---|
| Uitgerolde versie | [VERSION] |
| Datum van ingebruikname | [JJJJ-MM-DD] |
| Omgeving | [IN TE VULLEN] |
| Verantwoordelijke | [NAAM] |
| Rollback getest | [Ja / Nee] |
| Eindstatus | [In productie / Mislukt / Rollback] |

---

# Wijzigingsgeschiedenis van het document

| Datum | Versie | Auteur | Wijziging |
|---|---|---|---|
| [JJJJ-MM-DD] | 0.1 | [NAAM] | Aanmaak van het sjabloon |
| [JJJJ-MM-DD] | [VERSION] | [NAAM] | [IN TE VULLEN] |
