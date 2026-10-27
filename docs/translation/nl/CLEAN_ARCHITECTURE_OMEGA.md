# Projectarchitectuur — Clean Architecture

**Talen:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Dit document legt uit hoe het project is georganiseerd, waarom voor deze organisatie is gekozen en wat elke map bevat. Het is bedoeld voor bezoekers die willen begrijpen hoe de applicatie werkt én voor ontwikkelaars die eraan willen bijdragen of het willen onderhouden.

De applicatie volgt een **Clean Architecture**: de kern van de software is geïsoleerd van technische details, gebruikersinterfaces en externe afhankelijkheden. Door deze scheiding is het project eenvoudiger te lezen, te testen, te onderhouden en verder te ontwikkelen.

---

## 1. Algemeen principe

De applicatie is opgedeeld in lagen, elk met een duidelijke rol.

Het centrale idee is eenvoudig:

```text
De interface vraagt om een actie.
De applicatie orkestreert deze actie.
Het domein past de bedrijfsregels toe.
De ports bepalen wat de applicatie nodig heeft.
De infrastructuur levert de concrete implementaties.
```

Daardoor is de belangrijke logica van het project niet rechtstreeks afhankelijk van:

- de terminal;
- de grafische interface;
- een database;
- het netwerk;
- het bestandssysteem;
- een externe bibliotheek;
- een systeemtool.

Dankzij deze onafhankelijkheid kan een deel van de software worden vervangen zonder de rest te herschrijven.

---

## 2. Overzicht

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, levenscyclus en dependency injection
        ├── core/             Overkoepelende capabilities, enums en exceptions
        ├── domain/           Pure bedrijfslogica
        ├── application/      Use cases: commands en queries
        ├── infrastructure/   Backends, opslag, exports, logs, systeemprobes…
        ├── ports/            Protocol- / ABC-contracten
        ├── interfaces/       CLI en TUI
        ├── plugins/          Ingebouwde extensies
        └── shared/           Parsing, netwerk, opmaak en overkoepelende hulpmiddelen
