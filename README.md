# ai-project-bootstrap

Skill de bootstrap para projetos AI-native, com workflows multi-LLM, base de conhecimento em Obsidian, agentes, skills, hooks, GitFlow e foco em entrega rápida de MVPs.

## Qual problema resolve?

No desenvolvimento com IA, regras de negócio, decisões e progresso frequentemente ficam espalhados em conversas. Trocar de ferramenta ou atingir um limite de uso exige reconstruir contexto, favorece decisões inconsistentes e pode transformar um MVP em um trabalho sem fim.

## Como resolve?

A skill começa com um Intake em pequenos blocos para esclarecer produto, MVP, regras, stack e ambiente. Depois prepara uma fundação versionada no próprio projeto: conhecimento em Markdown no Vault, workflow em `.ai/`, adapters para diferentes LLMs, contratos entre agentes e um roadmap com critérios objetivos de conclusão.

O Obsidian é a interface para navegar pelo conhecimento. Os arquivos Markdown continuam acessíveis pelo terminal, Git e outras ferramentas.

## O que entrega?

- Estrutura inicial de monorepo adequada à stack.
- Vault Obsidian com produto, regras, arquitetura, decisões e estado atual.
- Workflow de desenvolvimento, agentes, contratos, skills e hooks pertinentes.
- Adapters para Claude Code, Codex e modelos locais quando necessários.
- GitFlow, gates humanos e orientações de segurança definidos no Intake.
- Planejamento em `vault/11_ROADMAP/DEVELOPMENT_PLAN.md`.
- Dashboard do planejamento em `docs/development-plan.html`.
- Explicação visual do sistema de desenvolvimento em `docs/ai-development-system.html`.
- Manual de desenvolvimento, handoff e README do projeto.

Ao concluir o bootstrap, a skill indica a próxima etapa e aguarda o engenheiro iniciar a implementação do produto.

## Conteúdo e compatibilidade

O corpo de `skills/ai-project-bootstrap/SKILL.md` contém o prompt-mestre com suas 59 seções e o bloco **INICIE AGORA**. O cabeçalho YAML identifica a skill para as ferramentas. O README é documentação de instalação e uso, separada das instruções do prompt.

A mesma pasta é utilizada no Claude Code e no Codex. A skill fornece instruções; suporte a subagentes, seleção de modelos, MCPs, hooks e execução entre fornecedores depende das capacidades e permissões reais do ambiente. Instalar esta skill não instala as LLMs, não conecta contas nem cria automaticamente um runtime multi-LLM.

## Pré-requisitos

- Git.
- Claude Code e/ou Codex instalados e autenticados.
- Acesso de escrita ao projeto que receberá o bootstrap.
- Obsidian para navegar visualmente pelo Vault gerado, quando desejado.

Não é necessário um MCP de Obsidian para ler e escrever Markdown no filesystem. Informe no Intake quais MCPs, modelos e ferramentas estão realmente disponíveis.

## Baixar o repositório

```bash
git clone https://github.com/daniilooo/ai-project-bootstrap.git
cd ai-project-bootstrap
```

Os comandos de instalação abaixo partem da raiz deste repositório. Copie a **pasta inteira** da skill.

## Instalação no Linux ou macOS

### Claude Code — todos os projetos da máquina

```bash
mkdir -p "$HOME/.claude/skills"
cp -R skills/ai-project-bootstrap "$HOME/.claude/skills/"
```

### Codex — todos os projetos da máquina

```bash
mkdir -p "$HOME/.agents/skills"
cp -R skills/ai-project-bootstrap "$HOME/.agents/skills/"
```

### Instalação somente em um projeto

Substitua o caminho pelo projeto que receberá a skill:

```bash
projeto_destino="/caminho/do/seu/projeto"
mkdir -p "$projeto_destino/.claude/skills" "$projeto_destino/.agents/skills"
cp -R skills/ai-project-bootstrap "$projeto_destino/.claude/skills/"
cp -R skills/ai-project-bootstrap "$projeto_destino/.agents/skills/"
```

