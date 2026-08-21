# Routing freeze — 2026-08-21

Live table is marketplace SSoT: **VeigaPunk/grok-marketplace** `plugins/xbgst-stack/docs/model-routing.md`. Pointer: `docs/model-routing.md`. Do not fork. This skill-only mirror is not SSoT.

## Lanes that PASS

- **M02** token-plan `qwen3.8-max` → `XBGST_QWEN38_OK` (HTTP 200)
- **M03** token-plan `deepseek-v4-flash-0731` → `XBGST_DSFLASH0731_OK` (HTTP 200)
- **M04** token-plan `deepseek-v4-pro-0813` → `XBGST_DSPRO0813_OK` (HTTP 200; no unversioned alias)
- **M05** daybreak lab `gpt-daybreak-blue-latest` → `XBGST_DAYBREAK_BLUE_OK` via **stock** `codex exec` (not titanium)

Daybreak is lab/defensive ping, not default revenger.

## Binary split

- **stock `codex`** — Daybreak Blue lab ping; Exception E2 `cdx-revenger-*`. Not sekhmet L3.
- **`codex-titanium`** — sekhmet **L3 workers only**. Never Daybreak. Never L2. Never Grok-host E2.
- **`prime-agent` / `scripts/prime-agent-l2.sh`** — optional already-spawned `gx-*` (xAI fail-closed). Never wrap or exec `codex-titanium`.

## Vault (title only)

`DashScope Token Plan Team (intl sk-sp)` in vault `AgentAutomation`. No secrets in this tree.

## Exception E2 — the-revenger → cdx

Outbound **stock** `codex exec` named `cdx-revenger-*`. Not Grok `spawn_subagent`. Not `codex-titanium`. Overfit: `codex exec -m gpt-5.6-luna`. Daybreak Blue is not this lane. `agents/the-revenger.md` stays `model: inherit`.

## Policy smoke (run in marketplace `xbgst-stack`)

```
bash scripts/route-smoke.sh
```

Policy greps only (no `op`, no `curl`, no secrets), then `tests/test-prime-agent-l2.sh`.

Superseded WWKD (do not execute titanium Daybreak/E2 recipes): `docs/prime-agent-routing-plan.md`.