```

---

## 3. Afhankelijkheidsschema

Afhankelijkheden moeten altijd dezelfde richting volgen:

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

In de praktijk:

- `interfaces/` mag `application/` aanroepen.
- `application/` mag `domain/` aanroepen en de contracten uit `ports/` gebruiken.
- `domain/` is niet afhankelijk van `application/`, `infrastructure/` of `interfaces/`.
- `infrastructure/` implementeert de contracten uit `ports/`.
- `app/` voegt de lagen samen en levert de benodigde afhankelijkheden.

Kernregel:

> Het domein kent de infrastructuur nooit.  
> De infrastructuur kent de ports, maar het domein kent de infrastructuur niet.

---

## 4. De map `app/`

### Rol

De map `app/` is het **assemblagepunt** van de applicatie.

Ze bevat:

- het opstarten van de applicatie;
- de levenscyclus;
- de dependency-injectioncontainer;
- het opbouwen van de objecten die nodig zijn voor de werking;
- de keuze van de concrete implementaties;
- de initialisatie van de configuratie;
- de koppeling tussen de lagen.

### Voorbeelden van verantwoordelijkheden

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Bestand | Rol |
|---|---|
| `bootstrap.py` | Start de applicatie en kiest de interface die wordt gestart |
| `container.py` | Maakt en koppelt de afhankelijkheden |
| `lifecycle.py` | Beheert opstarten, afsluiten en opruimen |

### Regel

`app/` bevat geen bedrijfslogica.

Ze beslist niet:

- wat een bedrijfsregel is;
- hoe een gegeven berekend moet worden;
- hoe een verzoek geanalyseerd moet worden;
- hoe een bestand geëxporteerd moet worden.

Ze voegt alleen de bestaande componenten samen.

---

## 5. De map `core/`

### Rol

De map `core/` bevat het **overkoepelende vocabulaire** van het project.

Ze groepeert elementen die door meerdere lagen worden gedeeld, maar die op zichzelf geen bedrijfsregels zijn.

Ze kan bevatten:

- capabilities;
- enumeraties;
- constanten;
- overkoepelende exceptions;
- gemeenschappelijke types;
- platforminformatie;
- definities van niveaus of toestanden.

### Voorbeeld

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Bestand | Rol |
|---|---|
| `capabilities.py` | Beschrijft de beschikbare of activeerbare capabilities |
| `constants.py` | Bevat de constanten van het project |
| `enums.py` | Definieert mogelijke toestanden, types of niveaus |
| `exceptions.py` | Definieert overkoepelende fouten |

### Regel

`core/` moet licht en stabiel blijven.

Ze mag niet bevatten:

- complexe bedrijfslogica;
- netwerkaanroepen;
- schijftoegang;
- gebruikersinterfacecode;
- directe afhankelijkheden van externe bibliotheken.

---

## 6. De map `domain/`

### Rol

De map `domain/` is het **hart van het project**.

Ze bevat de pure bedrijfslogica: de regels, concepten en berekeningen die werkelijk bepalen wat de applicatie doet.

Ze kan bevatten:

- entiteiten;
- value objects;
- policies;
- bedrijfsregels;
- domeinservices;
- berekeningen;
- bedrijfsvalidaties;
- bedrijfsdatamodellen.

### Voorbeeld

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Element | Rol |
|---|---|
| Entiteit | Bedrijfsobject met een identiteit |
| Value object | Onveranderlijke en gevalideerde waarde |
| Policy | Herbruikbare bedrijfsregel |
| Domeinservice | Bedrijfslogica die niet bij één enkele entiteit hoort |

### Strikte regels

De map `domain/`:

- heeft geen schijftoegang;
- doet geen netwerkaanroepen;
- voert geen systeemcommando's uit;
- benadert geen database;
- importeert de gebruikersinterface niet;
- importeert de infrastructuur niet;
- is niet afhankelijk van een externe technische bibliotheek als dat te vermijden is.

Het domein moet testbaar zijn zonder server, zonder bestanden, zonder netwerk en zonder interface.

---

## 7. De map `application/`

### Rol

De map `application/` orkestreert de use cases.

Ze beantwoordt de vraag:

> "Wat gebeurt er als de gebruiker om deze actie vraagt?"

Ze bevat:

- de commands;
- de queries;
- de use cases;
- de orchestrators;
- de actiehandlers;
- de coördinatie tussen het domein en de ports.

### Onderscheid commands / queries

| Type | Doel | Wijzigt gegevens |
|---|---|---|
| Command | Een actie uitvoeren | Ja |
| Query | Een gegeven lezen of berekenen | Nee |

Voorbeelden:

| Command | Query |
|---|---|
| Een configuratie toepassen | De huidige configuratie lezen |
| Een analyse starten | Het resultaat van een analyse ophalen |
| Een rapport exporteren | De beschikbare items opsommen |
| Gegevens opschonen | Een geschiedenis raadplegen |

### Voorbeeld

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

`application/` bevat geen:

- terminaluitvoer;
- Textual-interface;
- Rich-commando's;
- directe databasetoegang;
- directe aanroepen van externe tools.

Ze coördineert, maar implementeert geen technische details.

---

## 8. De map `ports/`

### Rol

De map `ports/` definieert de **contracten** die de applicatie verwacht.

Een port beschrijft **wat de applicatie nodig heeft**, zonder voor te schrijven hoe dat geïmplementeerd moet worden.

Ze bevat doorgaans:

- `Protocol`-definities;
- abstracte `ABC`-klassen;
- repository-interfaces;
- exportinterfaces;
- probe-interfaces;
- interfaces voor externe services;
- opslaginterfaces.

### Voorbeeld

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Rol |
|---|---|
| `Repository` | Gegevens lezen of opslaan |
| `Exporter` | Uitvoer in een bepaald formaat produceren |
| `Probe` | Systeem- of netwerkinformatie verzamelen |
| `Storage` | Een persistentiebackend beheren |

### Conceptueel voorbeeld

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Dit contract zegt:

> "De applicatie heeft een object nodig dat een rapport kan exporteren."

Het zegt niet:

- of de export in Markdown gebeurt;
- of de export in JSON gebeurt;
- of het bestand lokaal wordt geschreven;
- of de export via het netwerk wordt verzonden.

Die keuzes horen bij `infrastructure/`.

### Regel

Ports zijn contracten, geen implementaties.

Ze mogen niet bevatten:

- complexe bedrijfslogica;
- schijftoegang;
- netwerkaanroepen;
- concrete implementaties;
- directe afhankelijkheden van externe bibliotheken.

---

## 9. De map `infrastructure/`

### Rol

De map `infrastructure/` bevat de **concrete implementaties** van de ports.

Dit is de laag die met de buitenwereld communiceert.

Ze kan bevatten:

- bestandstoegang;
- databasetoegang;
- exports naar Markdown, JSON, CSV of andere formaten;
- logging;
- netwerkaanroepen;
- systeemprobes;
- gecontroleerde uitvoering van externe tools;
- adapters voor bibliotheken van derden;
- repository-implementaties;
- opslagimplementaties.

### Voorbeeld

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

| Element | Rol |
|---|---|
| `sqlite_repository.py` | Implementeert een repository met SQLite |
| `json_file_repository.py` | Implementeert een repository met JSON-bestanden |
| `markdown_exporter.py` | Exporteert een rapport naar Markdown |
| `json_exporter.py` | Exporteert een rapport naar JSON |
| `process_probe.py` | Verzamelt informatie over processen |
| `filesystem_probe.py` | Verzamelt informatie over het bestandssysteem |
| `structured_logger.py` | Produceert gestructureerde logs |

### Regel

`infrastructure/` is de enige laag die rechtstreeks toegang mag hebben tot:

- het bestandssysteem;
- het netwerk;
- SQLite;
- externe bibliotheken;
- systeemtools;
- subprocessen, wanneer die nodig en gecontroleerd zijn.

Deze centralisatie vergemakkelijkt:

- het testen;
- de beveiligingsaudit;
- het vervangen van een backend;
- het beperken van neveneffecten.

---

## 10. De map `interfaces/`

### Rol

De map `interfaces/` bevat de toegangspunten die zichtbaar zijn voor de gebruiker.

Ze scheidt duidelijk:

- de CLI;
- de TUI;
- eventuele toekomstige web- of API-interfaces.

### Structuur

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

| Interface | Technologie | Rol |
|---|---|---|
| `cli/` | Rich | Opdrachtregelinterface |
| `tui/` | Textual | Interactieve terminalinterface |

### CLI

De CLI is de opdrachtregelinterface.

Ze maakt het mogelijk om:

- de applicatie te starten;
- een specifieke actie uit te voeren;
- een resultaat te tonen;
- een taak te automatiseren;
- de tool in een script te integreren;
- de applicatie op afstand via SSH te gebruiken.

### TUI

De TUI is de interactieve terminalinterface.

Ze maakt het mogelijk om:

- door de functies te navigeren;
- informatie te bekijken;
- acties uit te voeren;
- resultaten te raadplegen;
- de applicatie te gebruiken zonder alle commando's te onthouden.

### Regel

Interfaces bevatten geen bedrijfslogica.

Ze:

- ontvangen een intentie van de gebruiker;
- roepen een use case aan in `application/`;
- tonen het resultaat;
- vertalen fouten naar begrijpelijke meldingen.

Ze mogen niet:

- de infrastructuur rechtstreeks aanroepen;
- subprocessen uitvoeren;
- rechtstreeks bestanden benaderen;
- bedrijfsregels bevatten;
- logica uit `application/` dupliceren.

---

## 11. De map `plugins/`

### Rol

De map `plugins/` is gereserveerd voor **ingebouwde extensies**.

Ze maakt het mogelijk functies toe te voegen zonder de kern van het project te verzwaren.

Een plugin kan bijvoorbeeld:

- een exportformaat toevoegen;
- een probe toevoegen;
- een commando toevoegen;
- een TUI-scherm toevoegen;
- een externe integratie toevoegen;
- een optionele capability toevoegen.

### Principe

Een plugin moet dezelfde regels volgen als de rest van het project:

- hij omzeilt de ports niet;
- hij wijzigt het domein niet rechtstreeks;
- hij stelt zijn functies beschikbaar via duidelijke contracten;
- hij blijft uitschakelbaar zonder de applicatie te breken.

### Mogelijke structuur

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

Een plugin is een extensie, geen achterdeur.

Hij moet de algemene architectuur respecteren en mag geen circulaire afhankelijkheden met de kern van het project veroorzaken.

---

## 12. De map `shared/`

### Rol

De map `shared/` bevat overkoepelende hulpmiddelen die niet bij het domein, de applicatie of de infrastructuur horen.

Ze groepeert herbruikbare generieke functies.

Ze kan bevatten:

- parsing;
- netwerkhulpmiddelen;
- opmaak;
- tekstbewerking;
- datumhelpers;
- padhelpers;
- generieke validatiehulpmiddelen;
- serialisatiehelpers.

### Voorbeeld

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Map | Rol |
|---|---|
| `parsing/` | Analyse van tekst, JSON, YAML of andere formaten |
| `network/` | Generieke netwerkhulpmiddelen |
| `formatting/` | Opmaak van waarden, datums, groottes of tabellen |
| `utils/` | Overkoepelende hulpfuncties |

### Regel

`shared/` mag geen rommelmap worden.

Een hulpmiddel hoort alleen in `shared/` als het:

- herbruikbaar is;
- generiek is;
- onafhankelijk is van een specifieke use case;
- nuttig is voor meerdere lagen.

---

## 13. Overzicht van verantwoordelijkheden

| Map | Hoofdrol | Mag afhangen van | Mag niet afhangen van |
|---|---|---|---|
| `app/` | De applicatie samenstellen en starten | Alle lagen | — |
| `core/` | Vocabulaire, constanten, enums en exceptions | `shared/` indien nodig | `infrastructure/`, `interfaces/` |
| `domain/` | Pure bedrijfslogica | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Use cases orkestreren | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Contracten definiëren | `domain/` indien nodig | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Ports implementeren en met de buitenwereld communiceren | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Met de gebruiker communiceren | `application/`, `core/` | `infrastructure/` rechtstreeks |
| `plugins/` | Extensies toevoegen | Afhankelijk van het type extensie | Omzeilen van de architectuur |
| `shared/` | Overkoepelende hulpmiddelen | Geen bedrijfslaag | Specifieke bedrijfslogica |

---

## 14. Voorbeeld van de flow van een actie

Neem een gebruiker die vraagt om een rapport naar Markdown te exporteren.

```text
1. De gebruiker voert een CLI-commando uit.