Escolha instalação pessoal ou por projeto conforme sua necessidade. Evite instalar duas cópias com o mesmo nome no mesmo ambiente.

## Instalação no Windows — PowerShell

### Instalação pessoal

```powershell
New-Item -ItemType Directory -Force -Path "$HOME/.claude/skills", "$HOME/.agents/skills" | Out-Null
Copy-Item -Recurse -Path "./skills/ai-project-bootstrap" -Destination "$HOME/.claude/skills/"
Copy-Item -Recurse -Path "./skills/ai-project-bootstrap" -Destination "$HOME/.agents/skills/"
```

Você pode executar apenas a cópia correspondente à ferramenta que utiliza.

### Instalação somente em um projeto

```powershell
$projetoDestino = "C:/Projetos/meu-projeto"
New-Item -ItemType Directory -Force -Path "$projetoDestino/.claude/skills", "$projetoDestino/.agents/skills" | Out-Null
Copy-Item -Recurse -Path "./skills/ai-project-bootstrap" -Destination "$projetoDestino/.claude/skills/"
Copy-Item -Recurse -Path "./skills/ai-project-bootstrap" -Destination "$projetoDestino/.agents/skills/"
```

## Uso no Claude Code

Abra o terminal na pasta do **projeto que receberá o bootstrap** e inicie:

```bash
claude
```

Na sessão, use:

```text
/ai-project-bootstrap
```

Você também pode informar a ideia:

```text
/ai-project-bootstrap Quero criar um sistema de locação de salas por hora. Comece pelo Intake.
```

## Uso no Codex

Abra o terminal na pasta do **projeto que receberá o bootstrap** e inicie:

```bash
codex
```

Na sessão, use:

```text
$ai-project-bootstrap
```

Ou solicite explicitamente:

```text
Use a skill ai-project-bootstrap para inicializar este projeto. Minha ideia é um sistema de locação de salas por hora. Comece pelo Intake.
```

Se a skill não aparecer, confira se existe `SKILL.md` dentro da pasta instalada e abra uma nova sessão. A cópia em `~/.claude/skills/` se destina ao Claude Code local; a instalação em Cowork e sessões cloud utiliza mecanismos próprios da plataforma.

## Como será a execução?

1. Apresente sua ideia e responda aos pequenos blocos de perguntas.
2. Informe requisitos críticos, critérios de MVP pronto e ferramentas disponíveis.
3. Confira a proposta consolidada e corrija divergências críticas.
4. A LLM gera a fundação, a documentação e os dois HTMLs.
5. Abra a pasta `vault/` como Vault no Obsidian e navegue por `00_HOME/START_HERE.md`.
6. Revise o estado, o planejamento e a próxima ação antes de iniciar o desenvolvimento.

A skill não deve começar automaticamente a implementar o produto ao terminar o bootstrap.

## Atualizar a instalação

Na cópia deste repositório:

```bash
git pull --ff-only
```

Depois copie novamente a pasta da skill para o destino escolhido. Preserve eventuais personalizações antes de substituir arquivos.

## Desinstalar

Remova apenas a pasta `ai-project-bootstrap` do local em que a instalou. Isso remove a skill, mas mantém os artefatos já gerados nos projetos.

## Limites e próximos passos

- O resultado deve ser conferido em um projeto piloto; validação do formato não comprova a execução completa em todas as ferramentas.
- O prompt não define uma sincronização determinística entre o plano Markdown e seu HTML. Ao evoluir a skill, vale estabelecer o Markdown como origem e gerar o HTML a partir dele.
- Uma licença de distribuição deve ser escolhida antes de incentivar reutilização pública. Repositório público, por si só, não concede uma licença de uso.
- Versionamento e validação automatizada podem ser adicionados após o primeiro uso real, mantendo o prompt original preservado nesta versão.

## Documentação oficial

- [Skills no Codex](https://learn.chatgpt.com/docs/build-skills)
- [Skills no Claude Code](https://code.claude.com/docs/en/skills)

# ai-project-bootstrap
