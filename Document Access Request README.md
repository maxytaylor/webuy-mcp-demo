# weBuy MCP Demo — Experiment Context Repo

This repo contains supporting context files used by MCP-connected AI agents running the weBuy experiment workflow. It is designed to be queried via MCP during live demo sessions.

---

## What's in here

| File | Purpose |
|---|---|
| `experiment-constraints.md` | Engineering constraints, sprint capacity, known component issues — keeps experiment briefs feasibility-aware |
| `experiment-log.md` | Running log of past experiment results — prevents re-running failed tests and surfaces institutional memory |
| `skills/brainstorm-skill.md` | The MCP skill definition that powers the Experiment Brainstorm stage |

---

## How this fits into the OADA loop

```
Observe    →  Mixpanel (funnel data) + Slack (team signals)
Analyze    →  Session replays + experiment-log.md (what we've tried)
Design     →  experiment-constraints.md (what's feasible) → Experiment Brief
Act        →  Mixpanel Experiments results → write back to experiment-log.md
```

MCP connects all of these in a single conversation thread. Context flows through each stage instead of getting lost at every handoff.

---

## Maintained by

Growth & Experimentation team — update `experiment-log.md` within 48hrs of concluding any experiment.
