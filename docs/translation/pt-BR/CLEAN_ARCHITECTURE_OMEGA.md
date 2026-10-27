# Arquitetura do projeto — Clean Architecture

**Idiomas:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/CLEAN_ARCHITECTURE_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/CLEAN_ARCHITECTURE_OMEGA.md)

Este documento explica como o projeto está organizado, por que essa organização foi escolhida e o que cada pasta contém. Ele se destina tanto aos visitantes que querem entender o funcionamento da aplicação quanto aos desenvolvedores que desejam contribuir com ela ou mantê-la.

A aplicação segue uma **Clean Architecture**: o núcleo do software é isolado dos detalhes técnicos, das interfaces de usuário e das dependências externas. Essa separação torna o projeto mais fácil de ler, testar, manter e evoluir.

---

## 1. Princípio geral

A aplicação é dividida em camadas, cada uma com um papel preciso.

A ideia central é simples:

```text
A interface solicita uma ação.
A aplicação orquestra essa ação.
O domínio aplica as regras de negócio.
Os ports definem do que a aplicação precisa.
A infraestrutura fornece as implementações concretas.
```

Assim, a lógica importante do projeto não depende diretamente:

- do terminal;
- da interface gráfica;
- de um banco de dados;
- da rede;
- do sistema de arquivos;
- de uma biblioteca externa;
- de uma ferramenta do sistema.

Essa independência permite substituir uma parte do software sem reescrever todo o resto.

---

## 2. Visão geral

```text
[PROJECT_NAME]/
└── src/
    └── [project_name]/
        ├── app/              Bootstrap, ciclo de vida e injeção de dependências
        ├── core/             Capacidades, enums e exceções transversais
        ├── domain/           Lógica de negócio pura
        ├── application/      Casos de uso: commands e queries
        ├── infrastructure/   Backends, armazenamento, exportações, logs, sondas do sistema…
        ├── ports/            Contratos Protocol / ABC
        ├── interfaces/       CLI e TUI
        ├── plugins/          Extensões integradas
        └── shared/           Parsing, rede, formatação e utilitários transversais
```

---

## 3. Diagrama de dependências

As dependências devem sempre seguir a mesma direção:

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

Na prática:

- `interfaces/` pode chamar `application/`.
- `application/` pode chamar `domain/` e usar os contratos definidos em `ports/`.
- `domain/` não depende nem de `application/`, nem de `infrastructure/`, nem de `interfaces/`.
- `infrastructure/` implementa os contratos definidos em `ports/`.
- `app/` monta as camadas e fornece as dependências necessárias.

Regra essencial:

> O domínio nunca conhece a infraestrutura.  
> A infraestrutura conhece os ports, mas o domínio não conhece a infraestrutura.

---

## 4. A pasta `app/`

### Papel

A pasta `app/` é o **ponto de montagem** da aplicação.

Ela contém:

- a inicialização da aplicação;
- o ciclo de vida;
- o contêiner de injeção de dependências;
- a construção dos objetos necessários ao funcionamento;
- a escolha das implementações concretas;
- a inicialização da configuração;
- a ligação entre as camadas.

### Exemplos de responsabilidades

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Arquivo | Papel |
|---|---|
| `bootstrap.py` | Inicia a aplicação e escolhe a interface a ser lançada |
| `container.py` | Cria e conecta as dependências |
| `lifecycle.py` | Gerencia inicialização, encerramento e limpeza |

### Regra

`app/` não contém lógica de negócio.

Ela não decide:

- o que é uma regra de negócio;
- como um dado deve ser calculado;
- como uma requisição deve ser analisada;
- como um arquivo deve ser exportado.

Ela apenas monta os componentes existentes.

---

## 5. A pasta `core/`

### Papel

A pasta `core/` contém o **vocabulário transversal** do projeto.

Ela agrupa elementos compartilhados por várias camadas, mas que não são, por si só, regras de negócio.

Ela pode conter:

