# Architettura del progetto — Clean Architecture

**Lingue:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Questo documento spiega come è organizzato il progetto, perché è stata scelta questa organizzazione e che cosa contiene ogni cartella. È pensato sia per i visitatori che vogliono capire il funzionamento dell'applicazione, sia per gli sviluppatori che desiderano contribuire o occuparsi della sua manutenzione.

L'applicazione segue una **Clean Architecture**: il cuore del software è isolato dai dettagli tecnici, dalle interfacce utente e dalle dipendenze esterne. Questa separazione rende il progetto più facile da leggere, testare, mantenere e far evolvere.

---

## 1. Principio generale

L'applicazione è suddivisa in livelli, ciascuno con un ruolo preciso.

L'idea centrale è semplice:

```text
L'interfaccia richiede un'azione.
L'applicazione orchestra questa azione.
Il dominio applica le regole di business.
Le port definiscono ciò di cui l'applicazione ha bisogno.
L'infrastruttura fornisce le implementazioni concrete.
```

In questo modo, la logica importante del progetto non dipende direttamente:

- dal terminale;
- dall'interfaccia grafica;
- da un database;
- dalla rete;
- dal file system;
- da una libreria esterna;
- da uno strumento di sistema.

Questa indipendenza permette di sostituire una parte del software senza riscrivere tutto il resto.

---

## 2. Panoramica

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, ciclo di vita e iniezione delle dipendenze
        ├── core/             Capacità, enum ed eccezioni trasversali
        ├── domain/           Logica di business pura
        ├── application/      Casi d'uso: command e query
        ├── infrastructure/   Backend, archiviazione, esportazioni, log, sonde di sistema…
        ├── ports/            Contratti Protocol / ABC
        ├── interfaces/       CLI e TUI
        ├── plugins/          Estensioni integrate
        └── shared/           Parsing, rete, formattazione e utilità trasversali
