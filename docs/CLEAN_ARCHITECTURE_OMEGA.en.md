# Project Architecture — Clean Architecture

This document explains how the project is organized, why this organization was chosen, and what each folder contains. It is intended both for visitors who want to understand how the application works and for developers who want to contribute to or maintain it.

The application follows a **Clean Architecture**: the software core is isolated from technical details, user interfaces, and external dependencies. This separation makes the project easier to read, test, maintain, and evolve.

---

## 1. General principle

The application is divided into layers, each with a specific role.

The central idea is simple:

```text
The interface requests an action.
The application orchestrates that action.
The domain applies business rules.
The ports define what the application needs.
The infrastructure provides concrete implementations.
```

As a result, the project’s important logic does not directly depend on:

- the terminal;
- the graphical interface;
- a database;
- the network;
- the file system;
- an external library;
- a system tool.

This independence makes it possible to replace part of the software without rewriting everything else.

---

## 2. Overview

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, lifecycle, and dependency injection
        ├── core/             Cross-cutting capabilities, enums, and exceptions
        ├── domain/           Pure business logic
        ├── application/      Use cases: commands and queries
        ├── infrastructure/   Backends, storage, exports, logs, system probes…
        ├── ports/            Protocol / ABC contracts
        ├── interfaces/       CLI and TUI
        ├── plugins/          Built-in extensions
        └── shared/           Parsing, networking, formatting, and cross-cutting utilities
