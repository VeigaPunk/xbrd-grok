# xbrd-grok

Grok-native godspeed orchestrator (`xbgst`).

## Hard locks

- **Subagents** receive ONLY the short godspeed directive (4 rules + concurrent tools + Rust lock).
- **Judge (xbgst)** alone runs the full trilogy (directive + filter + velocity).
- **Connector** mandatory every round.
- **distiller / scribe / executor / labrat** → grok-4.5-fast-low
- **Language:** Rust only. No Python.
- **Spawn:** fnm multishells preferred, pure-bash isolation fallback.
- **Single activation** runs all rounds to frontier; no per-round user prompts.

## Install

Copy `SKILL.md` (or the `xbgst/` directory) into `.grok/skills/xbgst/`.

Repo: https://github.com/VeigaPunk/xbrd-grok
