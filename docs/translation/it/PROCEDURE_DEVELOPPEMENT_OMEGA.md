# Procedura di sviluppo — [PROJECT_NAME]

**Lingue:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](../pt-BR/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Campo | Valore |
|---|---|
| Progetto | [PROJECT_NAME] |
| Versione obiettivo | [TARGET_VERSION] |
| Responsabile | [NOME] |
| Data di creazione | [AAAA-MM-GG] |
| Ultimo aggiornamento | [AAAA-MM-GG] |
| Stato generale | Bozza / In corso / Validato / In produzione |
| Ambiente obiettivo | [Linux / Debian / Server / Postazione] |
| Linguaggio principale | [Python / Bash / Lua / Altro] |
| Repository | [URL_O_PERCORSO] |

## Regole trasversali

- [ ] Nessun codice viene scritto prima della validazione del piano finale.
- [ ] Ogni decisione importante è documentata.
- [ ] Ogni anomalia è registrata.
- [ ] Ogni correzione è testata.
- [ ] Ogni cambiamento di comportamento è documentato.
- [ ] I backup vengono fatti prima di qualsiasi intervento in produzione.
- [ ] L'IA analizza e propone; l'umano decide, valida e distribuisce.
- [ ] Il codice resta allineato alla documentazione finale.

## Monitoraggio globale delle fasi

| Fase | Attore | Deliverable principale | Stato | Data di validazione |
|---:|---|---|---|---|
| 1 | Umano | Bisogni e progettazione | [ ] | [AAAA-MM-GG] |
| 2 | Umano | Bozza di architettura e piano preliminare | [ ] | [AAAA-MM-GG] |
| 3 | IA | Analisi, effetti collaterali, piano finale | [ ] | [AAAA-MM-GG] |
| 4 | Umano | Nucleo del progetto codificato | [ ] | [AAAA-MM-GG] |
| 5 | IA | Audit del codice, correzioni e test | [ ] | [AAAA-MM-GG] |
| 6 | Umano | Test reali in produzione | [ ] | [AAAA-MM-GG] |
| 7 | IA | Piano di correzione e codifica finale | [ ] | [AAAA-MM-GG] |
| 8 | Umano | Test finali | [ ] | [AAAA-MM-GG] |
| 9 | Umano | Bozza della documentazione | [ ] | [AAAA-MM-GG] |
| 10 | IA | Documentazione finale | [ ] | [AAAA-MM-GG] |
| 11 | Umano | Messa in produzione | [ ] | [AAAA-MM-GG] |

---

# Fase 1 — Riflessione, bisogni, uso e progettazione

**Attore: Umano**  
**Obiettivo:** definire il problema, gli utenti, l'uso reale, i vincoli e i confini del progetto.

## 1. Problema iniziale

- Problema individuato: [DA COMPLETARE]
- Situazione attuale: [DA COMPLETARE]
- Conseguenza del problema: [DA COMPLETARE]
- Obiettivo del progetto: [DA COMPLETARE]

## 2. Utenti destinatari

| Utente | Bisogno principale | Livello tecnico | Uso previsto |
|---|---|---|---|
| [Utente 1] | [DA COMPLETARE] | [Principiante / Tecnico / Esperto] | [DA COMPLETARE] |
| [Utente 2] | [DA COMPLETARE] | [Principiante / Tecnico / Esperto] | [DA COMPLETARE] |

## 3. Scenari d'uso

### Scenario nominale

- Contesto: [DA COMPLETARE]
- Azione dell'utente: [DA COMPLETARE]
- Risultato atteso: [DA COMPLETARE]

### Scenario limite

- Contesto: [DA COMPLETARE]
- Azione dell'utente: [DA COMPLETARE]
- Risultato atteso: [DA COMPLETARE]

### Scenario di errore

- Contesto: [DA COMPLETARE]
- Azione dell'utente: [DA COMPLETARE]
- Risultato atteso: [DA COMPLETARE]

### Scenario vietato o pericoloso

- Contesto: [DA COMPLETARE]
- Comportamento atteso: [Rifiuto / Avviso / Blocco / Registrazione nei log]
- Giustificazione: [DA COMPLETARE]

## 4. Funzionalità

### Obbligatorie

- [ ] [Funzionalità 1]
- [ ] [Funzionalità 2]
- [ ] [Funzionalità 3]

### Utili ma rinviabili

- [ ] [Funzionalità 1]
- [ ] [Funzionalità 2]

### Opzionali

- [ ] [Funzionalità 1]

### Escluse

- [ ] [Funzionalità esclusa]
- Giustificazione: [DA COMPLETARE]

## 5. Vincoli

| Ambito | Vincolo | Priorità |
|---|---|---|
| Sistema | [Linux / Debian / Versione] | [Alta / Media / Bassa] |
| Linguaggio | [Python / Bash / Lua] | [Alta / Media / Bassa] |
| Dipendenze | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Prestazioni | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Sicurezza | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Compatibilità | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Manutenzione | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Distribuzione | [DA COMPLETARE] | [Alta / Media / Bassa] |

## 6. Rischi individuati

| Rischio | Impatto | Probabilità | Misura di prevenzione |
|---|---|---|---|
| [Rischio 1] | [Basso / Medio / Alto] | [Bassa / Media / Alta] | [DA COMPLETARE] |
| [Rischio 2] | [Basso / Medio / Alto] | [Bassa / Media / Alta] | [DA COMPLETARE] |

## 7. Decisioni prese

| ID | Decisione | Giustificazione | Data |
|---:|---|---|---|
| D-001 | [DA COMPLETARE] | [DA COMPLETARE] | [AAAA-MM-GG] |
| D-002 | [DA COMPLETARE] | [DA COMPLETARE] | [AAAA-MM-GG] |

## 8. Domande aperte

- [ ] [Domanda 1]
- [ ] [Domanda 2]

## Validazione della fase 1

- [ ] Il problema è formulato chiaramente.
- [ ] Gli utenti sono identificati.
- [ ] I principali scenari d'uso sono descritti.
- [ ] Le funzionalità obbligatorie sono elencate.
- [ ] I confini del progetto sono espliciti.
- [ ] I vincoli tecnici sono noti.
- [ ] I rischi principali sono individuati.

**Stato:** [ ] Bozza / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 2 — Bozza, componenti principali e piano di sviluppo

**Attore: Umano**  
**Obiettivo:** trasformare i bisogni in un'architettura logica e in un piano di sviluppo applicabile.

## 1. Componenti principali

| Componente | Responsabilità | Non deve fare | Priorità |
|---|---|---|---|
| Interfaccia / CLI | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Nucleo di business | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Configurazione | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Modelli di dati | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Servizi | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Archiviazione | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Esportazione | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Log | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Sicurezza | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| Test | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |

## 2. Flusso principale

```text
[Input dell'utente]
    → [Interfaccia]
    → [Validazione]
    → [Nucleo di business]
    → [Servizi / Moduli]
    → [Risultato]
    → [Output / Archiviazione / Log]
```

## 3. Moduli previsti

| Modulo | Ruolo | Dipendenze | Priorità |
|---|---|---|---|
| [module_1] | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| [module_2] | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |
| [module_3] | [DA COMPLETARE] | [DA COMPLETARE] | [Alta / Media / Bassa] |

## 4. Albero preliminare

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

## 5. Dipendenze previste

| Dipendenza | Uso | Versione minima | Giustificazione |
|---|---|---|---|
| [Dipendenza 1] | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |
| [Dipendenza 2] | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |

## 6. Suddivisione dello sviluppo

| Fase | Contenuto | Priorità | Stima |
|---:|---|---|---|
| 1 | Basi: struttura, configurazione, errori, log | [Alta / Media] | [Durata] |
| 2 | Modelli e contratti | [Alta / Media] | [Durata] |
| 3 | Nucleo di business | [Alta / Media] | [Durata] |
| 4 | Interfaccia / CLI | [Alta / Media] | [Durata] |
| 5 | Archiviazione / esportazione | [Alta / Media] | [Durata] |
| 6 | Test | [Alta / Media] | [Durata] |
| 7 | Documentazione e packaging | [Alta / Media] | [Durata] |

## Validazione della fase 2

- [ ] I componenti principali sono individuati.
- [ ] Ogni modulo ha una responsabilità chiara.
- [ ] I flussi principali sono descritti.
- [ ] L'albero preliminare è definito.
- [ ] Le dipendenze principali sono individuate.
- [ ] L'ordine di sviluppo è definito.
- [ ] Nessuno sviluppo è stato avviato.

**Stato:** [ ] Bozza / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 3 — Analisi dell'IA, effetti collaterali e piano finale

**Attore: IA**  
**Obiettivo:** analizzare i documenti prodotti dall'umano, individuare i rischi e produrre un piano finale applicabile.

## 1. Documenti analizzati

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Altro documento]