```

---

## 3. Dependency diagram

Dependencies must always flow in the same direction:

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

In practice:

- `interfaces/` may call `application/`.
- `application/` may call `domain/` and use the contracts defined in `ports/`.
- `domain/` depends neither on `application/`, nor on `infrastructure/`, nor on `interfaces/`.
- `infrastructure/` implements the contracts defined in `ports/`.
- `app/` assembles the layers and provides the required dependencies.

Essential rule:

> The domain never knows about the infrastructure.  
> The infrastructure knows about the ports, but the domain does not know about the infrastructure.

---

## 4. The `app/` folder

### Role

The `app/` folder is the application’s **assembly point**.

It contains:

- application startup;
- the lifecycle;
- the dependency injection container;
- construction of the objects required for operation;
- selection of concrete implementations;
- configuration initialization;
- wiring between layers.

### Example responsibilities

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| File | Role |
|---|---|
| `bootstrap.py` | Starts the application and selects the interface to launch |
| `container.py` | Creates and wires dependencies |
| `lifecycle.py` | Manages startup, shutdown, and cleanup |

### Rule

`app/` does not contain business logic.

It does not decide:

- what a business rule is;
- how data must be calculated;
- how a request must be analyzed;
- how a file must be exported.

It only assembles existing components.

---

## 5. The `core/` folder

### Role

The `core/` folder contains the project’s **cross-cutting vocabulary**.

It groups elements shared by several layers that are not, in themselves, business rules.

It may contain:

- capabilities;
- enumerations;
- constants;
- cross-cutting exceptions;
- common types;
- platform information;
- level or state definitions.

### Example

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| File | Role |
|---|---|
| `capabilities.py` | Describes available or activatable capabilities |
| `constants.py` | Contains project constants |
| `enums.py` | Defines possible states, types, or levels |
| `exceptions.py` | Defines cross-cutting errors |

### Rule

`core/` must remain lightweight and stable.

It must not contain:

- complex business logic;
- network calls;
- disk access;
- user interface code;
- direct dependencies on external libraries.

---

## 6. The `domain/` folder

### Role

The `domain/` folder is the **core of the project**.

It contains pure business logic: the rules, concepts, and calculations that truly define what the application does.

It may contain:

- entities;
- value objects;
- policies;
- business rules;
- domain services;
- calculations;
- business validations;
- business data models.

### Example

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Element | Role |
|---|---|
| Entity | Business object with an identity |
| Value object | Immutable and validated value |
| Policy | Reusable business rule |
| Domain service | Business logic that does not belong to a single entity |

### Strict rules

The `domain/` folder:

- performs no disk access;
- makes no network calls;
- does not execute system commands;
- does not access a database;
- does not import the user interface;
- does not import the infrastructure;
- does not depend on an external technical library when this can be avoided.

The domain must be testable without a server, files, network, or interface.

---

## 7. The `application/` folder

### Role

The `application/` folder orchestrates use cases.

It answers the question:

> “What happens when the user requests this action?”

It contains:

- commands;
- queries;
- use cases;
- orchestrators;
- action handlers;
- coordination between the domain and the ports.

### Commands / queries distinction

| Type | Purpose | Modifies data |
|---|---|---|
| Command | Perform an action | Yes |
| Query | Read or calculate information | No |

Examples:

| Command | Query |
|---|---|
| Apply a configuration | Read the current configuration |
| Run an analysis | Get the result of an analysis |
| Export a report | List available items |
| Purge data | Consult a history |

### Example

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Rule

`application/` does not contain:

- terminal output;
- a Textual interface;
- Rich commands;
- direct database access;
- direct calls to external tools.

It coordinates, but does not implement technical details.

---

## 8. The `ports/` folder

### Role

The `ports/` folder defines the **contracts** expected by the application.

A port describes **what the application needs**, without imposing how it must be implemented.

It generally contains:

- `Protocol` definitions;
- abstract `ABC` classes;
- repository interfaces;
- export interfaces;
- probe interfaces;
- external service interfaces;
- storage interfaces.

### Example

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Role |
|---|---|
| `Repository` | Read or store data |
| `Exporter` | Produce output in a given format |
| `Probe` | Collect system or network information |
| `Storage` | Manage a persistence backend |

### Conceptual example

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

This contract says:

> “The application needs an object capable of exporting a report.”

It does not say:

- whether the export will be in Markdown;
- whether the export will be in JSON;
- whether the file will be written locally;
- whether the export will be sent over the network.

Those choices belong to `infrastructure/`.

### Rule

Ports are contracts, not implementations.

They must not contain:

- complex business logic;
- disk access;
- network calls;
- concrete implementations;
- direct dependencies on external libraries.

---

## 9. The `infrastructure/` folder

### Role

The `infrastructure/` folder contains the **concrete implementations** of the ports.

It is the layer that communicates with the outside world.

It may contain:

- file access;
- database access;
- Markdown, JSON, CSV, or other exports;
- logging;
- network calls;
- system probes;
- controlled execution of external tools;
- adapters for third-party libraries;
- repository implementations;
- storage implementations.

### Example

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

| Element | Role |
|---|---|
| `sqlite_repository.py` | Implements a repository using SQLite |
| `json_file_repository.py` | Implements a repository using JSON files |
| `markdown_exporter.py` | Exports a report as Markdown |
| `json_exporter.py` | Exports a report as JSON |
| `process_probe.py` | Collects information about processes |
| `filesystem_probe.py` | Collects information about the file system |
| `structured_logger.py` | Produces structured logs |

### Rule

`infrastructure/` is the only layer allowed to directly access:

- the file system;
- the network;
- SQLite;
- external libraries;
- system tools;
- subprocesses, when necessary and controlled.

This centralization facilitates:

- testing;
- security auditing;
- replacing a backend;
- limiting side effects.

---

## 10. The `interfaces/` folder

### Role

The `interfaces/` folder contains the entry points visible to the user.

It clearly separates:

- the CLI;
- the TUI;
- possible future web or API interfaces.

### Structure

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

| Interface | Technology | Role |
|---|---|---|
| `cli/` | Rich | Command-line interface |
| `tui/` | Textual | Interactive terminal interface |

### CLI

The CLI is the command-line interface.

It allows users to:

- launch the application;
- run a specific action;
- display a result;
- automate a task;
- integrate the tool into a script;
- use the application remotely over SSH.

### TUI

The TUI is the interactive terminal interface.

It allows users to:

- navigate through features;
- view information;
- perform actions;
- consult results;
- use the application without memorizing every command.

### Rule

Interfaces do not contain business logic.

They:

- receive a user intention;
- call a use case in `application/`;
- display the result;
- translate errors into understandable messages.

They must not:

- call the infrastructure directly;
- execute subprocesses;
- access files directly;
- contain business rules;
- duplicate logic from `application/`.

---

## 11. The `plugins/` folder

### Role

The `plugins/` folder is reserved for **built-in extensions**.

It allows features to be added without overloading the project core.

For example, a plugin may:

- add an export format;
- add a probe;
- add a command;
- add a TUI screen;
- add an external integration;
- add an optional capability.

### Principle

A plugin must follow the same rules as the rest of the project:

- it does not bypass the ports;
- it does not directly modify the domain;
- it exposes its features through clear contracts;
- it remains disableable without breaking the application.

### Possible structure

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Rule

A plugin is an extension, not a back door.

It must follow the overall architecture and must not create circular dependencies with the project core.

---

## 12. The `shared/` folder

### Role

The `shared/` folder contains cross-cutting utilities that belong neither to the domain, nor to the application, nor to the infrastructure.

It groups reusable generic functions.

It may contain:

- parsing;
- networking utilities;
- formatting;
- text manipulation;
- date helpers;
- path helpers;
- generic validation utilities;
- serialization helpers.

### Example

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Folder | Role |
|---|---|
| `parsing/` | Parsing of text, JSON, YAML, or other formats |
| `network/` | Generic networking utilities |
| `formatting/` | Formatting of values, dates, sizes, or tables |
| `utils/` | Cross-cutting utility functions |

### Rule

`shared/` must not become a catch-all folder.

A utility belongs in `shared/` only if it is:

- reusable;
- generic;
- independent of a specific use case;
- useful to several layers.

---

## 13. Responsibility summary

| Folder | Main role | May depend on | Must not depend on |
|---|---|---|---|
| `app/` | Assemble and start the application | All layers | — |
| `core/` | Vocabulary, constants, enums, and exceptions | `shared/` if needed | `infrastructure/`, `interfaces/` |
| `domain/` | Pure business logic | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Orchestrate use cases | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Define contracts | `domain/` if needed | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Implement ports and communicate with the outside world | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Interact with the user | `application/`, `core/` | `infrastructure/` directly |
| `plugins/` | Add extensions | Depending on extension type | Bypassing the architecture |
| `shared/` | Cross-cutting utilities | No business layer | Specific business logic |

---

## 14. Example of an action flow

Consider a user requesting the export of a report as Markdown.

```text
1. The user runs a CLI command.

