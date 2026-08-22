# xbrd-grok

Grok-native godspeed orchestrator skill (`xbgst`).

> **Canonical install path is the marketplace plugin**, not this skill-only mirror:
> [VeigaPunk/grok-marketplace](https://github.com/VeigaPunk/grok-marketplace) → plugin **`xbgst-stack`** (agents + commands + livepatch + this skill).

This repo stays a thin, paste-friendly mirror of `plugins/xbgst-stack/skills/xbgst/SKILL.md` for docs and quick copy.

## Hard locks

- **Subagents** receive ONLY the byte-exact canonical godspeed directive plus their task; every initial and follow-up dispatch ends exactly once with `| godspeed`.
- **Judge (xbgst)** alone runs the full trilogy (directive + filter + velocity).
- **Connector** mandatory every round.
- **distiller / scribe / executor / labrat** → grok-4.5-fast-low
- **Language:** Match the repo. No language lock. Prefer the stack already in-tree.
- **Concurrency:** host-governed with no smaller package-level cap; this distribution is certified at 64 concurrent agents. tools={*} for every agent.
- **Single activation** runs all rounds to frontier; no per-round user prompts.
- **Local-first ship:** after each judged milestone `APPROVED` → commit + push **direct to `main`** (no fork/PR default).
- **Host substrate:** CLI livepatch that bans `general-purpose` / `explore` ships inside **xbgst-stack**.

## Install (recommended)

Canonical install is **grok-marketplace** `xbgst-stack`:

```bash
curl -fsSL https://raw.githubusercontent.com/VeigaPunk/grok-marketplace/main/scripts/install-xbgst-stack.sh | bash
```

Pinned channel (optional):

```bash
curl -fsSL https://raw.githubusercontent.com/VeigaPunk/grok-marketplace/grok-stable/scripts/install-xbgst-stack.sh | bash
```

Manual equivalent:

```bash
grok plugin marketplace add VeigaPunk/grok-marketplace
grok plugin install xbgst-stack@veigapunk/grok-marketplace --trust
bash ~/.grok/installed-plugins/xbgst-stack-*/scripts/install-host.sh
```

## Skill-only install (this repo — secondary)

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
| L3 swarm substrate | `sekhmet` / `xbrd-spark` (primary `gpt-5.3-codex-spark`, fallback `gpt-5.6-luna`) — `~/Projects/xbgst/xbrd-spark` |
| Skill source in marketplace | `plugins/xbgst-stack/skills/xbgst/SKILL.md` |

Repo: https://github.com/VeigaPunk/xbrd-grok
