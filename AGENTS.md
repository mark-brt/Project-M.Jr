# MazyOS para Codex

Este workspace foi adaptado do MazyOS original, que vinha configurado para Claude Code.
Aqui, o arquivo principal de regras para o Codex e este `AGENTS.md`.

## Contexto do negocio

No inicio de toda conversa, ler estes arquivos quando existirem e estiverem preenchidos:

1. `_memoria/empresa.md` - quem e o usuario, o que faz, como funciona o negocio
2. `_memoria/preferencias.md` - tom de voz, estilo de escrita, o que evitar
3. `_memoria/estrategia.md` - foco atual, prioridades, prazos

Usar essas informacoes como base para qualquer resposta ou decisao. Para tarefas visuais
como landing page, carrossel, post ou proposta, consultar tambem `identidade/design-guide.md`.

Nao precisa listar tudo que foi lido. Use o contexto naturalmente.

## Fluxo de trabalho no Codex

Antes de executar qualquer tarefa, verificar se existe um workflow relevante em:

- `.codex/skills/<nome>/SKILL.md`
- se nao existir em `.codex`, verificar o legado `.claude/skills/<nome>/SKILL.md`

Quando o usuario pedir um comando no estilo `/abrir`, `/instalar`, `/carrossel`,
`/seo`, `/salvar` ou parecido, interpretar como pedido para seguir a skill
correspondente.

Exemplos:

- `/instalar` -> ler `.codex/skills/instalar/SKILL.md`
- `/abrir` -> ler `.codex/skills/abrir/SKILL.md`
- `/carrossel` -> ler `.codex/skills/carrossel/SKILL.md`
- `/seo` -> ler `.codex/skills/seo/SKILL.md`

## Organizacao do workspace

- `_memoria/` - contexto permanente do negocio
- `identidade/` - identidade visual e referencias de marca
- `clientes/` - uma pasta por cliente ou projeto
- `marketing/` - conteudo proprio do Marcos
- `saidas/` - entregas, rascunhos e arquivos finais
- `dados/` - arquivos enviados para analise
- `scripts/` - automacoes criadas conforme necessidade
- `.codex/skills/` - workflows locais adaptados para Codex
- `.claude/skills/` - workflows originais mantidos por compatibilidade com o curso

## Regras do sistema

- Preferir os workflows locais antes de inventar um processo novo.
- Para cliente novo, criar `clientes/<nome-do-cliente>/briefing.md`.
- Para landing pages, manter briefing, referencias, textos e arquivos finais dentro da pasta do cliente.
- Ao concluir algo repetivel, perguntar se isso pode virar uma skill para a proxima vez.
- Ao receber uma correcao com valor permanente, perguntar se deve salvar na memoria.
- Nao sobrescrever contexto existente sem confirmar quando houver conteudo real preenchido.

## Adaptacao Claude -> Codex

O curso pode falar em `CLAUDE.md`, `.claude/skills` e comandos do Claude Code.
Neste workspace, a equivalencia e:

- `CLAUDE.md` -> `AGENTS.md`
- `.claude/skills` -> `.codex/skills`
- comando `/nome` -> ler e executar `.codex/skills/nome/SKILL.md`

Manter `CLAUDE.md` e `.claude/skills` no projeto porque eles ajudam a acompanhar o curso
e servem como fonte original dos workflows.