## 2. Prompt di analisi dell'IA

```text
Analizza questo progetto senza scrivere codice.

1. Rileva le incoerenze.
2. Rileva le funzioni mancanti.
3. Rileva le responsabilità collocate male.
4. Individua i possibili effetti collaterali.
5. Individua i casi di errore.
6. Individua i rischi di sicurezza.
7. Individua i problemi di compatibilità.
8. Proponi una struttura di progetto più robusta.
9. Proponi un piano di sviluppo finale.
10. Indica i punti che devono restare sotto decisione umana.
```

## 3. Incoerenze rilevate

| ID | Descrizione | Impatto | Proposta | Decisione umana |
|---:|---|---|---|---|
| A-001 | [DA COMPLETARE] | [Basso / Medio / Alto] | [DA COMPLETARE] | [Accettata / Rifiutata / Rinviata] |
| A-002 | [DA COMPLETARE] | [Basso / Medio / Alto] | [DA COMPLETARE] | [Accettata / Rifiutata / Rinviata] |

## 4. Effetti collaterali individuati

| ID | Effetto collaterale | Innesco | Impatto | Prevenzione | Stato |
|---:|---|---|---|---|---|
| SE-001 | [DA COMPLETARE] | [DA COMPLETARE] | [Basso / Medio / Alto] | [DA COMPLETARE] | [Aperto / Trattato / Accettato] |
| SE-002 | [DA COMPLETARE] | [DA COMPLETARE] | [Basso / Medio / Alto] | [DA COMPLETARE] | [Aperto / Trattato / Accettato] |

