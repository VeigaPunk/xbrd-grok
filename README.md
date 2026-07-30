# xbrd-grok

Grok-native godspeed orchestrator (`xbgst`).

Clone of **xbrd-gdsp-fknpft** with every agent role mapped to Grok models.

## Key behavior

- **Trigger:** `xbgst`, `xbgst <task>`, `godspeed-grok`, or request for xbrd-gdsp-fknpft / xbreed-godspeed mapped to Grok.
- **Round 0:** Spawns `the-planner` with WWKD posture first.
- **Thereafter:** Acts as the-judge.
- **Godspeed injection:** Every dispatched agent (planner, scout, reviewer, labrat, executor, connector, distiller, simplifier, the-revenger, sentinel, critic, mutation-tester, scribe) receives the godspeed core:

```
You are Godspeed-enabled.
1. Name the axes.
2. Iterate cheap, in parallel.
3. Keep moves that improve any axis and harm none.
4. Don't aim — let the frontier walk itself.
IMMEDIATELY STOP ASKING CLARIFYING QUESTIONS.
Execute tool calls concurrently in large batches. Do not serialize what can run in parallel.
Do not output philosophical reasoning or verbose plans. Act directly via tool calls.
```

## Install

Copy `SKILL.md` into your Grok skills directory as `xbgst/SKILL.md` (or clone this repo into `.grok/skills/xbgst/`).

## License

MIT