```

---

## 3. Schema delle dipendenze

Le dipendenze devono sempre andare nella stessa direzione:

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

In pratica:

- `interfaces/` può chiamare `application/`.
- `application/` può chiamare `domain/` e usare i contratti definiti in `ports/`.
- `domain/` non dipende né da `application/`, né da `infrastructure/`, né da `interfaces/`.
- `infrastructure/` implementa i contratti definiti in `ports/`.
- `app/` assembla i livelli e fornisce le dipendenze necessarie.

Regola essenziale:

> Il dominio non conosce mai l'infrastruttura.  
> L'infrastruttura conosce le port, ma il dominio non conosce l'infrastruttura.

---

## 4. La cartella `app/`

### Ruolo

La cartella `app/` è il **punto di assemblaggio** dell'applicazione.

Contiene:

- l'avvio dell'applicazione;
- il ciclo di vita;
- il container di iniezione delle dipendenze;
- la costruzione degli oggetti necessari al funzionamento;
- la scelta delle implementazioni concrete;
- l'inizializzazione della configurazione;
- il collegamento tra i livelli.

### Esempi di responsabilità

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| File | Ruolo |
|---|---|
| `bootstrap.py` | Avvia l'applicazione e sceglie l'interfaccia da lanciare |
| `container.py` | Crea e collega le dipendenze |
| `lifecycle.py` | Gestisce avvio, arresto e pulizia |

### Regola

`app/` non contiene logica di business.

Non decide:

- che cos'è una regola di business;
- come deve essere calcolato un dato;
- come deve essere analizzata una richiesta;
- come deve essere esportato un file.

Si limita ad assemblare i componenti esistenti.

---

## 5. La cartella `core/`

### Ruolo

La cartella `core/` contiene il **vocabolario trasversale** del progetto.

Raggruppa elementi condivisi da più livelli, che però non sono di per sé regole di business.

Può contenere:

- capacità;
- enumerazioni;
- costanti;
- eccezioni trasversali;
- tipi comuni;
- informazioni sulla piattaforma;
- definizioni di livelli o di stati.

### Esempio

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| File | Ruolo |
|---|---|
| `capabilities.py` | Descrive le capacità disponibili o attivabili |
| `constants.py` | Contiene le costanti del progetto |
| `enums.py` | Definisce gli stati, i tipi o i livelli possibili |
| `exceptions.py` | Definisce gli errori trasversali |

### Regola

`core/` deve restare leggero e stabile.

Non deve contenere:

- logica di business complessa;
- chiamate di rete;
- accessi al disco;
- codice di interfaccia utente;
- dipendenze dirette da librerie esterne.

---

## 6. La cartella `domain/`

### Ruolo

La cartella `domain/` è il **cuore del progetto**.

Contiene la logica di business pura: le regole, i concetti e i calcoli che definiscono davvero ciò che fa l'applicazione.

Può contenere:

- entità;
- value object;
- policy;
- regole di business;
- servizi di dominio;
- calcoli;
- validazioni di business;
- modelli di dati di business.

### Esempio

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Elemento | Ruolo |
|---|---|
| Entità | Oggetto di business dotato di identità |
| Value object | Valore immutabile e validato |
| Policy | Regola di business riutilizzabile |
| Servizio di dominio | Logica di business che non appartiene a una sola entità |

### Regole rigorose

La cartella `domain/`:

- non accede al disco;
- non effettua chiamate di rete;
- non esegue comandi di sistema;
- non accede a database;
- non importa l'interfaccia utente;
- non importa l'infrastruttura;
- non dipende da librerie tecniche esterne quando è possibile evitarlo.

Il dominio deve poter essere testato senza server, senza file, senza rete e senza interfaccia.

---

## 7. La cartella `application/`

### Ruolo

La cartella `application/` orchestra i casi d'uso.

Risponde alla domanda:

> «Che cosa succede quando l'utente richiede questa azione?»

Contiene:

- i command;
- le query;
- i casi d'uso;
- gli orchestratori;
- i gestori delle azioni;
- il coordinamento tra il dominio e le port.

### Distinzione command / query

| Tipo | Obiettivo | Modifica i dati |
|---|---|---|
| Command | Eseguire un'azione | Sì |
| Query | Leggere o calcolare un'informazione | No |

Esempi:

| Command | Query |
|---|---|
| Applicare una configurazione | Leggere la configurazione attuale |
| Avviare un'analisi | Ottenere il risultato di un'analisi |
| Esportare un report | Elencare gli elementi disponibili |
| Eliminare dati | Consultare una cronologia |

### Esempio

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Regola

`application/` non contiene:

- output nel terminale;
- interfaccia Textual;
- comandi Rich;
- accessi diretti al database;
- chiamate dirette a strumenti esterni.

Coordina, ma non implementa i dettagli tecnici.

---

## 8. La cartella `ports/`

### Ruolo

La cartella `ports/` definisce i **contratti** attesi dall'applicazione.

Una port descrive **ciò di cui l'applicazione ha bisogno**, senza imporre il modo in cui deve essere implementato.

Contiene in genere:

- `Protocol`;
- classi astratte `ABC`;
- interfacce di repository;
- interfacce di esportazione;
- interfacce di sonde;
- interfacce di servizi esterni;
- interfacce di archiviazione.

### Esempio

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Ruolo |
|---|---|
| `Repository` | Leggere o memorizzare dati |
| `Exporter` | Produrre un output in un formato dato |
| `Probe` | Raccogliere un'informazione di sistema o di rete |
| `Storage` | Gestire un backend di persistenza |

### Esempio concettuale

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Questo contratto dice:

> «L'applicazione ha bisogno di un oggetto capace di esportare un report.»

Non dice:

- se l'esportazione sarà in Markdown;
- se l'esportazione sarà in JSON;
- se il file sarà scritto in locale;
- se l'esportazione sarà inviata in rete.

Queste scelte appartengono a `infrastructure/`.

### Regola

Le port sono contratti, non implementazioni.

Non devono contenere:

- logica di business complessa;
- accessi al disco;
- chiamate di rete;
- implementazioni concrete;
- dipendenze dirette da librerie esterne.

---

## 9. La cartella `infrastructure/`

### Ruolo

La cartella `infrastructure/` contiene le **implementazioni concrete** delle port.

È il livello che comunica con il mondo esterno.

Può contenere:

- accessi ai file;
- accessi al database;
- esportazioni Markdown, JSON, CSV o altre;
- logging;
- chiamate di rete;
- sonde di sistema;
- esecuzione controllata di strumenti esterni;
- adattatori verso librerie di terze parti;
- implementazioni di repository;
- implementazioni di archiviazione.

### Esempio

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

| Elemento | Ruolo |
|---|---|
| `sqlite_repository.py` | Implementa un repository con SQLite |
| `json_file_repository.py` | Implementa un repository con file JSON |
| `markdown_exporter.py` | Esporta un report in Markdown |
| `json_exporter.py` | Esporta un report in JSON |
| `process_probe.py` | Raccoglie informazioni sui processi |
| `filesystem_probe.py` | Raccoglie informazioni sul file system |
| `structured_logger.py` | Produce log strutturati |

### Regola

`infrastructure/` è l'unico livello autorizzato ad accedere direttamente:

- al file system;
- alla rete;
- a SQLite;
- alle librerie esterne;
- agli strumenti di sistema;
- ai sottoprocessi, quando sono necessari e controllati.

Questa centralizzazione facilita:

- i test;
- l'audit di sicurezza;
- la sostituzione di un backend;
- la limitazione degli effetti collaterali.

---

## 10. La cartella `interfaces/`

### Ruolo

La cartella `interfaces/` contiene i punti di ingresso visibili all'utente.

Separa chiaramente:

- la CLI;
- la TUI;
- eventuali future interfacce web o API.

### Struttura

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

| Interfaccia | Tecnologia | Ruolo |
|---|---|---|
| `cli/` | Rich | Interfaccia a riga di comando |
| `tui/` | Textual | Interfaccia interattiva nel terminale |

### CLI

La CLI è l'interfaccia a riga di comando.

Permette di:

- avviare l'applicazione;
- eseguire un'azione precisa;
- visualizzare un risultato;
- automatizzare un'operazione;
- integrare lo strumento in uno script;
- usare l'applicazione da remoto via SSH.

### TUI

La TUI è l'interfaccia interattiva nel terminale.

Permette di:

- navigare tra le funzionalità;
- visualizzare informazioni;
- eseguire azioni;
- consultare risultati;
- usare l'applicazione senza memorizzare tutti i comandi.

### Regola

Le interfacce non contengono logica di business.

Esse:

- ricevono un'intenzione dell'utente;
- chiamano un caso d'uso in `application/`;
- visualizzano il risultato;
- traducono gli errori in messaggi comprensibili.

Non devono:

- chiamare direttamente l'infrastruttura;
- eseguire sottoprocessi;
- accedere direttamente ai file;
- contenere regole di business;
- duplicare la logica di `application/`.

---

## 11. La cartella `plugins/`

### Ruolo

La cartella `plugins/` è riservata alle **estensioni integrate**.

Permette di aggiungere funzionalità senza appesantire il cuore del progetto.

Un plugin può, per esempio:

- aggiungere un formato di esportazione;
- aggiungere una sonda;
- aggiungere un comando;
- aggiungere una schermata TUI;
- aggiungere un'integrazione esterna;
- aggiungere una capacità opzionale.

### Principio

Un plugin deve rispettare le stesse regole del resto del progetto:

- non aggira le port;
- non modifica direttamente il dominio;
- espone le sue funzionalità tramite contratti chiari;
- resta disattivabile senza rompere l'applicazione.

### Struttura possibile

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Regola

Un plugin è un'estensione, non una porta sul retro.

Deve rispettare l'architettura generale e non deve creare dipendenze circolari con il cuore del progetto.

---

## 12. La cartella `shared/`

### Ruolo

La cartella `shared/` contiene utilità trasversali che non appartengono né al dominio, né all'applicazione, né all'infrastruttura.

Raggruppa funzioni generiche riutilizzabili.

Può contenere:

- parsing;
- utilità di rete;
- formattazione;
- manipolazione di testo;
- helper per le date;
- helper per i percorsi;
- utilità generiche di validazione;
- helper di serializzazione.

### Esempio

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Cartella | Ruolo |
|---|---|
| `parsing/` | Analisi di testo, JSON, YAML o altri formati |
| `network/` | Utilità di rete generiche |
| `formatting/` | Formattazione di valori, date, dimensioni o tabelle |
| `utils/` | Funzioni di utilità trasversali |

### Regola

`shared/` non deve diventare una cartella "ripostiglio".

Un'utilità va in `shared/` solo se è:

- riutilizzabile;
- generica;
- indipendente da un caso d'uso specifico;
- utile a più livelli.

---

## 13. Riepilogo delle responsabilità

| Cartella | Ruolo principale | Può dipendere da | Non deve dipendere da |
|---|---|---|---|
| `app/` | Assemblare e avviare l'applicazione | Tutti i livelli | — |
| `core/` | Vocabolario, costanti, enum ed eccezioni | `shared/` se necessario | `infrastructure/`, `interfaces/` |
| `domain/` | Logica di business pura | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Orchestrare i casi d'uso | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Definire i contratti | `domain/` se necessario | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Implementare le port e comunicare con l'esterno | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Interagire con l'utente | `application/`, `core/` | `infrastructure/` direttamente |
| `plugins/` | Aggiungere estensioni | A seconda del tipo di estensione | Aggirare l'architettura |
| `shared/` | Utilità trasversali | Nessun livello di business | Logica di business specifica |

---

## 14. Esempio di flusso di un'azione

Prendiamo un utente che richiede l'esportazione di un report in Markdown.

```text
1. L'utente lancia un comando CLI.