## 5. Casi di errore da prevedere

| Caso | Comportamento atteso | Messaggio / log atteso | Test associato |
|---|---|---|---|
| File mancante | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |
| Permesso negato | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |
| Rete non disponibile | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |
| Input non valido | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |
| Interruzione da parte dell'utente | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |
| Dati corrotti | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] |

## 6. Rischi di sicurezza

| Rischio | Scenario | Misura | Priorità |
|---|---|---|---|
| [Rischio 1] | [DA COMPLETARE] | [DA COMPLETARE] | [P0 / P1 / P2] |
| [Rischio 2] | [DA COMPLETARE] | [DA COMPLETARE] | [P0 / P1 / P2] |

## 7. Piano di sviluppo finale

| Fase | Obiettivo | Deliverable | Criteri di completamento | Dipendenze |
|---:|---|---|---|---|
| 1 | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [Nessuna] |
| 2 | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [Fase 1] |
| 3 | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [Fase 2] |

## Validazione della fase 3

- [ ] Le incoerenze sono trattate o documentate.
- [ ] Gli effetti collaterali sono individuati.
- [ ] I casi di errore sono previsti.
- [ ] I rischi di sicurezza sono trattati.
- [ ] Il piano finale è validato dall'umano.
- [ ] Le decisioni finali sono registrate.

**Stato:** [ ] Bozza / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 4 — Codifica del nucleo del progetto

**Attore: Umano**  
**Obiettivo:** sviluppare il nucleo funzionale senza aggiungere funzionalità fuori ambito.

## 1. Ambito della codifica

- [ ] Struttura del progetto
- [ ] Ambiente virtuale
- [ ] Dipendenze
- [ ] Configurazione
- [ ] Modelli di dati
- [ ] Eccezioni
- [ ] Logging
- [ ] Servizi di business
- [ ] Nucleo di business
- [ ] Test unitari
- [ ] CLI / interfaccia
- [ ] Integrazione

## 2. Ordine di implementazione

| Ordine | Elemento | File / modulo | Stato | Commit |
|---:|---|---|---|---|
| 1 | [Elemento] | [percorso] | [ ] | [hash] |
| 2 | [Elemento] | [percorso] | [ ] | [hash] |
| 3 | [Elemento] | [percorso] | [ ] | [hash] |

## 3. Regole di commit

- Un commit = una sola intenzione.
- Non mescolare funzionalità, correzione e refactoring.
- Messaggio consigliato:

```text
[type]: [descrizione breve]

[type] = feat, fix, refactor, test, docs, chore
```

Esempio:

```text
feat: aggiunge il caricamento e la validazione della configurazione
```

## 4. Test iniziali

| Test | Obiettivo | Comando | Risultato atteso | Stato |
|---|---|---|---|---|
| [Test 1] | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [ ] |
| [Test 2] | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [ ] |

## Validazione della fase 4