2. interfaces/cli/
   Receives the command and its options.

3. interfaces/cli/
   Calls the corresponding use case in application/.

4. application/
   Validates the intention and prepares the action.

5. application/
   Uses the domain to build or validate the report.

6. application/
   Requests an export through the ReportExporter port.

7. infrastructure/
   Provides the MarkdownExporter implementation.

8. infrastructure/
   Writes the Markdown file to disk.

9. interfaces/cli/
   Displays the result to the user.
```

Simplified diagram:

```text
CLI
 ↓
Application
 ↓
Domain
 ↓
Exporter Port
 ↓
Markdown Infrastructure
 ↓
Markdown File
```

---

## 15. Why this architecture?

### Readability

Each folder has a single role, making it easier to find where to add or fix a feature.

### Testability

The domain can be tested without an interface, database, or network access.

### Maintainability

A change to the interface, storage, or an external tool must not require rewriting the business logic.

### Security

Sensitive access — files, network, subprocesses, databases — is concentrated in `infrastructure/`. This makes it easier to audit and control.

### Evolvability

You can add:

- a new interface;
- a new export format;
- a new storage backend;
- a new plugin;
- a new system probe;

without modifying the business core.

### Portability

The application can evolve toward other environments, systems, or interaction modes without being tied to a specific technology.

---

## 16. Rules to remember

- The domain is pure.
- The application orchestrates.
- Ports declare needs.
- Infrastructure implements.
- Interfaces display and collect.
- `app/` assembles.
- `core/` and `shared/` provide cross-cutting vocabulary and utilities.
- Plugins extend without bypassing the architecture.

In one sentence:

> **The application separates what it does, how it does it, and how the user uses it.**
