---
name: ai-project-bootstrap
description: >
  Inicializa projetos de software AI-native com Intake estruturado, base de conhecimento
  em Obsidian, agentes, skills, hooks, GitFlow, contratos de comunicação, adapters
  multi-LLM e roadmap de MVP. Use ao iniciar um projeto a partir de uma ideia ou
  preparar sua fundação de desenvolvimento para Claude Code, Codex e modelos locais.
---

# PROMPT MESTRE — BOOTSTRAP AI-NATIVE HÍBRIDO

Você está iniciando um novo projeto de software utilizando um modelo de desenvolvimento **AI-Native, Multi-Agent e Multi-LLM**.

Sua responsabilidade nesta execução NÃO é começar imediatamente a implementar funcionalidades.

Sua primeira responsabilidade é transformar uma ideia ainda incompleta em uma base de desenvolvimento profissional, organizada, rastreável e pronta para ser executada por diferentes LLMs como:

- Claude Code
- OpenAI Codex
- Qwen
- modelos locais
- outras LLMs disponíveis

O projeto deve ser construído de forma que seja possível trocar de LLM a qualquer momento sem:

- perder contexto;
- perder decisões arquiteturais;
- perder regras de negócio;
- abandonar o workflow definido;
- duplicar documentação;
- depender do histórico de chat de uma LLM específica.

---

# 1. PRINCÍPIO CENTRAL

O centro da inteligência do projeto será um **Vault Obsidian versionado junto ao repositório**.

O Obsidian será a:

> Single Source of Truth / Fonte Única da Verdade do projeto.

Nenhuma informação estruturalmente importante deve depender exclusivamente da memória ou histórico de uma LLM.

Decisões relevantes devem ser persistidas no Vault.

Isso inclui, minimamente:

- visão do produto;
- regras de negócio;
- glossário;
- arquitetura;
- ADRs;
- workflows;
- contratos;
- integrações;
- APIs;
- modelo de dados;
- segurança;
- infraestrutura;
- CI/CD;
- estratégia de testes;
- riscos;
- dívida técnica;
- roadmap;
- decisões;
- backlog macro;
- estado atual do desenvolvimento;
- releases;
- histórico relevante;
- aprendizados;
- convenções;
- agentes;
- skills;
- hooks;
- MCPs;
- GitFlow.

O Vault deve permitir que um engenheiro ou uma LLM que nunca viu o projeto consiga entender rapidamente:

1. o que estamos construindo;
2. por que estamos construindo;
3. como o sistema funciona;
4. quais decisões já foram tomadas;
5. quais regras não podem ser violadas;
6. qual é o estado atual;
7. qual é a próxima etapa.

---

# 2. IDIOMA OFICIAL

Toda comunicação entre:

- LLM;
- orquestrador;
- agentes;
- subagentes;
- engenheiro de software;
- documentação operacional;

deve acontecer em:

# Português do Brasil — PT-BR

Código-fonte pode seguir as convenções idiomáticas da stack utilizada.

Nomes técnicos amplamente aceitos podem permanecer em inglês.

Exemplos:

- Controller
- Service
- Repository
- Aggregate
- Event
- Commit
- Pull Request
- Deploy
- Pipeline

Porém:

- relatórios;
- análises;
- explicações;
- decisões;
- perguntas;
- documentação;

devem ser escritos em português-BR.

---

# 3. REGRA DE OURO: NÃO COMEÇAR CODIFICANDO

Antes de qualquer implementação significativa:

execute um processo formal de:

# INTAKE

O objetivo do Intake é transformar a ideia inicial em uma definição suficientemente clara para iniciar um MVP.

Não transforme o Intake em uma consultoria interminável.

Pergunte apenas aquilo que possa alterar significativamente:

- produto;
- arquitetura;
- desenvolvimento;
- infraestrutura;
- segurança;
- custo;
- prazo;
- workflow.

Quando houver lacunas não críticas:

faça uma recomendação pragmática e registre-a como hipótese.

---

# 4. INTAKE — PRODUTO

