# EiffelFly's skills

Skills for [Claude Code](https://claude.com/claude-code) and other agents that read `SKILL.md` files.

| Skill | What it does |
|---|---|
| [do-i-understand](skills/do-i-understand/SKILL.md) | Tests whether you really understand a concept. It asks crucial questions three at a time, grades your answers honestly, and keeps a record per topic so the next session goes back over what you got wrong. |

## Install

In Claude Code:

```
/plugin marketplace add EiffelFly/skills
/plugin install eiffelfly@eiffelfly
```

Then run `/eiffelfly:do-i-understand bitcoin`, or just ask "do I understand bitcoin?".

To use a skill without the plugin, copy its folder into `~/.claude/skills/`. It is then available as `/do-i-understand`.

## Where records go

`do-i-understand` writes one Markdown file per topic to `~/do-i-understand/`. To use another folder, set `DO_I_UNDERSTAND_DIR` or name a folder when you start a session.

## License

MIT