- capacidades;
- enumerações;
- constantes;
- exceções transversais;
- tipos comuns;
- informações de plataforma;
- definições de níveis ou de estados.

### Exemplo

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Arquivo | Papel |
|---|---|
| `capabilities.py` | Descreve as capacidades disponíveis ou ativáveis |
| `constants.py` | Contém as constantes do projeto |
| `enums.py` | Define os estados, tipos ou níveis possíveis |
| `exceptions.py` | Define os erros transversais |

### Regra

`core/` deve permanecer leve e estável.

Ela não deve conter:

- lógica de negócio complexa;
- chamadas de rede;
- acesso a disco;
- código de interface de usuário;
- dependência direta de bibliotecas externas.

---

## 6. A pasta `domain/`

### Papel

A pasta `domain/` é o **coração do projeto**.

Ela contém a lógica de negócio pura: as regras, os conceitos e os cálculos que definem de fato o que a aplicação faz.

Ela pode conter:

- entidades;
- value objects;
- políticas;
- regras de negócio;
- serviços de domínio;
- cálculos;
- validações de negócio;
- modelos de dados de negócio.

### Exemplo

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Elemento | Papel |
|---|---|
| Entidade | Objeto de negócio com identidade |
| Value object | Valor imutável e validado |
| Política | Regra de negócio reutilizável |
| Serviço de domínio | Lógica de negócio que não pertence a uma única entidade |

### Regras estritas

A pasta `domain/`:

- não faz nenhum acesso a disco;
- não faz nenhuma chamada de rede;
- não executa comandos do sistema;
- não acessa banco de dados;
- não importa a interface de usuário;
- não importa a infraestrutura;
- não depende de biblioteca técnica externa quando isso pode ser evitado.

O domínio deve poder ser testado sem servidor, sem arquivos, sem rede e sem interface.

---

## 7. A pasta `application/`

### Papel

A pasta `application/` orquestra os casos de uso.

Ela responde à pergunta:

> “O que acontece quando o usuário solicita esta ação?”

Ela contém:

- os commands;
- as queries;
- os casos de uso;
- os orquestradores;
- os handlers de ações;
- a coordenação entre o domínio e os ports.

### Distinção commands / queries

| Tipo | Objetivo | Modifica os dados |
|---|---|---|
| Command | Executar uma ação | Sim |
| Query | Ler ou calcular uma informação | Não |

Exemplos:

| Command | Query |
|---|---|
| Aplicar uma configuração | Ler a configuração atual |
| Iniciar uma análise | Obter o resultado de uma análise |
| Exportar um relatório | Listar os itens disponíveis |
| Limpar dados | Consultar um histórico |

### Exemplo

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Regra

`application/` não contém:

- exibição no terminal;
- interface Textual;
- comandos Rich;
- acesso direto a banco de dados;
- chamadas diretas a ferramentas externas.

Ela coordena, mas não implementa os detalhes técnicos.

---

## 8. A pasta `ports/`

### Papel

A pasta `ports/` define os **contratos** esperados pela aplicação.

Um port descreve **do que a aplicação precisa**, sem impor como isso deve ser implementado.

Ela contém geralmente:

- `Protocol`;
- classes abstratas `ABC`;
- interfaces de repositórios;
- interfaces de exportação;
- interfaces de sondas;
- interfaces de serviços externos;
- interfaces de armazenamento.

### Exemplo

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Papel |
|---|---|
| `Repository` | Ler ou armazenar dados |
| `Exporter` | Produzir uma saída em um formato dado |
| `Probe` | Coletar uma informação do sistema ou da rede |
| `Storage` | Gerenciar um backend de persistência |

### Exemplo conceitual

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Esse contrato diz:

> “A aplicação precisa de um objeto capaz de exportar um relatório.”

Ele não diz:

- se a exportação será em Markdown;
- se a exportação será em JSON;
- se o arquivo será gravado localmente;
- se a exportação será enviada pela rede.

Essas escolhas pertencem a `infrastructure/`.

### Regra

Os ports são contratos, não implementações.

Eles não devem conter:

- lógica de negócio complexa;
- acesso a disco;
- chamadas de rede;
- implementação concreta;
- dependência direta de bibliotecas externas.

---

## 9. A pasta `infrastructure/`

### Papel

A pasta `infrastructure/` contém as **implementações concretas** dos ports.

É a camada que se comunica com o mundo exterior.

Ela pode conter:

- acesso a arquivos;
- acesso a banco de dados;
- exportações em Markdown, JSON, CSV ou outros;
- logging;
- chamadas de rede;
- sondas do sistema;
- execução controlada de ferramentas externas;
- adaptadores para bibliotecas de terceiros;
- implementações de repositórios;
- implementações de armazenamento.

### Exemplo

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

| Elemento | Papel |
|---|---|
| `sqlite_repository.py` | Implementa um repositório com SQLite |
| `json_file_repository.py` | Implementa um repositório com arquivos JSON |
| `markdown_exporter.py` | Exporta um relatório em Markdown |
| `json_exporter.py` | Exporta um relatório em JSON |
| `process_probe.py` | Coleta informações sobre os processos |
| `filesystem_probe.py` | Coleta informações sobre o sistema de arquivos |
| `structured_logger.py` | Produz logs estruturados |

### Regra

`infrastructure/` é a única camada autorizada a acessar diretamente:

- o sistema de arquivos;
- a rede;
- o SQLite;
- as bibliotecas externas;
- as ferramentas do sistema;
- os subprocessos, quando necessários e controlados.

Essa centralização facilita:

- os testes;
- a auditoria de segurança;
- a substituição de um backend;
- a limitação de efeitos colaterais.

---

## 10. A pasta `interfaces/`

### Papel

A pasta `interfaces/` contém os pontos de entrada visíveis para o usuário.

Ela separa claramente:

- a CLI;
- a TUI;
- eventuais futuras interfaces web ou API.

### Estrutura

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

| Interface | Tecnologia | Papel |
|---|---|---|
| `cli/` | Rich | Interface de linha de comando |
| `tui/` | Textual | Interface interativa no terminal |

### CLI

A CLI é a interface de linha de comando.

Ela permite:

- iniciar a aplicação;
- executar uma ação precisa;
- exibir um resultado;
- automatizar uma tarefa;
- integrar a ferramenta em um script;
- usar a aplicação remotamente via SSH.

### TUI

A TUI é a interface interativa no terminal.

Ela permite:

- navegar entre as funcionalidades;
- visualizar informações;
- executar ações;
- consultar resultados;
- usar a aplicação sem decorar todos os comandos.

### Regra

As interfaces não contêm lógica de negócio.

Elas:

- recebem uma intenção do usuário;
- chamam um caso de uso em `application/`;
- exibem o resultado;
- traduzem os erros em mensagens compreensíveis.

Elas não devem:

- chamar diretamente a infraestrutura;
- executar subprocessos;
- acessar arquivos diretamente;
- conter regras de negócio;
- duplicar a lógica de `application/`.

---

## 11. A pasta `plugins/`

### Papel

A pasta `plugins/` é reservada às **extensões integradas**.

Ela permite adicionar funcionalidades sem sobrecarregar o núcleo do projeto.

Um plugin pode, por exemplo:

- adicionar um formato de exportação;
- adicionar uma sonda;
- adicionar um comando;
- adicionar uma tela TUI;
- adicionar uma integração externa;
- adicionar uma capacidade opcional.

### Princípio

Um plugin deve respeitar as mesmas regras que o restante do projeto:

- não contorna os ports;
- não modifica diretamente o domínio;
- expõe suas funcionalidades por meio de contratos claros;
- pode ser desativado sem quebrar a aplicação.

### Estrutura possível