2. interfaces/cli/
   Ontvangt het commando en de opties.

3. interfaces/cli/
   Roept de bijbehorende use case aan in application/.

4. application/
   Valideert de intentie en bereidt de actie voor.

5. application/
   Gebruikt het domein om het rapport op te bouwen of te valideren.

6. application/
   Vraagt een export aan via de port ReportExporter.

7. infrastructure/
   Levert de implementatie MarkdownExporter.

8. infrastructure/
   Schrijft het Markdown-bestand naar schijf.

9. interfaces/cli/
   Toont het resultaat aan de gebruiker.
```

Vereenvoudigd schema:

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
Markdown-bestand
```

---

## 15. Waarom deze architectuur?

### Leesbaarheid

Elke map heeft één rol, waardoor je makkelijker vindt waar je een functie moet toevoegen of corrigeren.

### Testbaarheid

Het domein kan worden getest zonder interface, zonder database en zonder netwerktoegang.

### Onderhoudbaarheid

Een wijziging in de interface, de opslag of een externe tool mag niet vereisen dat de bedrijfslogica wordt herschreven.

### Beveiliging

Gevoelige toegang — bestanden, netwerk, subprocessen, databases — is geconcentreerd in `infrastructure/`. Dat maakt auditen en controleren eenvoudiger.

### Uitbreidbaarheid

Je kunt toevoegen:

- een nieuwe interface;
- een nieuw exportformaat;
- een nieuwe opslagbackend;
- een nieuwe plugin;
- een nieuwe systeemprobe;

zonder de bedrijfskern te wijzigen.

### Overdraagbaarheid

De applicatie kan zich ontwikkelen naar andere omgevingen, systemen of interactievormen zonder aan een specifieke technologie vast te zitten.

---

## 16. Regels om te onthouden

- Het domein is puur.
- De applicatie orkestreert.
- De ports declareren de behoeften.
- De infrastructuur implementeert.
- De interfaces tonen en verzamelen.
- `app/` assembleert.
- `core/` en `shared/` leveren het overkoepelende vocabulaire en de hulpmiddelen.
- Plugins breiden uit zonder de architectuur te omzeilen.

In één zin:

> **De applicatie scheidt wat ze doet, hoe ze het doet en hoe de gebruiker haar gebruikt.**