2. interfaces/cli/
   Riceve il comando e le sue opzioni.

3. interfaces/cli/
   Chiama il caso d'uso corrispondente in application/.

4. application/
   Valida l'intenzione e prepara l'azione.

5. application/
   Usa il dominio per costruire o validare il report.

6. application/
   Richiede un'esportazione tramite la port ReportExporter.

7. infrastructure/
   Fornisce l'implementazione MarkdownExporter.

8. infrastructure/
   Scrive il file Markdown su disco.

9. interfaces/cli/
   Mostra il risultato all'utente.
```

Schema semplificato:

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
File Markdown
```

---

## 15. Perché questa architettura?

### Leggibilità

Ogni cartella ha un ruolo unico, il che rende più facile capire dove aggiungere o correggere una funzionalità.

### Testabilità

Il dominio può essere testato senza interfaccia, senza database e senza accesso alla rete.

### Manutenibilità

Una modifica dell'interfaccia, dell'archiviazione o di uno strumento esterno non deve richiedere la riscrittura della logica di business.

### Sicurezza

Gli accessi sensibili — file, rete, sottoprocessi, database — sono concentrati in `infrastructure/`. Questo li rende più facili da verificare e controllare.

### Evolutività

È possibile aggiungere:

- una nuova interfaccia;
- un nuovo formato di esportazione;
- un nuovo backend di archiviazione;
- un nuovo plugin;
- una nuova sonda di sistema;

senza modificare il cuore di business.

### Portabilità

L'applicazione può evolvere verso altri ambienti, sistemi o modalità di interazione senza essere legata a una tecnologia specifica.

---

## 16. Regole da ricordare

- Il dominio è puro.
- L'applicazione orchestra.
- Le port dichiarano i bisogni.
- L'infrastruttura implementa.
- Le interfacce mostrano e raccolgono.
- `app/` assembla.
- `core/` e `shared/` forniscono il vocabolario e le utilità trasversali.
- I plugin estendono senza aggirare l'architettura.

In una frase:

> **L'applicazione separa ciò che fa, come lo fa e come l'utente la usa.**