```text
plugins/
└── [plugin_name]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Regra

Um plugin é uma extensão, não uma porta dos fundos.

Ele deve respeitar a arquitetura geral e não deve criar dependências circulares com o núcleo do projeto.

---

## 12. A pasta `shared/`

### Papel

A pasta `shared/` contém utilitários transversais que não pertencem nem ao domínio, nem à aplicação, nem à infraestrutura.

Ela agrupa funções genéricas reutilizáveis.

Ela pode conter:

- parsing;
- utilitários de rede;
- formatação;
- manipulação de texto;
- auxiliares de datas;
- auxiliares de caminhos;
- utilitários genéricos de validação;
- auxiliares de serialização.

### Exemplo

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Pasta | Papel |
|---|---|
| `parsing/` | Análise de texto, JSON, YAML ou outros formatos |
| `network/` | Utilitários de rede genéricos |
| `formatting/` | Formatação de valores, datas, tamanhos ou tabelas |
| `utils/` | Funções utilitárias transversais |

### Regra

`shared/` não deve virar uma pasta de despejo.

Um utilitário só deve ir para `shared/` se for:

- reutilizável;
- genérico;
- independente de um caso de uso específico;
- útil para várias camadas.

---

## 13. Resumo das responsabilidades

| Pasta | Papel principal | Pode depender de | Não deve depender de |
|---|---|---|---|
| `app/` | Montar e iniciar a aplicação | Todas as camadas | — |
| `core/` | Vocabulário, constantes, enums e exceções | `shared/` se necessário | `infrastructure/`, `interfaces/` |
| `domain/` | Lógica de negócio pura | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Orquestrar os casos de uso | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Definir os contratos | `domain/` se necessário | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Implementar os ports e se comunicar com o exterior | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Interagir com o usuário | `application/`, `core/` | `infrastructure/` diretamente |
| `plugins/` | Adicionar extensões | Conforme o tipo de extensão | Contornar a arquitetura |
| `shared/` | Utilitários transversais | Nenhuma camada de negócio | Lógica de negócio específica |

---

## 14. Exemplo de fluxo de uma ação

Considere um usuário que solicita a exportação de um relatório em Markdown.

```text
1. O usuário executa um comando CLI.

2. interfaces/cli/
   Recebe o comando e suas opções.

3. interfaces/cli/
   Chama o caso de uso correspondente em application/.

4. application/
   Valida a intenção e prepara a ação.

5. application/
   Usa o domínio para construir ou validar o relatório.

6. application/
   Solicita uma exportação por meio do port ReportExporter.

7. infrastructure/
   Fornece a implementação MarkdownExporter.

8. infrastructure/
   Grava o arquivo Markdown no disco.

9. interfaces/cli/
   Exibe o resultado ao usuário.
```

Diagrama simplificado:

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
Arquivo Markdown
```

---

## 15. Por que esta arquitetura?

### Legibilidade

Cada pasta tem um papel único, o que facilita encontrar onde adicionar ou corrigir uma funcionalidade.

### Testabilidade

O domínio pode ser testado sem interface, sem banco de dados e sem acesso à rede.

### Manutenibilidade

Uma mudança na interface, no armazenamento ou em uma ferramenta externa não deve exigir a reescrita da lógica de negócio.

### Segurança

Os acessos sensíveis — arquivos, rede, subprocessos, bancos de dados — ficam concentrados em `infrastructure/`. Isso facilita a auditoria e o controle.

### Evolução

É possível adicionar:

- uma nova interface;
- um novo formato de exportação;
- um novo backend de armazenamento;
- um novo plugin;
- uma nova sonda do sistema;

sem modificar o núcleo de negócio.

### Portabilidade

A aplicação pode evoluir para outros ambientes, sistemas ou modos de interação sem ficar presa a uma tecnologia específica.

---

## 16. Regras a lembrar

- O domínio é puro.
- A aplicação orquestra.
- Os ports declaram as necessidades.
- A infraestrutura implementa.
- As interfaces exibem e coletam.
- `app/` monta.
- `core/` e `shared/` fornecem o vocabulário e os utilitários transversais.
- Os plugins estendem sem contornar a arquitetura.

Em uma frase:

> **A aplicação separa o que ela faz, como ela faz e como o usuário a utiliza.**