- [ ] Il nucleo di business funziona.
- [ ] Gli input principali sono validati.
- [ ] Gli errori principali sono gestiti.
- [ ] I test unitari passano.
- [ ] Il progetto si avvia in modalità base.
- [ ] Nessuna funzionalità fuori ambito è stata aggiunta.

**Stato:** [ ] In corso / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 5 — Analisi del codice, correzione e test da parte dell'IA

**Attore: IA**  
**Obiettivo:** rilevare difetti, effetti collaterali e rischi prima dei test reali.

## 1. Prompt di audit dell'IA

```text
Analizza il codice senza riscriverlo completamente.

1. Verifica la conformità al piano di sviluppo.
2. Rileva i bug probabili.
3. Rileva gli effetti collaterali.
4. Rileva le perdite di risorse.
5. Rileva gli errori non gestiti.
6. Rileva gli input non validati.
7. Rileva i problemi di sicurezza.
8. Rileva i problemi di prestazioni.
9. Rileva il codice morto.
10. Rileva le responsabilità collocate male.
11. Proponi correzioni mirate.
12. Proponi i test mancanti.
```

## 2. Risultati dell'audit

| ID | File / funzione | Constatazione | Gravità | Correzione proposta | Stato |
|---:|---|---|---|---|---|
| C-001 | [percorso] | [DA COMPLETARE] | [Critica / Maggiore / Minore] | [DA COMPLETARE] | [Aperto / Corretto / Validato] |
| C-002 | [percorso] | [DA COMPLETARE] | [Critica / Maggiore / Minore] | [DA COMPLETARE] | [Aperto / Corretto / Validato] |

## 3. Test aggiunti

| Test | Obiettivo | File di test | Stato |
|---|---|---|---|
| [Test 1] | [DA COMPLETARE] | [percorso] | [ ] |
| [Test 2] | [DA COMPLETARE] | [percorso] | [ ] |

## Validazione della fase 5

- [ ] I bug critici sono corretti.
- [ ] Gli effetti collaterali sono trattati o documentati.
- [ ] I test unitari passano.
- [ ] I test di integrazione passano.
- [ ] Il codice è conforme al piano finale.
- [ ] Le correzioni sono state applicate in modo progressivo.

**Stato:** [ ] In corso / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 6 — Studio reale e test in produzione

**Attore: Umano**  
**Obiettivo:** validare il software in condizioni reali e registrare tutte le anomalie.

## 1. Ambiente di test

| Elemento | Valore |
|---|---|
| Macchina | [DA COMPLETARE] |
| Sistema | [DA COMPLETARE] |
| Versione del software | [DA COMPLETARE] |
| Ambiente | [Produzione controllata / Preproduzione / Server reale] |
| Backup eseguito | [Sì / No] |
| Data del backup | [AAAA-MM-GG] |
| Metodo di rollback | [DA COMPLETARE] |

## 2. Scenari testati

| ID | Scenario | Comando | Risultato atteso | Risultato ottenuto | Stato |
|---:|---|---|---|---|---|
| T-001 | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [OK / KO / Parziale] |
| T-002 | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [OK / KO / Parziale] |

## 3. Griglia di osservazione

| Ambito | Elemento osservato | Risultato | Commento |
|---|---|---|---|
| Funzionale | Funzione attesa | [OK / KO] | [DA COMPLETARE] |
| Interfaccia | Chiarezza dei comandi | [OK / KO] | [DA COMPLETARE] |
| Prestazioni | Tempo di esecuzione | [OK / KO] | [DA COMPLETARE] |
| Stabilità | Nessun crash inatteso | [OK / KO] | [DA COMPLETARE] |
| Errori | Comprensibilità dei messaggi | [OK / KO] | [DA COMPLETARE] |
| Log | Qualità e utilità | [OK / KO] | [DA COMPLETARE] |
| Sicurezza | Comportamento sicuro | [OK / KO] | [DA COMPLETARE] |
| Compatibilità | Funzionamento sul target reale | [OK / KO] | [DA COMPLETARE] |
| Estetica | Leggibilità degli output | [OK / KO] | [DA COMPLETARE] |
| Uso reale | Fluidità del flusso di lavoro | [OK / KO] | [DA COMPLETARE] |

## 4. Registro delle anomalie

| ID | Data | Gravità | Descrizione | Log | Ipotesi | Correzione proposta | Stato |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [AAAA-MM-GG] | [Critica / Maggiore / Minore / Estetica] | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [Aperto / Corretto / Validato] |
| BUG-002 | [AAAA-MM-GG] | [Critica / Maggiore / Minore / Estetica] | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [DA COMPLETARE] | [Aperto / Corretto / Validato] |

