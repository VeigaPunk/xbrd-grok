# Plan — Live model routing (Alibaba + Daybreak Blue + revenger→cdx), Prime Agent later

> **SUPERSEDED (2026-08-21 judge freeze).** Do not execute the `codex-titanium` Daybreak/E2 recipes below. Live table: marketplace `plugins/xbgst-stack/docs/model-routing.md`. Daybreak + E2 use stock `codex`. Titanium is sekhmet L3 only. L2 never titanium.

Shippable copy of `.xbgst/plans/2026-08-21-prime-agent-routing.md` (grok-marketplace gitignores `.xbgst/`; this file is the in-tree pointer).

**Session:** 2 | **Dispatched by:** xbgst | **Date:** 2026-08-21

## Phase 0 — State map
- **Exists:** xbgst-stack plugin (installed 1.1.23 / marketplace 1.1.24); Prime Agent 0.7.4 with xAI-only L2 wrapper; empty `~/.prime/agent/auth.json`; DashScope model ids already in xbrd-spark benches; Codex Titanium + ChatGPT OAuth; Codex cache slug `gpt-daybreak-blue-latest`; agent-browser + musketeer CDP; 1Password desktop present (item names unverified this dispatch).
- **Missing:** live `qwen3.8-max` token completion; versioned DeepSeek ids on that key; Daybreak Blue lane; `the-revenger`→cdx spawn; executable routing table. gdsd-fknpft crate is a stub (no `router.rs`).
- **Risk:** token item unverified; env name split (`DASHSCOPE_API_KEY` vs `ALIBABA_API_KEY`); Prime hybrid fights fail-closed; Grok skill pins revenger→grok (user override wins for cdx this round). Do not claim Alibaba grants.

## WWKD
1. **What:** One live Alibaba completion for `qwen3.8-max`, then DeepSeek flash/pro, then Daybreak Blue, then overfit the-revenger on cdx. Prime multi-provider later.
2. **Why:** User override: route eligible token models now; skip grant-claim.
3. **Assumptions/Risks:** token in 1Password or Model Studio; Codex OAuth live; Daybreak slug callable; isolate Prime L2.
4. **How:** curl + `op run` for Alibaba; `codex-titanium` for Daybreak/cdx; do not patch `prime-agent-l2.sh` until judge picks hybrid.
5. **Escalation:** isolation vs hybrid Prime (E1); revenger-only roster split (E2); `DASHSCOPE_API_KEY` canonical (E3); Daybreak defensive scope (E4); missing token item (E5); marketplace SSoT vs installed plugin (E6).

## Milestones
| # | Title | Gate command | Expected output | Executor |
|---|---|---|---|---|
| M01 | 1Password inventory (names only) | `op whoami && op item list` (titles only) | candidate DashScope/Alibaba item title; no secrets echoed | gx-janitor-keys |
| M02 | Skeleton: `qwen3.8-max` | `op run` + curl DashScope `chat/completions` model `qwen3.8-max` | HTTP 200 + `XBGST_QWEN38_OK` | gx-labrat-qwen38 |
| M03 | `deepseek-v4-flash-0731` | same curl, that model id | HTTP 200 + `XBGST_DSFLASH0731_OK` | gx-labrat-dsflash |
| M04 | `deepseek-v4-pro-0813` | same curl, that model id | HTTP 200 + `XBGST_DSPRO0813_OK` (no silent alias) | gx-labrat-dspro |
| M05 | Daybreak Blue enable + ping | `codex-titanium exec -m gpt-daybreak-blue-latest … XBGST_DAYBREAK_BLUE_OK` | slug listed + canary | gx-labrat-daybreak |
| M06 | Overfit: revenger→cdx | `codex-titanium exec -m gpt-5.6-luna` RECON of `prime-agent-l2.sh` | `XBGST_CDX_REVENGER_OK` + FINDING | cdx-revenger-l2 |
| M07 | Routing table freeze | `docs/model-routing.md` + L2 test still PASS | table + `PASS: prime-agent-l2 fail-closed + ban strings` | gx-executor-routing |
| M08 | Prime isolation vs hybrid | list `auth.json` keys only; no wrapper edit | keys `[]` today; judge decision | gx-critic-prime |

## Dependencies
M01 → M02 → M03 → M04. M05 independent of Alibaba (Codex OAuth exists). M02+M05 → M06. M02+M03+M05+M06 → M07 → M08 (advisory).

`[planner-gate: advisory, risks-open]`

Full sequencing, gates, and evidence list: `.xbgst/plans/2026-08-21-prime-agent-routing.md`.