Comece perguntando ao usuário/engenheiro:

## Visão

1. Qual problema estamos tentando resolver?

2. Quem utilizará o sistema?

3. Qual é o principal resultado esperado?

4. Existe algum sistema semelhante ou referência?

5. Qual é a principal jornada do usuário?

6. Quais funcionalidades são consideradas essenciais?

7. Quais funcionalidades seriam desejáveis, mas podem esperar?

---

# 5. INTAKE — REGRA DE NEGÓCIO

Pergunte sobre:

- principais regras;
- exceções;
- estados;
- transições;
- permissões;
- papéis;
- limites;
- aprovações;
- validações;
- cálculos;
- eventos importantes.

Questione especialmente:

> Existem regras que, se implementadas incorretamente, tornam o produto inviável?

Identifique invariantes de negócio.

Registre posteriormente essas informações no Vault.

---

# 6. INTAKE — DEFINIÇÃO DO MVP

Pergunte explicitamente:

> Quando exatamente este MVP poderá ser considerado pronto?

Ajude o usuário a transformar a resposta em critérios objetivos.

Exemplo:

MVP considerado pronto quando:

- fluxo principal funciona ponta a ponta;
- autenticação funciona;
- regras críticas foram implementadas;
- testes essenciais passam;
- aplicação está disponível em homologação;
- dados persistem corretamente;
- logs básicos estão disponíveis;
- documentação mínima está atualizada.

Crie uma:

# Definition of MVP Done

Evite transformar o MVP em produto final.

---

# 7. FILOSOFIA DE ENTREGA

Este projeto deve seguir a filosofia:

# IDEA → MVP → HOMOLOGAÇÃO → FEEDBACK → POLISH

Nosso objetivo é reduzir o tempo entre:

nascimento da ideia

e

primeiro MVP completo disponível em homologação.

Devemos buscar:

- qualidade;
- clareza;
- segurança;
- testes;
- boas decisões arquiteturais.

Porém devemos evitar:

- abstrações prematuras;
- plataformas genéricas prematuras;
- otimizações sem evidência;
- arquitetura para problemas inexistentes;
- infraestrutura exagerada;
- microserviços sem necessidade;
- automações excessivas antes do primeiro deploy;
- padrões utilizados apenas por elegância.

Antes do primeiro MVP:

> Simplicidade sustentável vence sofisticação prematura.

O polish vem depois que o produto existe.

---

# 8. MONOREPO OBRIGATÓRIO NO MVP

Todo MVP deve inicialmente nascer como:

# MONOREPO

A menos que exista uma restrição técnica extremamente forte e documentada.

Exemplo:

```text
project/
├── apps/
│   ├── backend/
│   └── frontend/
├── packages/
├── infra/
├── scripts/
├── docs/
└── vault/
```

A organização final deve respeitar a stack escolhida.

Microserviços podem existir posteriormente caso evidências reais justifiquem.

---

# 9. INTAKE — STACK

Pergunte:

- linguagem backend;
- framework backend;
- frontend;
- banco;
- cache;
- mensageria;
- autenticação;
- cloud;
- containers;
- CI/CD;
- observabilidade;
- ferramentas de qualidade;
- gerenciadores de dependência.

Quando o usuário não souber escolher:

sugira opções pragmáticas.

Evite introduzir tecnologia desnecessária.

---

# 10. INTAKE — ARQUITETURA

Pergunte se existe uma arquitetura previamente definida.

Exemplos:

- MVC;
- layered architecture;
- hexagonal;
- clean architecture;
- modular monolith;
- DDD;
- event-driven;
- CQRS.

Caso não exista:

o Arquiteto deve sugerir uma arquitetura proporcional à complexidade real do MVP.

Princípio:

> Arquitetura deve reduzir complexidade, não demonstrar conhecimento.

A arquitetura escolhida deve ser documentada no Obsidian.

Crie ADR quando necessário.

---

# 11. INTAKE — LLMs DISPONÍVEIS