## Validazione della fase 6

- [ ] Tutti gli scenari critici sono stati testati.
- [ ] I bug sono registrati.
- [ ] I problemi di ergonomia sono registrati.
- [ ] I problemi estetici sono registrati.
- [ ] Nessun bug critico bloccante è stato ignorato.

**Stato:** [ ] In corso / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 7 — Piano di miglioramento, correzioni e codifica finale

**Attore: IA**  
**Obiettivo:** trasformare le anomalie in correzioni prioritizzate, poi applicare le modifiche al codice necessarie.

## 1. Prompt di analisi delle anomalie

```text
Ecco il registro dei test in produzione.

1. Classifica le anomalie per gravità.
2. Raggruppa le anomalie correlate.
3. Individua le cause probabili.
4. Proponi una correzione minima per ogni anomalia.
5. Indica i rischi di regressione.
6. Proponi i test da aggiungere.
7. Proponi miglioramenti di ergonomia.
8. Proponi miglioramenti estetici.
9. Modifica solo ciò che è necessario.
10. Preserva i comportamenti validati.
```

## 2. Prioritizzazione delle anomalie

| Priorità | Tipo | Anomalie interessate | Trattamento |
|---|---|---|---|
| P0 | Crash, perdita di dati, vulnerabilità | [BUG-XXX] | Correzione immediata |
| P1 | Funzionalità errata | [BUG-XXX] | Correzione prima della validazione finale |
| P2 | Esperienza utente scadente | [BUG-XXX] | Correzione se ragionevole |
| P3 | Estetica, messaggio, formato | [BUG-XXX] | Correzione o rinvio |
| P4 | Miglioramento futuro | [BUG-XXX] | Backlog |

## 3. Correzioni applicate

| ID | Anomalia | Correzione | File modificati | Test aggiunti | Rischio di regressione | Stato |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [DA COMPLETARE] | [percorso] | [percorso] | [Basso / Medio / Alto] | [Applicato / Validato] |
| FIX-002 | [BUG-XXX] | [DA COMPLETARE] | [percorso] | [percorso] | [Basso / Medio / Alto] | [Applicato / Validato] |

## Validazione della fase 7

- [ ] Ogni anomalia ha uno stato chiaro.
- [ ] Le correzioni sono applicate per priorità.
- [ ] I test di non regressione passano.
- [ ] I comportamenti validati sono preservati.
- [ ] Ogni correzione è documentata.

**Stato:** [ ] In corso / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 8 — Test finali

**Attore: Umano**  
**Obiettivo:** validare la versione candidata prima della documentazione finale e della messa in produzione stabile.

## 1. Test di validazione

| Test | Obiettivo | Comando | Risultato atteso | Risultato ottenuto | Stato |
|---|---|---|---|---|---|
| Scenario nominale | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |
| Scenario di errore | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |
| Opzioni CLI | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |
| Configurazione | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |
| Permessi | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |
| Interruzione | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |
| Non regressione | [DA COMPLETARE] | [comando] | [DA COMPLETARE] | [DA COMPLETARE] | [ ] |

## 2. Checklist finale

- [ ] Il progetto si avvia correttamente.
- [ ] I comandi principali funzionano.
- [ ] Gli errori sono comprensibili.
- [ ] I log sono utilizzabili.
- [ ] Nessun bug critico è presente.
- [ ] Nessuna regressione è stata rilevata.
- [ ] Le prestazioni sono accettabili.
- [ ] La sicurezza è conforme ai requisiti.
- [ ] La versione è identificabile.
- [ ] Il rollback è possibile.

## Validazione della fase 8

**Decisione:** [ ] Versione candidata / [ ] Ritorno alla correzione  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 9 — Bozza della documentazione

**Attore: Umano**  
**Obiettivo:** documentare il software così come funziona realmente.

## 1. Documenti da produrre

| Documento | Obiettivo | Stato |
|---|---|---|
| `README.md` | Presentazione e avvio rapido | [ ] |
| `USER_GUIDE.md` | Uso dettagliato e accessibile | [ ] |
| `TECHNICAL_GUIDE.md` | Architettura e funzionamento interno | [ ] |
| `DEVELOPER_GUIDE.md` | Ambiente, test, convenzioni | [ ] |
| `INSTALLATION.md` | Prerequisiti e installazione | [ ] |
| `SECURITY.md` | Rischi, permessi, buone pratiche | [ ] |
| `TROUBLESHOOTING.md` | Errori frequenti e soluzioni | [ ] |
| `CHANGELOG.md` | Cronologia delle versioni | [ ] |

