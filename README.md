# xbrd-grok

Grok-native godspeed orchestrator skill (`xbgst`).

> **Canonical install path is the marketplace plugin**, not this skill-only mirror:
> [VeigaPunk/grok-marketplace](https://github.com/VeigaPunk/grok-marketplace) → plugin **`xbgst-stack`** (agents + commands + livepatch + this skill).

This repo stays a thin, paste-friendly mirror of `plugins/xbgst-stack/skills/xbgst/SKILL.md` for docs and quick copy.

## Hard locks

- **Subagents** receive ONLY the short godspeed directive (4 rules + concurrent tools + Rust lock).
- **Judge (xbgst)** alone runs the full trilogy (directive + filter + velocity).
- **Connector** mandatory every round.
- **distiller / scribe / executor / labrat** → grok-4.5-fast-low
- **Language:** Rust only. No Python.
- **Concurrency hardcap:** 16 concurrent Grok agents. tools={*} for every agent.
- **Single activation** runs all rounds to frontier; no per-round user prompts.
- **Local-first ship:** after each judged milestone `APPROVED` → commit + push **direct to `main`** (no fork/PR default).
- **Host substrate:** CLI livepatch that bans `general-purpose` / `explore` ships inside **xbgst-stack**.

## Install (recommended)

```bash
grok plugin marketplace add VeigaPunk/grok-marketplace
grok plugin install xbgst-stack@veigapunk/grok-marketplace --trust
bash ~/.grok/installed-plugins/xbgst-stack-*/scripts/install-host.sh
```

## Skill-only install (this repo)

```bash
mkdir -p ~/.grok/skills/xbgst
cp SKILL.md ~/.grok/skills/xbgst/SKILL.md
# or: cp -a xbgst ~/.grok/skills/
```

You still need agent profiles + livepatch from **xbgst-stack** for full specialist dispatch and host bans.

## Related

| Piece | Location |
|-------|----------|
| Marketplace SSoT | https://github.com/VeigaPunk/grok-marketplace |
| Channel tag | `grok-stable` |
| L3 swarm substrate | `sekhmet` / `~/Projects/xbrd-spark` (gpt-5.6-luna + fast + effort low) |
| Skill source in marketplace | `plugins/xbgst-stack/skills/xbgst/SKILL.md` |

Repo: https://github.com/VeigaPunk/xbrd-grok
