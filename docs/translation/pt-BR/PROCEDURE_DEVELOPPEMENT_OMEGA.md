# Procedimento de desenvolvimento — [PROJECT_NAME]

**Idiomas:**
<img src="https://flagcdn.com/w20/fr.png" alt="France" style="height:14px;"> [Français](../../PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/gb.png" alt="English" style="height:14px;"> [English](../en/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/es.png" alt="Español" style="height:14px;"> [Español](../es/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/br.png" alt="Português (Brasil)" style="height:14px;"> [Português (Brasil)](PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/it.png" alt="Italiano" style="height:14px;"> [Italiano](../it/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/de.png" alt="Deutsch" style="height:14px;"> [Deutsch](../de/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/nl.png" alt="Nederlands" style="height:14px;"> [Nederlands](../nl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/pl.png" alt="Polski" style="height:14px;"> [Polski](../pl/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ru.png" alt="Русский" style="height:14px;"> [Русский](../ru/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/cn.png" alt="中文" style="height:14px;"> [中文](../zh-CN/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/vn.png" alt="Tiếng Việt" style="height:14px;"> [Tiếng Việt](../vi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/th.png" alt="ไทย" style="height:14px;"> [ไทย](../th/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/id.png" alt="Bahasa Indonesia" style="height:14px;"> [Bahasa Indonesia](../id/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/jp.png" alt="日本語" style="height:14px;"> [日本語](../ja/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/kr.png" alt="한국어" style="height:14px;"> [한국어](../ko/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/in.png" alt="हिन्दी" style="height:14px;"> [हिन्दी](../hi/PROCEDURE_DEVELOPPEMENT_OMEGA.md) · <img src="https://flagcdn.com/w20/ae.png" alt="العربية" style="height:14px;"> [العربية](../ar/PROCEDURE_DEVELOPPEMENT_OMEGA.md)

| Campo | Valor |
|---|---|
| Projeto | [PROJECT_NAME] |
| Versão alvo | [TARGET_VERSION] |
| Responsável | [NOME] |
| Data de criação | [AAAA-MM-DD] |
| Última atualização | [AAAA-MM-DD] |
| Status geral | Rascunho / Em andamento / Validado / Em produção |
| Ambiente alvo | [Linux / Debian / Servidor / Estação de trabalho] |
| Linguagem principal | [Python / Bash / Lua / Outra] |
| Repositório | [URL_OU_CAMINHO] |

## Regras transversais

- [ ] Nenhum código é escrito antes da validação do plano final.
- [ ] Toda decisão importante é documentada.
- [ ] Toda anomalia é registrada.
- [ ] Toda correção é testada.
- [ ] Toda mudança de comportamento é documentada.
- [ ] Os backups são feitos antes de qualquer intervenção em produção.
- [ ] A IA analisa e propõe; o humano decide, valida e implanta.
- [ ] O código permanece alinhado com a documentação final.

## Acompanhamento global das fases

| Fase | Ator | Entregável principal | Status | Data de validação |
|---:|---|---|---|---|
| 1 | Humano | Necessidades e concepção | [ ] | [AAAA-MM-DD] |
| 2 | Humano | Esboço de arquitetura e plano preliminar | [ ] | [AAAA-MM-DD] |
| 3 | IA | Análise, efeitos colaterais, plano final | [ ] | [AAAA-MM-DD] |
| 4 | Humano | Núcleo do projeto codificado | [ ] | [AAAA-MM-DD] |
| 5 | IA | Auditoria do código, correções e testes | [ ] | [AAAA-MM-DD] |
| 6 | Humano | Testes reais em produção | [ ] | [AAAA-MM-DD] |
| 7 | IA | Plano de correção e codificação final | [ ] | [AAAA-MM-DD] |
| 8 | Humano | Testes finais | [ ] | [AAAA-MM-DD] |
| 9 | Humano | Rascunho da documentação | [ ] | [AAAA-MM-DD] |
| 10 | IA | Documentação final | [ ] | [AAAA-MM-DD] |
| 11 | Humano | Implantação em produção | [ ] | [AAAA-MM-DD] |

---

# Fase 1 — Reflexão, necessidades, uso e concepção

**Ator: Humano**  
**Objetivo:** definir o problema, os usuários, o uso real, as restrições e os limites do projeto.

## 1. Problema inicial

- Problema identificado: [A COMPLETAR]
- Situação atual: [A COMPLETAR]
- Consequência do problema: [A COMPLETAR]
- Objetivo do projeto: [A COMPLETAR]

## 2. Usuários-alvo

| Usuário | Necessidade principal | Nível técnico | Uso previsto |
|---|---|---|---|
| [Usuário 1] | [A COMPLETAR] | [Iniciante / Técnico / Especialista] | [A COMPLETAR] |
| [Usuário 2] | [A COMPLETAR] | [Iniciante / Técnico / Especialista] | [A COMPLETAR] |

## 3. Cenários de uso

### Cenário nominal

- Contexto: [A COMPLETAR]
- Ação do usuário: [A COMPLETAR]
- Resultado esperado: [A COMPLETAR]

### Cenário limite

- Contexto: [A COMPLETAR]
- Ação do usuário: [A COMPLETAR]
- Resultado esperado: [A COMPLETAR]

### Cenário de erro

- Contexto: [A COMPLETAR]
- Ação do usuário: [A COMPLETAR]
- Resultado esperado: [A COMPLETAR]

### Cenário proibido ou perigoso

- Contexto: [A COMPLETAR]
- Comportamento esperado: [Recusa / Aviso / Bloqueio / Registro em log]
- Justificativa: [A COMPLETAR]

## 4. Funcionalidades

### Obrigatórias

- [ ] [Funcionalidade 1]
- [ ] [Funcionalidade 2]
- [ ] [Funcionalidade 3]

### Úteis, mas adiáveis

- [ ] [Funcionalidade 1]
- [ ] [Funcionalidade 2]

### Opcionais

- [ ] [Funcionalidade 1]

### Excluídas

- [ ] [Funcionalidade excluída]
- Justificativa: [A COMPLETAR]

## 5. Restrições

| Área | Restrição | Prioridade |
|---|---|---|
| Sistema | [Linux / Debian / Versão] | [Alta / Média / Baixa] |
| Linguagem | [Python / Bash / Lua] | [Alta / Média / Baixa] |
| Dependências | [A COMPLETAR] | [Alta / Média / Baixa] |
| Desempenho | [A COMPLETAR] | [Alta / Média / Baixa] |
| Segurança | [A COMPLETAR] | [Alta / Média / Baixa] |
| Compatibilidade | [A COMPLETAR] | [Alta / Média / Baixa] |
| Manutenção | [A COMPLETAR] | [Alta / Média / Baixa] |
| Implantação | [A COMPLETAR] | [Alta / Média / Baixa] |

## 6. Riscos identificados

| Risco | Impacto | Probabilidade | Medida de prevenção |
|---|---|---|---|
| [Risco 1] | [Baixo / Médio / Alto] | [Baixa / Média / Alta] | [A COMPLETAR] |
| [Risco 2] | [Baixo / Médio / Alto] | [Baixa / Média / Alta] | [A COMPLETAR] |

## 7. Decisões tomadas

| ID | Decisão | Justificativa | Data |
|---:|---|---|---|
| D-001 | [A COMPLETAR] | [A COMPLETAR] | [AAAA-MM-DD] |
| D-002 | [A COMPLETAR] | [A COMPLETAR] | [AAAA-MM-DD] |

## 8. Questões em aberto

- [ ] [Questão 1]
- [ ] [Questão 2]

## Validação da fase 1

- [ ] O problema está claramente formulado.
- [ ] Os usuários estão identificados.
- [ ] Os principais cenários de uso estão descritos.
- [ ] As funcionalidades obrigatórias estão listadas.
- [ ] Os limites do projeto estão explícitos.
- [ ] As restrições técnicas são conhecidas.
- [ ] Os principais riscos estão identificados.

**Status:** [ ] Rascunho / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 2 — Esboço, componentes principais e plano de desenvolvimento

**Ator: Humano**  
**Objetivo:** transformar as necessidades em uma arquitetura lógica e em um plano de desenvolvimento aplicável.

## 1. Componentes principais

| Componente | Responsabilidade | Não deve fazer | Prioridade |
|---|---|---|---|
| Interface / CLI | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Núcleo de negócio | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Configuração | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Modelos de dados | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Serviços | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Armazenamento | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Exportação | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Logs | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Segurança | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| Testes | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |

## 2. Fluxo principal

```text
[Entrada do usuário]
    → [Interface]
    → [Validação]
    → [Núcleo de negócio]
    → [Serviços / Módulos]
    → [Resultado]
    → [Saída / Armazenamento / Logs]
```

## 3. Módulos previstos

| Módulo | Papel | Dependências | Prioridade |
|---|---|---|---|
| [module_1] | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| [module_2] | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |
| [module_3] | [A COMPLETAR] | [A COMPLETAR] | [Alta / Média / Baixa] |

## 4. Árvore preliminar

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

## 5. Dependências previstas

| Dependência | Uso | Versão mínima | Justificativa |
|---|---|---|---|
| [Dependência 1] | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |
| [Dependência 2] | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |

## 6. Divisão do desenvolvimento

| Fase | Conteúdo | Prioridade | Estimativa |
|---:|---|---|---|
| 1 | Base: estrutura, configuração, erros, logs | [Alta / Média] | [Duração] |
| 2 | Modelos e contratos | [Alta / Média] | [Duração] |
| 3 | Núcleo de negócio | [Alta / Média] | [Duração] |
| 4 | Interface / CLI | [Alta / Média] | [Duração] |
| 5 | Armazenamento / exportação | [Alta / Média] | [Duração] |
| 6 | Testes | [Alta / Média] | [Duração] |
| 7 | Documentação e empacotamento | [Alta / Média] | [Duração] |

## Validação da fase 2

- [ ] Os componentes principais estão identificados.
- [ ] Cada módulo tem uma responsabilidade clara.
- [ ] Os fluxos principais estão descritos.
- [ ] A árvore preliminar está definida.
- [ ] As principais dependências estão identificadas.
- [ ] A ordem de desenvolvimento está definida.
- [ ] Nenhum desenvolvimento foi iniciado.

**Status:** [ ] Rascunho / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 3 — Análise da IA, efeitos colaterais e plano final

**Ator: IA**  
**Objetivo:** analisar os documentos produzidos pelo humano, identificar os riscos e produzir um plano final aplicável.

## 1. Documentos analisados

- [ ] `PROJECT_00_NEEDS_AND_DESIGN.md`
- [ ] `PROJECT_01_ARCHITECTURE_DRAFT.md`
- [ ] `PROJECT_02_DEVELOPMENT_PLAN_DRAFT.md`
- [ ] [Outro documento]

## 2. Prompt de análise da IA

```text
Analise este projeto sem escrever código.

1. Detecte as incoerências.
2. Detecte as funções ausentes.
3. Detecte as responsabilidades mal posicionadas.
4. Identifique os possíveis efeitos colaterais.
5. Identifique os casos de falha.
6. Identifique os riscos de segurança.
7. Identifique os problemas de compatibilidade.
8. Proponha uma estrutura de projeto mais robusta.
9. Proponha um plano de desenvolvimento final.
10. Indique os pontos que devem permanecer sob decisão humana.
```

## 3. Incoerências detectadas

| ID | Descrição | Impacto | Proposta | Decisão humana |
|---:|---|---|---|---|
| A-001 | [A COMPLETAR] | [Baixo / Médio / Alto] | [A COMPLETAR] | [Aceita / Recusada / Adiada] |
| A-002 | [A COMPLETAR] | [Baixo / Médio / Alto] | [A COMPLETAR] | [Aceita / Recusada / Adiada] |

## 4. Efeitos colaterais identificados

| ID | Efeito colateral | Gatilho | Impacto | Prevenção | Status |
|---:|---|---|---|---|---|
| SE-001 | [A COMPLETAR] | [A COMPLETAR] | [Baixo / Médio / Alto] | [A COMPLETAR] | [Aberto / Tratado / Aceito] |
| SE-002 | [A COMPLETAR] | [A COMPLETAR] | [Baixo / Médio / Alto] | [A COMPLETAR] | [Aberto / Tratado / Aceito] |

## 5. Casos de falha a antecipar

| Caso | Comportamento esperado | Mensagem / log esperado | Teste associado |
|---|---|---|---|
| Arquivo ausente | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |
| Permissão negada | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |
| Rede indisponível | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |
| Entrada inválida | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |
| Interrupção pelo usuário | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |
| Dados corrompidos | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] |

## 6. Riscos de segurança

| Risco | Cenário | Medida | Prioridade |
|---|---|---|---|
| [Risco 1] | [A COMPLETAR] | [A COMPLETAR] | [P0 / P1 / P2] |
| [Risco 2] | [A COMPLETAR] | [A COMPLETAR] | [P0 / P1 / P2] |

## 7. Plano de desenvolvimento final

| Fase | Objetivo | Entregáveis | Critérios de conclusão | Dependências |
|---:|---|---|---|---|
| 1 | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [Nenhuma] |
| 2 | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [Fase 1] |
| 3 | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [Fase 2] |

## Validação da fase 3

- [ ] As incoerências foram tratadas ou documentadas.
- [ ] Os efeitos colaterais estão identificados.
- [ ] Os casos de falha estão antecipados.
- [ ] Os riscos de segurança foram tratados.
- [ ] O plano final foi validado pelo humano.
- [ ] As decisões finais estão registradas.

**Status:** [ ] Rascunho / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 4 — Codificação do núcleo do projeto

**Ator: Humano**  
**Objetivo:** desenvolver o núcleo funcional sem adicionar funcionalidades fora do escopo.

## 1. Escopo da codificação

- [ ] Estrutura do projeto
- [ ] Ambiente virtual
- [ ] Dependências
- [ ] Configuração
- [ ] Modelos de dados
- [ ] Exceções
- [ ] Logging
- [ ] Serviços de negócio
- [ ] Núcleo de negócio
- [ ] Testes unitários
- [ ] CLI / interface
- [ ] Integração

## 2. Ordem de implementação

| Ordem | Elemento | Arquivo / módulo | Status | Commit |
|---:|---|---|---|---|
| 1 | [Elemento] | [caminho] | [ ] | [hash] |
| 2 | [Elemento] | [caminho] | [ ] | [hash] |
| 3 | [Elemento] | [caminho] | [ ] | [hash] |

## 3. Regras de commit

- Um commit = uma única intenção.
- Não misturar funcionalidade, correção e refatoração.
- Mensagem recomendada:

```text
[type]: [descrição curta]

[type] = feat, fix, refactor, test, docs, chore
```

Exemplo:

```text
feat: adiciona o carregamento e a validação da configuração
```

## 4. Testes iniciais

| Teste | Objetivo | Comando | Resultado esperado | Status |
|---|---|---|---|---|
| [Teste 1] | [A COMPLETAR] | [comando] | [A COMPLETAR] | [ ] |
| [Teste 2] | [A COMPLETAR] | [comando] | [A COMPLETAR] | [ ] |

## Validação da fase 4

- [ ] O núcleo de negócio funciona.
- [ ] As principais entradas são validadas.
- [ ] Os principais erros são tratados.
- [ ] Os testes unitários passam.
- [ ] O projeto inicia em modo básico.
- [ ] Nenhuma funcionalidade fora do escopo foi adicionada.

**Status:** [ ] Em andamento / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 5 — Análise do código, correção e testes pela IA

**Ator: IA**  
**Objetivo:** detectar defeitos, efeitos colaterais e riscos antes dos testes reais.

## 1. Prompt de auditoria da IA

```text
Analise o código sem reescrevê-lo por completo.

1. Verifique a conformidade com o plano de desenvolvimento.
2. Detecte os bugs prováveis.
3. Detecte os efeitos colaterais.
4. Detecte os vazamentos de recursos.
5. Detecte os erros não tratados.
6. Detecte as entradas não validadas.
7. Detecte os problemas de segurança.
8. Detecte os problemas de desempenho.
9. Detecte o código morto.
10. Detecte as responsabilidades mal posicionadas.
11. Proponha correções pontuais.
12. Proponha os testes ausentes.
```

## 2. Resultados da auditoria

| ID | Arquivo / função | Constatação | Gravidade | Correção proposta | Status |
|---:|---|---|---|---|---|
| C-001 | [caminho] | [A COMPLETAR] | [Crítica / Maior / Menor] | [A COMPLETAR] | [Aberto / Corrigido / Validado] |
| C-002 | [caminho] | [A COMPLETAR] | [Crítica / Maior / Menor] | [A COMPLETAR] | [Aberto / Corrigido / Validado] |

## 3. Testes adicionados

| Teste | Objetivo | Arquivo de teste | Status |
|---|---|---|---|
| [Teste 1] | [A COMPLETAR] | [caminho] | [ ] |
| [Teste 2] | [A COMPLETAR] | [caminho] | [ ] |

## Validação da fase 5

- [ ] Os bugs críticos foram corrigidos.
- [ ] Os efeitos colaterais foram tratados ou documentados.
- [ ] Os testes unitários passam.
- [ ] Os testes de integração passam.
- [ ] O código está conforme o plano final.
- [ ] As correções foram aplicadas de forma progressiva.

**Status:** [ ] Em andamento / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 6 — Estudo real e testes em produção

**Ator: Humano**  
**Objetivo:** validar o software em condições reais e registrar todas as anomalias.

## 1. Ambiente de teste

| Elemento | Valor |
|---|---|
| Máquina | [A COMPLETAR] |
| Sistema | [A COMPLETAR] |
| Versão do software | [A COMPLETAR] |
| Ambiente | [Produção controlada / Pré-produção / Servidor real] |
| Backup realizado | [Sim / Não] |
| Data do backup | [AAAA-MM-DD] |
| Método de rollback | [A COMPLETAR] |

## 2. Cenários testados

| ID | Cenário | Comando | Resultado esperado | Resultado obtido | Status |
|---:|---|---|---|---|---|
| T-001 | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [OK / KO / Parcial] |
| T-002 | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [OK / KO / Parcial] |

## 3. Grade de observação

| Área | Elemento observado | Resultado | Comentário |
|---|---|---|---|
| Funcional | Função esperada | [OK / KO] | [A COMPLETAR] |
| Interface | Clareza dos comandos | [OK / KO] | [A COMPLETAR] |
| Desempenho | Tempo de execução | [OK / KO] | [A COMPLETAR] |
| Estabilidade | Ausência de travamento inesperado | [OK / KO] | [A COMPLETAR] |
| Erros | Compreensão das mensagens | [OK / KO] | [A COMPLETAR] |
| Logs | Qualidade e utilidade | [OK / KO] | [A COMPLETAR] |
| Segurança | Comportamento seguro | [OK / KO] | [A COMPLETAR] |
| Compatibilidade | Funcionamento no alvo real | [OK / KO] | [A COMPLETAR] |
| Estética | Legibilidade das saídas | [OK / KO] | [A COMPLETAR] |
| Uso real | Fluidez do fluxo de trabalho | [OK / KO] | [A COMPLETAR] |

## 4. Registro de anomalias

| ID | Data | Gravidade | Descrição | Logs | Hipótese | Correção proposta | Status |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [AAAA-MM-DD] | [Crítica / Maior / Menor / Estética] | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [Aberto / Corrigido / Validado] |
| BUG-002 | [AAAA-MM-DD] | [Crítica / Maior / Menor / Estética] | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [A COMPLETAR] | [Aberto / Corrigido / Validado] |

## Validação da fase 6

- [ ] Todos os cenários críticos foram testados.
- [ ] Os bugs estão registrados.
- [ ] Os problemas de ergonomia estão registrados.
- [ ] Os problemas estéticos estão registrados.
- [ ] Nenhum bug crítico bloqueante foi ignorado.

**Status:** [ ] Em andamento / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 7 — Plano de melhoria, correções e codificação final

**Ator: IA**  
**Objetivo:** transformar as anomalias em correções priorizadas e, em seguida, aplicar as alterações de código necessárias.

## 1. Prompt de análise das anomalias

```text
Aqui está o registro dos testes em produção.

1. Classifique as anomalias por gravidade.
2. Agrupe as anomalias relacionadas.
3. Identifique as causas prováveis.
4. Proponha uma correção mínima para cada anomalia.
5. Indique os riscos de regressão.
6. Proponha os testes a adicionar.
7. Proponha melhorias de ergonomia.
8. Proponha melhorias estéticas.
9. Altere apenas o necessário.
10. Preserve os comportamentos validados.
```

## 2. Priorização das anomalias

| Prioridade | Tipo | Anomalias afetadas | Tratamento |
|---|---|---|---|
| P0 | Travamento, perda de dados, vulnerabilidade | [BUG-XXX] | Correção imediata |
| P1 | Funcionalidade incorreta | [BUG-XXX] | Correção antes da validação final |
| P2 | Experiência ruim do usuário | [BUG-XXX] | Correção se razoável |
| P3 | Estética, mensagem, formato | [BUG-XXX] | Correção ou adiamento |
| P4 | Melhoria futura | [BUG-XXX] | Backlog |

## 3. Correções aplicadas

| ID | Anomalia | Correção | Arquivos alterados | Testes adicionados | Risco de regressão | Status |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [A COMPLETAR] | [caminho] | [caminho] | [Baixo / Médio / Alto] | [Aplicado / Validado] |
| FIX-002 | [BUG-XXX] | [A COMPLETAR] | [caminho] | [caminho] | [Baixo / Médio / Alto] | [Aplicado / Validado] |

## Validação da fase 7

- [ ] Cada anomalia tem um status claro.
- [ ] As correções são aplicadas por prioridade.
- [ ] Os testes de não regressão passam.
- [ ] Os comportamentos validados são preservados.
- [ ] Cada correção está documentada.

**Status:** [ ] Em andamento / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 8 — Testes finais

**Ator: Humano**  
**Objetivo:** validar a versão candidata antes da documentação final e da implantação estável em produção.

## 1. Testes de validação

| Teste | Objetivo | Comando | Resultado esperado | Resultado obtido | Status |
|---|---|---|---|---|---|
| Cenário nominal | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |
| Cenário de erro | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |
| Opções da CLI | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |
| Configuração | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |
| Permissões | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |
| Interrupção | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |
| Não regressão | [A COMPLETAR] | [comando] | [A COMPLETAR] | [A COMPLETAR] | [ ] |

## 2. Checklist final

- [ ] O projeto inicia corretamente.
- [ ] Os principais comandos funcionam.
- [ ] Os erros são compreensíveis.
- [ ] Os logs são utilizáveis.
- [ ] Nenhum bug crítico está presente.
- [ ] Nenhuma regressão foi detectada.
- [ ] O desempenho é aceitável.
- [ ] A segurança atende aos requisitos.
- [ ] A versão é identificável.
- [ ] O rollback é possível.

## Validação da fase 8

**Decisão:** [ ] Versão candidata / [ ] Retorno à correção  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 9 — Rascunho da documentação

**Ator: Humano**  
**Objetivo:** documentar o software tal como ele realmente funciona.

## 1. Documentos a produzir

| Documento | Objetivo | Status |
|---|---|---|
| `README.md` | Apresentação e início rápido | [ ] |
| `USER_GUIDE.md` | Uso detalhado e acessível | [ ] |
| `TECHNICAL_GUIDE.md` | Arquitetura e funcionamento interno | [ ] |
| `DEVELOPER_GUIDE.md` | Ambiente, testes, convenções | [ ] |
| `INSTALLATION.md` | Pré-requisitos e instalação | [ ] |
| `SECURITY.md` | Riscos, permissões, boas práticas | [ ] |
| `TROUBLESHOOTING.md` | Erros frequentes e soluções | [ ] |
| `CHANGELOG.md` | Histórico de versões | [ ] |

## 2. Conteúdo a verificar

- [ ] Cada comando está documentado.
- [ ] Cada opção está documentada.
- [ ] Cada arquivo de configuração está documentado.
- [ ] Cada dependência está documentada.
- [ ] Cada erro frequente está explicado.
- [ ] Os limites estão explícitos.
- [ ] Os exemplos são testáveis.

## Validação da fase 9

**Status:** [ ] Rascunho / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 10 — Formatação e documentação final

**Ator: IA**  
**Objetivo:** completar, estruturar e harmonizar a documentação sem inventar comportamentos ausentes do código.

## 1. Prompt de complementação da documentação

```text
Aqui estão os rascunhos da documentação.

1. Verifique a coerência com o código real.
2. Detecte as funções não documentadas.
3. Detecte as opções da CLI não documentadas.
4. Detecte as mensagens de erro não explicadas.
5. Detecte as dependências ausentes.
6. Detecte as etapas de instalação ausentes.
7. Detecte as incoerências entre documentos.
8. Melhore a estrutura e a legibilidade.
9. Complete as seções ausentes.
10. Não altere nenhum comportamento descrito sem evidência no código.
```

## 2. Verificações da documentação

| Verificação | Status | Comentário |
|---|---|---|
| Coerência com o código | [ ] | [A COMPLETAR] |
| Comandos documentados | [ ] | [A COMPLETAR] |
| Opções documentadas | [ ] | [A COMPLETAR] |
| Códigos de saída documentados | [ ] | [A COMPLETAR] |
| Configuração documentada | [ ] | [A COMPLETAR] |
| Dependências documentadas | [ ] | [A COMPLETAR] |
| Erros frequentes documentados | [ ] | [A COMPLETAR] |
| Exemplos testáveis | [ ] | [A COMPLETAR] |
| Estrutura harmonizada | [ ] | [A COMPLETAR] |

## Validação da fase 10

**Status:** [ ] Rascunho / [ ] Validado  
**Validado por:** [NOME]  
**Data:** [AAAA-MM-DD]

---

# Fase 11 — Implantação final em produção

**Ator: Humano**  
**Objetivo:** implantar a versão validada, documentada e testada.

## 1. Preparação

- [ ] Versão validada na fase 8.
- [ ] Documentação final validada na fase 10.
- [ ] Backup do ambiente existente realizado.
- [ ] Procedimento de rollback disponível.
- [ ] Tag de versão criada.

Comandos:

```bash
git tag -a v[VERSION] -m "Versão estável [VERSION]"
git push origin v[VERSION]
```

## 2. Empacotamento

```bash
python -m build
```

Verificação:

```bash
sha256sum dist/*
```

## 3. Implantação

| Etapa | Comando / ação | Status | Comentário |
|---:|---|---|---|
| 1 | Backup | [ ] | [A COMPLETAR] |
| 2 | Implantar a versão com tag | [ ] | [A COMPLETAR] |
| 3 | Verificar o serviço | [ ] | [A COMPLETAR] |
| 4 | Verificar os logs | [ ] | [A COMPLETAR] |
| 5 | Testar o comando principal | [ ] | [A COMPLETAR] |
| 6 | Documentar a versão implantada | [ ] | [A COMPLETAR] |

## 4. Verificações pós-implantação

```bash
systemctl status [SERVICE_NAME]
journalctl -u [SERVICE_NAME] -n 100 --no-pager
```

- [ ] O serviço está ativo.
- [ ] Nenhum erro crítico aparece nos logs.
- [ ] O comando principal responde.
- [ ] A versão implantada corresponde à tag validada.
- [ ] O rollback está documentado e é testável.

## Validação final

| Campo | Valor |
|---|---|
| Versão implantada | [VERSION] |
| Data de entrada em produção | [AAAA-MM-DD] |
| Ambiente | [A COMPLETAR] |
| Responsável | [NOME] |
| Rollback testado | [Sim / Não] |
| Status final | [Em produção / Falha / Rollback] |

---

# Histórico de alterações do documento

| Data | Versão | Autor | Alteração |
|---|---|---|---|
| [AAAA-MM-DD] | 0.1 | [NOME] | Criação do modelo |
| [AAAA-MM-DD] | [VERSION] | [NOME] | [A COMPLETAR] |
