---
title: Missions vs Sessions — The Unit of AI Work
description: A session is ephemeral and stateless; a mission is persistent, decomposable, and reviewable. Why the shift matters once your agent work outgrows one chat.
---

# Missions vs sessions

A session is one conversation. It starts empty, holds context while you talk, and forgets when it ends. That is fine for a question and bad for a project.

A mission is the larger unit: it has a target, a budget, a deadline, explicit sign-off gates, and durable state that outlives any single chat.

## What breaks when work outgrows a session

- **Context evaporates.** Each new session re-explains the same background.
- **Failures go quiet.** Work spread across terminal tabs fails without anyone noticing.
- **Nothing accumulates.** Yesterday's decisions are not available to today's agent.

## What a mission adds

- **Explicit context** — carried across sessions instead of retyped.
- **Decomposition** — the goal becomes a reviewable graph, not one long prompt.
- **Receipts** — what ran, on which runtime, at what cost.
- **A review loop** — the engine checks the result against the contract rather than trusting the plan.

## The practical difference

With sessions you manage attention constantly, because nothing else is watching. With missions you manage exceptions — see [the attention queue](attention-queue.md).

## Related

- [How a mission works](../getting-started/how-missions-work.md)
- [The task DAG](task-dag.md)
