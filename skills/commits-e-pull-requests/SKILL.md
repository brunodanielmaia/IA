---
name: commits-e-pull-requests
description: Escreve mensagens de commit no padrão Conventional Commits e descrições de pull request claras a partir do diff. Use quando o usuário for commitar, pedir uma mensagem de commit, abrir um PR ou quiser organizar mudanças em commits menores.
---

# Commits e pull requests

## Antes de escrever

1. Rode `git status` e `git diff --staged` (ou `git diff`) e leia as mudanças.
2. Se o diff mistura assuntos diferentes (ex.: correção de bug + refatoração + nova feature), sugira separar em commits distintos.
3. Confira se não há segredos (`.env`, chaves de API, tokens) entre os arquivos. Se houver, avise antes de commitar.

## Mensagem de commit (Conventional Commits)

```
<tipo>(<escopo opcional>): <resumo no imperativo, até ~72 caracteres>

<corpo opcional: o porquê da mudança, não o como>

<rodapé opcional: BREAKING CHANGE: ..., Closes #123>
```

**Tipos:** `feat` (nova funcionalidade), `fix` (correção), `docs`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `style`.

Regras:
- Resumo no imperativo: "adiciona", "corrige", "remove" (ou "add", "fix" se o projeto for em inglês; siga o idioma do histórico do repositório).
- Sem ponto final no resumo.
- O corpo explica o motivo e o impacto. O diff já mostra o que mudou.
- Mudança que quebra compatibilidade: `feat!:` e `BREAKING CHANGE:` no rodapé.

Exemplos:
```
fix(auth): renova token antes de expirar

Usuários eram deslogados no meio do checkout porque o token só era
renovado depois de expirar. Agora renovamos 60s antes.
```
```
docs: adiciona prompt de pôster no estilo GTA VI
```

## Descrição de pull request

```markdown
## O que muda
Resumo em 1 a 3 frases, do ponto de vista de quem usa.

## Por quê
Problema ou motivação. Link da issue.

## Como testar
1. Passo a passo para verificar.

## Pontos de atenção
Riscos, decisões discutíveis, o que ficou de fora.
```

Inclua capturas de tela para mudanças visuais. Mantenha o PR pequeno; se passar de ~400 linhas alteradas, sugira dividir.