Pergunte quais LLMs/agentes estão disponíveis na máquina.

Exemplo:

- Claude Code;
- Codex;
- ChatGPT Desktop;
- Qwen;
- Ollama;
- modelo local;
- Gemini;
- outros.

Para cada ambiente identificado, registrar quando possível:

- modelo mais barato;
- modelo intermediário;
- modelo mais capaz;
- limitações;
- ferramentas disponíveis;
- MCPs disponíveis;
- suporte a subagentes;
- suporte a skills;
- suporte a hooks;
- acesso a terminal;
- acesso à internet.

Nunca acople o workflow a um único fornecedor.

---

# 12. INTAKE — MCPs

Pergunte quais MCPs estão disponíveis.

Exemplos:

- GitHub;
- GitLab;
- Jira;
- AWS;
- PostgreSQL;
- filesystem;
- browser;
- documentação;
- Slack;
- Teams;
- Obsidian.

Para cada integração:

documente:

- finalidade;
- permissões;
- quais agentes podem utilizá-la;
- operações proibidas;
- necessidade de aprovação humana.

---

# 13. INTAKE — HOOKS

Pergunte:

> Existem comandos que obrigatoriamente precisam ser executados em determinados momentos?

Exemplos:

- antes do commit;
- depois da alteração de código;
- antes do push;
- antes do merge;
- antes do deploy.

Pergunte também sobre:

- build;
- testes;
- lint;
- formatter;
- cobertura;
- análise estática;
- segurança;
- migrations;
- validação de contratos.

Depois das respostas:

sugira hooks úteis.

Exemplo:

```text
pre-commit
→ formatter
→ lint rápido

pre-push
→ build
→ testes
→ cobertura

pre-release
→ integração
→ segurança
→ migrations
```

Hooks devem executar tarefas:

# determinísticas

Não colocar decisões complexas de arquitetura dentro de hooks.

---

# 14. INTAKE — GITFLOW

Pergunte como o usuário deseja trabalhar com Git.

Explorar:

- main;
- release;
- develop;
- feature/*;
- fix/*;
- hotfix/*;
- tags;
- versionamento;
- Pull Requests;
- revisão;
- proteção de branch;
- merge strategy;
- conventional commits.

Pergunte especificamente:

- Quem pode fazer merge?
- LLM pode criar branch?
- LLM pode commitar?
- LLM pode fazer push?
- LLM pode abrir PR?
- LLM pode fazer merge?
- Precisa de autorização humana?

Definir estratégia de versionamento.

Preferencialmente:

Semantic Versioning quando aplicável.

Exemplo:

```text
v0.1.0
v0.2.0
v1.0.0
```

---

# 15. GATES HUMANOS

Identifique ações que precisam obrigatoriamente de autorização humana.

Exemplos:

- mudanças arquiteturais;
- exclusão de dados;
- migration destrutiva;
- deploy produção;
- merge main;
- alteração de infraestrutura crítica;
- mudança de segurança;
- mudança relevante de regra de negócio.

Documentar claramente.

---

# 16. MODELO MULTI-LLM

Após o Intake, crie infraestrutura capaz de trabalhar com múltiplas LLMs.

O workflow NÃO deve pertencer a:

- Claude;
- Codex;
- Qwen;
- qualquer fornecedor específico.

O workflow pertence ao projeto.

Arquitetura desejada:

```text
                     PROJETO
                        │
                        ▼
                 KNOWLEDGE BASE
                    OBSIDIAN
                        │
                        ▼
                   AI WORKFLOW
                        │
             ┌──────────┼──────────┐
             ▼          ▼          ▼
          CLAUDE      CODEX       QWEN
```

Claude/Codex/Qwen devem atuar como:

# adapters/executores

---

# 17. ESTRUTURA BASE

Crie algo equivalente a:

```text
project/
│
├── AGENTS.md
├── CLAUDE.md
│
├── .ai/
│   ├── README.md
│   │
│   ├── workflow/
│   │   ├── START.md
│   │   ├── INTAKE.md
│   │   ├── PLANEJAMENTO.md
│   │   ├── IMPLEMENTACAO.md
│   │   ├── TESTES.md
│   │   ├── REVISAO.md
│   │   ├── DEPLOY.md
│   │   └── COMMIT_PUSH.md
│   │
│   ├── agents/
│   ├── skills/
│   ├── contracts/
│   ├── hooks/
│   ├── prompts/
│   ├── templates/
│   └── adapters/
│       ├── claude/
│       ├── codex/
│       └── local/
│
├── vault/
│
├── apps/
├── packages/
├── infra/
├── scripts/
└── README.md
```

Adapte quando necessário.

---

# 18. CLAUDE.MD E AGENTS.MD

Esses arquivos NÃO devem conter toda a inteligência do projeto.

Eles devem funcionar como:

# adapters

Exemplo conceitual:

CLAUDE.md:

```text
Leia .ai/README.md.

O workflow oficial do projeto vive em .ai/.

A fonte da verdade de negócio e arquitetura vive em /vault.

Antes de executar uma demanda:
1. leia o estado atual;
2. consulte as regras necessárias;
3. siga o workflow;
4. respeite os gates humanos.
```

AGENTS.md deve seguir o mesmo princípio.

Não duplicar regras completas entre os dois arquivos.

---

# 19. OBSIDIAN VAULT

Crie um Vault profissional.

Estrutura inicial sugerida:

```text
vault/

00_HOME/
01_PRODUCT/
02_BUSINESS/
03_ARCHITECTURE/
04_ENGINEERING/
05_WORKFLOWS/
06_INFRASTRUCTURE/
07_SECURITY/
08_TESTING/
09_OPERATIONS/
10_DECISIONS/
11_ROADMAP/
12_RELEASES/
13_AI_SYSTEM/
14_MEETINGS/
15_KNOWLEDGE/
99_ARCHIVE/
```

---

# 20. HOME

Criar:

```text
00_HOME/START_HERE.md
```

Esse arquivo deve funcionar como mapa principal.

Deve responder rapidamente:

- o que é o produto;
- estado atual;
- versão;
- arquitetura;
- stack;
- roadmap;
- etapa atual;
- última decisão;
- próxima ação.

Criar também:

```text
PROJECT_STATUS.md
```

---

# 21. PRODUTO

Criar documentação como:

```text
PRODUCT_VISION.md
MVP_SCOPE.md
PERSONAS.md
USER_JOURNEYS.md
GLOSSARY.md
```

---

# 22. REGRA DE NEGÓCIO

Criar:

```text
BUSINESS_RULES.md
DOMAIN_GLOSSARY.md
BUSINESS_INVARIANTS.md
STATE_MACHINES.md
```

Quando o domínio crescer:

separar por domínio.

Exemplo:

```text
reservas/
pagamentos/
usuarios/
licenciamento/
```

---

# 23. ARQUITETURA

Criar:

```text
SYSTEM_OVERVIEW.md
ARCHITECTURE.md
MODULE_MAP.md
DATA_MODEL.md
INTEGRATIONS.md
API_CONTRACTS.md
```

Criar diretório:

```text
ADR/
```

ADR deve conter decisões arquiteturais importantes.

---

# 24. MAPA DO SISTEMA

Criar diagramas preferencialmente utilizando Mermaid.

Exemplos:

- C4 simplificado;
- fluxo de usuário;
- fluxo backend;
- integrações;
- deployment;
- sequência;
- estados.

Devem ser renderizáveis dentro do Obsidian.

---

# 25. WORKFLOW DE DESENVOLVIMENTO

Criar documentação contendo o fluxo completo.

Exemplo:

```text
INTAKE
   ↓
DISCOVERY
   ↓
PLANEJAMENTO
   ↓
ARQUITETURA
   ↓
IMPLEMENTAÇÃO
   ↓
TESTES
   ↓
REVISÃO
   ↓
HOMOLOGAÇÃO
   ↓
COMMIT/PUSH
   ↓
RELEASE
```

Nem toda alteração precisa atravessar todas as etapas formalmente.

O Orquestrador deve escolher o fluxo proporcional à mudança.

---

# 26. CONTRATOS ENTRE AGENTES

Defina contratos padronizados de comunicação.

Objetivo:

reduzir tokens e reduzir perda de contexto.

Cada agente deve receber apenas a informação necessária.

Não encaminhar histórico inteiro de conversa.

Contrato base:

```yaml
task_id:
objective:
context:
constraints:
inputs:
expected_output:
acceptance_criteria:
allowed_tools:
forbidden_actions:
references:
```

Resposta base:

```yaml
task_id:
status:
summary:
findings:
decisions:
changes:
risks:
tests:
artifacts:
recommendations:
needs_human_decision:
```

Adapte contratos por agente.

---

# 27. CONTEXT MINIMIZATION

Agentes não devem receber automaticamente toda a Knowledge Base.

O Orquestrador deve fornecer:

- contexto suficiente;
- referências específicas;
- arquivos relevantes;
- decisão necessária.

Princípio:

> Contexto mínimo suficiente > contexto máximo disponível.

Explorer deve ajudar nisso.

---

# 28. AGENTE ORQUESTRADOR

Criar obrigatoriamente:

# ORCHESTRATOR

Responsabilidades:

- receber demanda humana;
- interpretar necessidade;
- consultar Knowledge Base;
- decidir workflow;
- decompor trabalho;
- selecionar agentes;
- executar agentes em paralelo quando apropriado;
- controlar dependências;
- consolidar respostas;
- identificar conflitos;
- acionar arquiteto quando necessário;
- acionar QA;
- respeitar gates humanos;
- atualizar estado do projeto.

Modelo recomendado:

# intermediário

Evitar utilizar o modelo mais caro por padrão.

O Orquestrador pode lançar múltiplas instâncias do mesmo agente.

Exemplo:

```text
QA API
QA Segurança
QA Frontend
QA Banco
```

em paralelo.

---

# 29. EXPLORER AGENT

Criar obrigatoriamente:

# EXPLORER

Objetivo:

explorar projeto e responder perguntas factuais.

Exemplos:

- onde está determinada classe?
- quem chama esse método?
- qual tabela possui esse campo?
- existe teste para isso?
- qual configuração controla isso?
- onde está esse endpoint?

Explorer NÃO deve:

- definir arquitetura;
- mudar regra de negócio;
- propor grandes refatorações;
- tomar decisões estratégicas.

Resposta deve ser:

- curta;
- factual;
- referenciada.

Utilizar preferencialmente:

# modelo mais barato disponível.

Podem existir vários Explorers concorrentes.

---

# 30. REPORT AGENT

Criar obrigatoriamente:

# REPORTER

Responsabilidade:

transformar resultados técnicos em comunicação humana clara.

Produzir:

- resumo;
- status;
- riscos;
- alterações;
- testes;
- próximos passos;
- bloqueios.

Deve ser capaz de gerar relatório para:

- desenvolvedor;
- tech lead;
- PO;
- gestor;
- daily.

Utilizar preferencialmente:

# modelo barato.

---

# 31. ARCHITECT AGENT

Criar:

# ARCHITECT

Modelo recomendado:

intermediário ou avançado.

Responsabilidades:

- interpretar requisitos;
- avaliar impacto;
- desenhar solução;
- preservar arquitetura;
- evitar overengineering;
- registrar decisões;
- criar ADR quando necessário.

Pode haver especializações:

```text
backend-architect
frontend-architect
cloud-architect
data-architect
security-architect
```

Quando necessário, arquitetos devem discutir soluções entre si antes da implementação.

---

# 32. DEVELOPER AGENTS

Criar agentes compatíveis com a stack.

Exemplo:

```text
backend-developer
frontend-developer
mobile-developer
data-developer
```

Responsabilidades:

- implementar;
- testar localmente;
- respeitar contratos;
- respeitar arquitetura;
- reportar alterações;
- não ampliar escopo sem autorização.

---

# 33. DEVOPS AGENT

Criar obrigatoriamente:

# DEVOPS

Responsabilidades:

- containers;
- infraestrutura;
- cloud;
- CI/CD;
- secrets;
- ambientes;
- homologação;
- produção;
- observabilidade;
- deploy;
- rollback;
- backups.

Deploy destrutivo ou produção deve respeitar gates humanos.

---

# 34. QA AGENT

Criar:

# QA

Responsabilidades:

- validar critérios de aceite;
- criar testes;
- procurar regressões;
- testar edge cases;
- validar fluxos ponta a ponta.

Pode ser paralelizado.

Exemplo:

```text
QA_FUNCIONAL
QA_API
QA_FRONTEND
QA_SECURITY
QA_PERFORMANCE
```

---

# 35. REVIEWER AGENT

Criar:

# REVIEWER

Não deve simplesmente repetir implementação.

Deve procurar:

- bugs;
- regressões;
- violações arquiteturais;
- segurança;
- complexidade desnecessária;
- duplicação;
- ausência de testes;
- comportamento inesperado.

Preferencialmente receber:

- diff;
- requisitos;
- arquitetura relevante;
- testes.

Não enviar contexto desnecessário.

---

# 36. OUTROS AGENTES

Analise o projeto e determine se vale criar:

- Product Owner;
- Project Manager;
- Tech Lead;
- Security Engineer;
- DBA;
- UX;
- Data Engineer;
- SRE;
- FinOps.

Somente criar se houver benefício real.

Não criar agentes apenas para parecer sofisticado.

---

# 37. HIERARQUIA DE MODELOS

Crie uma estratégia de custo.

Exemplo:

## Tier 1 — barato

Usar para:

- exploração;
- buscas;
- relatórios;
- tarefas mecânicas.

## Tier 2 — intermediário

Usar para:

- orquestração;
- implementação;
- testes;
- revisão comum.

## Tier 3 — avançado

Usar para:

- arquitetura crítica;
- incidentes complexos;
- segurança crítica;
- decisões difíceis.

A estratégia deve funcionar independentemente do fornecedor.

---

# 38. SKILLS

Crie skills reutilizáveis.

Avalie minimamente:

```text
commit
git-flow
code-review
testing
documentation
release
deploy
jira
architecture-decision
database-migration
security-review
dependency-update
```

Não criar todas automaticamente se não fizer sentido.

---

# 39. SKILL DE COMMIT

Criar uma skill específica que:

- leia diff;
- entenda mudança;
- rode validações necessárias;
- gere mensagem apropriada;
- siga padrão escolhido;
- nunca inclua arquivos indevidos;
- não commite segredos.

---

# 40. SKILL DE JIRA / GESTÃO

Caso Jira ou ferramenta equivalente exista:

criar skill capaz de:

- criar Epic;
- criar Story;
- criar Task;
- criar Bug;
- atualizar status;
- registrar desenvolvimento;
- adicionar comentários;
- registrar tempo quando permitido.

Mapear equivalente se:

- Linear;
- GitHub Issues;
- GitLab;
- Azure DevOps.

---

# 41. SKILLS PORTÁVEIS

Sempre que possível:

mantenha especificação conceitual em:

```text
.ai/skills/
```

e adapters específicos em:

```text
.ai/adapters/
```

Evite duplicar lógica entre Claude e Codex.

---

# 42. HOOKS

Documentar cada hook:

```text
nome
momento
comando
objetivo
tempo esperado
bloqueante?
```

Exemplo:

```text
pre-push

backend:
./mvnw test

frontend:
npm test
npm run build
```

Hooks lentos devem ser usados com cuidado.

---

# 43. ESTADO DO DESENVOLVIMENTO

Criar:

```text
vault/00_HOME/PROJECT_STATUS.md
```

e, se apropriado:

```text
.ai/state/AI_DEVELOPMENT_STATE.md
```

Esse documento deve informar:

```text
fase atual
etapa atual
branch atual
última entrega
última decisão
tarefas em andamento
bloqueios
próxima ação
testes atuais
release atual
```

Esse arquivo permitirá trocar:

Claude → Codex

ou:

Codex → Qwen

sem depender da conversa anterior.

---

# 44. REGRA DE HANDOFF

Antes de interromper uma sessão longa ou trocar de LLM:

atualizar o estado.

Criar um bloco:

```text
HANDOFF

Contexto:
Estado:
Alterações:
Decisões:
Pendências:
Próximo passo:
Arquivos relevantes:
```

A próxima LLM deve começar por esse handoff.

---

# 45. REGRA DE DOCUMENTAÇÃO

Nunca documentar tudo.

Documentar aquilo que:

- será reutilizado;
- afeta decisões;
- explica comportamento;
- protege regras;
- evita investigação futura.

Evitar documentação burocrática.

---

# 46. ROADMAP DE DESENVOLVIMENTO

Depois do Intake e bootstrap:

criar obrigatoriamente:

```text
vault/11_ROADMAP/DEVELOPMENT_PLAN.md
```

Esse documento deve dividir o projeto em fases finitas.

Exemplo conceitual:

```text
FASE 0 — Discovery
FASE 1 — Bootstrap
FASE 2 — Identidade
FASE 3 — Core Backend
FASE 4 — Core Frontend
FASE 5 — Integrações
FASE 6 — QA
FASE 7 — Homologação
FASE 8 — MVP Release
```

NÃO copie esse exemplo automaticamente.

Crie fases adequadas ao projeto real.

Cada fase deve possuir:

```text
Objetivo
Escopo
Entregáveis
Dependências
Critérios de aceite
Definition of Done
Riscos
```

---

# 47. PREVENÇÃO DO "TÚNEL INFINITO"

O roadmap deve impedir desenvolvimento infinito.

Toda fase precisa ter:

# início claro

e

# fim claro.

Se surgir melhoria não essencial:

registrar em:

```text
POST_MVP_BACKLOG.md
```

Não aumentar silenciosamente o MVP.

---

# 48. HTML DO ROADMAP

Gerar também:

```text
docs/development-plan.html
```

Esse HTML deve ser visual e navegável.

Objetivo:

servir para:

- daily;
- acompanhamento do time;
- status executivo;
- compartilhamento.

Mostrar:

- fases;
- checklist;
- percentual;
- status;
- bloqueios;
- entregáveis;
- dependências.

Status sugeridos:

```text
Não iniciado
Em andamento
Bloqueado
Em validação
Concluído
```

---

# 49. DASHBOARD VISUAL DA ARQUITETURA AI

Ao concluir o bootstrap:

gerar:

```text
docs/ai-development-system.html
```

O HTML deve explicar visualmente:

- Obsidian;
- Knowledge Base;
- Orquestrador;
- agentes;
- subagentes;
- skills;
- hooks;
- MCPs;
- Claude;
- Codex;
- modelos locais;
- workflow;
- GitFlow;
- gates humanos;
- fluxo de contexto;
- estratégia de modelos.

Utilizar:

- diagramas;
- cards;
- timelines;
- fluxogramas;
- tabelas;
- Mermaid quando apropriado.

O HTML deve ser standalone sempre que possível.

---

# 50. MANUAL DE USO

Criar:

```text
vault/13_AI_SYSTEM/AI_DEVELOPMENT_MANUAL.md
```

Explicar:

## Como iniciar o projeto

## Como abrir Vault no Obsidian

Passo a passo:

1. instalar Obsidian;
2. selecionar "Open folder as vault";
3. selecionar `/vault`;
4. habilitar recursos necessários;
5. navegar pelo START_HERE.

Não exigir plugins externos desnecessários.

---

# 51. MANUAL DO WORKFLOW

Documentar:

```text
nova demanda
↓
orquestrador
↓
exploração
↓
arquitetura se necessário
↓
implementação
↓
QA
↓
review
↓
report
↓
gate humano
↓
commit/push
```

Mostrar exemplos.

---

# 52. COMO TROCAR DE LLM

O manual deve ter seção:

# Trocando de Claude para Codex

e:

# Trocando de Codex para Claude

e:

# Utilizando modelo local

O processo deve essencialmente ser:

1. abrir repositório;
2. ler adapter da ferramenta;
3. ler `.ai/README.md`;
4. ler `START_HERE`;
5. ler `PROJECT_STATUS`;
6. ler handoff;
7. continuar workflow.

---

# 53. ARQUIVOS RAIZ

Criar README principal simples.

Ele deve explicar:

```text
produto
como executar
onde está documentação
como abrir Obsidian
como usar AI workflow
```

---

# 54. SEGURANÇA

Nunca armazenar no Vault:

- passwords;
- tokens;
- secrets;
- chaves privadas.

Documentar apenas nomes de variáveis.

Criar:

```text
.env.example
```

quando apropriado.

---

# 55. INICIALIZAÇÃO FINAL

Depois que todas as perguntas essenciais forem respondidas:

apresente ao usuário um resumo:

```text
Produto
Stack
Arquitetura
MVP
GitFlow
LLMs
MCPs
Hooks
Agentes
Infra
Roadmap inicial
Riscos
```

Solicite correção apenas se houver divergências críticas.

Não interrompa o bootstrap por detalhes pequenos.

Faça hipóteses documentadas quando necessário.

---

# 56. EXECUÇÃO DO BOOTSTRAP

Após consolidar o Intake:

crie:

1. estrutura do repositório;
2. Obsidian Vault;
3. `.ai/`;
4. adapters Claude;
5. adapters Codex;
6. adapters locais quando necessários;
7. agentes;
8. contratos;
9. skills;
10. hooks;
11. GitFlow;
12. documentação;
13. roadmap;
14. estado inicial;
15. HTML da arquitetura AI;
16. HTML do roadmap;
17. manual de desenvolvimento;
18. README.

---

# 57. RELATÓRIO FINAL

O Report Agent deve apresentar:

## Estrutura criada

## Decisões tomadas

## Arquitetura escolhida

## Stack

## Agents

## Skills

## Hooks

## MCPs

## GitFlow

## Roadmap

## Como abrir Obsidian

## Como iniciar Claude

## Como iniciar Codex

## Como trocar de LLM

## Como iniciar a primeira demanda

---

# 58. PRIMEIRO PASSO APÓS O BOOTSTRAP

NÃO comece automaticamente a construir o produto.

Ao terminar:

defina claramente:

```text
BOOTSTRAP COMPLETO

Próxima etapa:
FASE X — <nome>

Próxima ação recomendada:
<ação>
```

O usuário/engenheiro decidirá quando iniciar a implementação.

---

# 59. PRINCÍPIOS FINAIS

Este sistema deve otimizar:

# Velocidade

sem sacrificar:

# Engenharia.

Deve otimizar:

# contexto

sem criar:

# burocracia.

Deve utilizar:

# agentes especializados

sem criar:

# uma empresa fictícia de agentes inúteis.

Deve buscar:

# MVP funcional

antes de:

# perfeição.

Deve usar:

# IA como multiplicador de engenharia

e não como substituto para:

# decisões técnicas conscientes.

A Knowledge Base pertence ao projeto.

O workflow pertence ao projeto.

As decisões pertencem ao projeto.

As LLMs são executores intercambiáveis.

---

# INICIE AGORA

Não implemente código do produto ainda.

Comece executando o:

# INTAKE

Faça as perguntas em grupos lógicos e pequenos.

Não envie 50 perguntas simultaneamente.

Priorize primeiro as perguntas que destravam:

1. Produto
2. MVP
3. Regra de negócio
4. Stack
5. Arquitetura
6. GitFlow
7. LLMs
8. MCPs
9. Hooks
10. Infraestrutura

Após cada bloco, consolide internamente as respostas e prossiga.

Ao final do Intake:

apresente a proposta de bootstrap e então gere a infraestrutura descrita neste documento.

