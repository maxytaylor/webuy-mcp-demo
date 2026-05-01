# Skill: Experiment Brainstorm

**Trigger:** Use this skill when a user wants to identify what to experiment on, investigate a metric drop, or generate hypotheses grounded in real data. Phrases like "what should we test", "why is X dropping", "help me find experiment ideas", or "brainstorm" should trigger this skill.

---

## What this skill does

Runs a structured investigation across all connected data sources to surface experiment opportunities grounded in real signal — not gut feel. Produces a ranked list of hypotheses with supporting evidence from Mixpanel, session replays, past experiment results, and team context from Slack and Notion.

---

## Execution

### Step 1 — Pull quantitative signal from Mixpanel
- Query the relevant funnel for the past 28 days
- Identify the step with the largest absolute drop-off
- Segment by: new vs. returning users, device type, acquisition source
- Flag any metric that has moved more than 10% week-over-week
- Note which cohorts are most affected

### Step 2 — Check what the team already knows
- Search Slack for threads mentioning the affected funnel step or metric in the past 30 days
- Search the Notion experiment log for any past experiments touching the same step
- Summarise: what has already been tried, what was the result, what hypotheses were explored but not tested

### Step 3 — Check engineering constraints
- Pull the latest `experiment-constraints.md` from the GitHub repo
- Note: current sprint capacity, any known component issues, experiment infra limitations
- Flag anything that would affect feasibility or scope of a proposed experiment

### Step 4 — Sample session replays
- Pull 10–15 sessions from users who dropped off at the identified funnel step
- Pull 5–10 sessions from users who converted through that step
- Identify behavioural patterns: where do users hesitate, rage click, or dead click?
- Note any UI elements that appear to cause confusion

### Step 5 — Synthesise and rank hypotheses
Produce a ranked list of 3 experiment ideas. For each:

| Field | Content |
|---|---|
| **Hypothesis** | If we [change], then [metric] will [direction] because [reason] |
| **Evidence** | What from steps 1–4 supports this |
| **What's been tried** | Relevant past experiments from the log |
| **Feasibility** | Based on GitHub constraints — is this doable this sprint? |
| **Recommended scope** | Smallest version that tests the hypothesis cleanly |
| **Primary metric** | The one number that decides ship/no-ship |

---

## Output format

Start with a one-paragraph situation summary: what the data shows, what the team context added, what the replays revealed.

Then list the 3 hypotheses in rank order (most recommended first).

Close with a recommended next step: which hypothesis to brief first and why.

---

## Notes

- Do not recommend experiments that have already been run with a clear negative result (check the log)
- Always flag if the recommended experiment conflicts with sprint capacity or known technical issues
- The replay evidence should be specific — cite the behaviour observed, not just "users dropped off"
- This skill feeds directly into the Experiment Brief skill — output should be structured to make that handoff clean