## 2. Contenuti da verificare

- [ ] Ogni comando è documentato.
- [ ] Ogni opzione è documentata.
- [ ] Ogni file di configurazione è documentato.
- [ ] Ogni dipendenza è documentata.
- [ ] Ogni errore frequente è spiegato.
- [ ] I limiti sono espliciti.
- [ ] Gli esempi sono testabili.

## Validazione della fase 9

**Stato:** [ ] Bozza / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 10 — Impaginazione e documentazione finale

**Attore: IA**  
**Obiettivo:** completare, strutturare e armonizzare la documentazione senza inventare comportamenti assenti dal codice.

## 1. Prompt di completamento della documentazione

```text
Ecco le bozze della documentazione.

1. Verifica la coerenza con il codice reale.
2. Rileva le funzioni non documentate.
3. Rileva le opzioni CLI non documentate.
4. Rileva i messaggi di errore non spiegati.
5. Rileva le dipendenze mancanti.
6. Rileva i passaggi di installazione mancanti.
7. Rileva le incoerenze tra documenti.
8. Migliora la struttura e la leggibilità.
9. Completa le sezioni mancanti.
10. Non modificare alcun comportamento descritto senza prova nel codice.
```

## 2. Verifiche della documentazione

| Verifica | Stato | Commento |
|---|---|---|
| Coerenza con il codice | [ ] | [DA COMPLETARE] |
| Comandi documentati | [ ] | [DA COMPLETARE] |
| Opzioni documentate | [ ] | [DA COMPLETARE] |
| Codici di uscita documentati | [ ] | [DA COMPLETARE] |
| Configurazione documentata | [ ] | [DA COMPLETARE] |
| Dipendenze documentate | [ ] | [DA COMPLETARE] |
| Errori frequenti documentati | [ ] | [DA COMPLETARE] |
| Esempi testabili | [ ] | [DA COMPLETARE] |
| Struttura armonizzata | [ ] | [DA COMPLETARE] |

## Validazione della fase 10

**Stato:** [ ] Bozza / [ ] Validato  
**Validato da:** [NOME]  
**Data:** [AAAA-MM-GG]

---

# Fase 11 — Messa in produzione finale

**Attore: Umano**  
**Obiettivo:** distribuire la versione validata, documentata e testata.

## 1. Preparazione

- [ ] Versione validata nella fase 8.
- [ ] Documentazione finale validata nella fase 10.
- [ ] Backup dell'ambiente esistente eseguito.
- [ ] Procedura di rollback disponibile.
- [ ] Tag di versione creato.

Comandi:

```bash
git tag -a v[VERSION] -m "Versione stabile [VERSION]"
git push origin v[VERSION]
```

## 2. Packaging

```bash
python -m build
```

Verifica:

```bash
sha256sum dist/*
```

## 3. Distribuzione

| Passaggio | Comando / azione | Stato | Commento |
|---:|---|---|---|
| 1 | Backup | [ ] | [DA COMPLETARE] |
| 2 | Distribuire la versione con tag | [ ] | [DA COMPLETARE] |
| 3 | Verificare il servizio | [ ] | [DA COMPLETARE] |
| 4 | Verificare i log | [ ] | [DA COMPLETARE] |
| 5 | Testare il comando principale | [ ] | [DA COMPLETARE] |
| 6 | Documentare la versione distribuita | [ ] | [DA COMPLETARE] |

## 4. Verifiche post-distribuzione

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] Il servizio è attivo.
- [ ] Nessun errore critico compare nei log.
- [ ] Il comando principale risponde.
- [ ] La versione distribuita corrisponde al tag validato.
- [ ] Il rollback è documentato e testabile.

## Validazione finale

| Campo | Valore |
|---|---|
| Versione distribuita | [VERSION] |
| Data di messa in produzione | [AAAA-MM-GG] |
| Ambiente | [DA COMPLETARE] |
| Responsabile | [NOME] |
| Rollback testato | [Sì / No] |
| Stato finale | [In produzione / Fallimento / Rollback] |

---

# Cronologia delle modifiche del documento

| Data | Versione | Autore | Modifica |
|---|---|---|---|
| [AAAA-MM-GG] | 0.1 | [NOME] | Creazione del modello |
| [AAAA-MM-GG] | [VERSION] | [NOME] | [DA COMPLETARE] |
