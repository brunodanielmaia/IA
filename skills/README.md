# Skills

Skills de IA para usar com agentes (Claude Code, Claude.ai e outros compatíveis com o formato `SKILL.md`).

Cada skill fica em sua própria pasta, com um `SKILL.md` que diz quando e como usá-la. O agente lê o campo `description` e carrega a skill sozinho quando ela é útil.

## Skills disponíveis

| Skill | Para que serve |
|---|---|
| [engenheiro-de-prompts](engenheiro-de-prompts/SKILL.md) | Melhora e cria prompts e system prompts claros e testáveis |
| [prompt-para-imagem](prompt-para-imagem/SKILL.md) | Cria prompts detalhados para GPT Image, Midjourney, Gemini, Flux e outros |
| [revisor-de-codigo](revisor-de-codigo/SKILL.md) | Code review focado em bugs reais e segurança, com veredito e correções |
| [depuracao-sistematica](depuracao-sistematica/SKILL.md) | Encontra a causa raiz de bugs com método, sem tentativa e erro |
| [commits-e-pull-requests](commits-e-pull-requests/SKILL.md) | Mensagens de commit (Conventional Commits) e descrições de PR |
| [ata-de-reuniao](ata-de-reuniao/SKILL.md) | Transforma transcrições em ata com decisões, tarefas e prazos |
| [pesquisa-com-fontes](pesquisa-com-fontes/SKILL.md) | Pesquisa na web com checagem cruzada e citações |
| [conteudo-para-redes-sociais](conteudo-para-redes-sociais/SKILL.md) | Posts, carrosséis, roteiros de vídeo curto e legendas |

## Como instalar

**Claude Code**
- Para todos os projetos: copie a pasta da skill para `~/.claude/skills/`.
- Só para um projeto: copie para `.claude/skills/` dentro do projeto.

```bash
git clone https://github.com/brunodanielmaia/IA.git
cp -r IA/skills/revisor-de-codigo ~/.claude/skills/
```

**Claude.ai**
Compacte a pasta da skill em `.zip` e envie em *Configurações → Capacidades → Skills*.

**Outros assistentes**
Copie o conteúdo do `SKILL.md` (sem o cabeçalho entre `---`) e cole como instrução personalizada ou no início da conversa.
