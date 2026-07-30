---
title: Run Your First Medley Mission
description: Give Medley a goal, answer the interview, approve the plan, and watch parallel agents execute it. A walkthrough of the first mission end to end.
---

# Your first mission

A mission starts with an outcome, not a prompt. Type the goal and let Medley do the decomposition.

```
/mission ship the onboarding flow with tests and docs
```

## 1. The interview

Medley asks what it needs to plan well: what "done" looks like, what the budget and deadline are, and which steps need your sign-off before they run. Answer plainly. This is where the mission gets its contract.

## 2. The plan

Medley proposes a task graph. Each task shows the runtime it routed to and the model it will use. Read it before you approve — this is the cheapest moment to change the shape of the work.

If the plan looks wrong, say so in plain language. Medley re-plans rather than making you rewrite a prompt.

## 3. Approve and start

Say "go". Workers spawn in your repo, in parallel, on whichever runtimes are installed and logged in. Each worker inherits your setup: skills, MCP servers, project memory, permission grants.

## 4. Supervise

While it runs you can:

- Steer in plain language — "tell the UI task to use shadcn", "kill the flaky one". See [steering a running mission](../guides/steering-missions.md).
- Open the live view with `/dashboard`. See [the dashboard](../guides/dashboard.md).
- Watch the [statusline](../guides/statusline.md) ticker: `medley ▸ <title> · RUNNING · 4/9`.

## 5. Review and finish

When a batch finishes, the engine reviews it against the contract you set. If the contract is not met, the engine generates the next batch instead of closing early. The plan is the mission's opening moves, not its whole story.

At the end you get a receipt of what ran.

## What missions are good for

Use a mission for goals with two or more separable pieces — build with tests and docs, research A versus B and recommend, refactor one thing while migrating another. For a small single-step ask, skip the mission and do it directly.

## Next steps

- [How a mission works](how-missions-work.md) — the loop in detail.
- [The task DAG](../concepts/task-dag.md) — how decomposition and routing are decided.
