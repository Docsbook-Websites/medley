---
title: How a Medley Mission Works End to End
description: Understand the mission loop — interview, contract, decomposition, launch, supervision, engine review, and finalize — and which part is yours versus the engine's.
---

# How a mission works

A mission is a contract plus a plan plus a supervised fleet. Knowing which part belongs to you and which belongs to the engine makes the whole thing predictable.

## The loop

1. **Interview** — Medley asks what the outcome is, what it may spend, and what needs your approval.
2. **Contract** — the target, the budget, the deadline, and the sign-off gates get fixed.
3. **Decompose** — the goal becomes a task graph, stopping at the information frontier rather than guessing past it.
4. **Plan submit** — you see the proposed graph with each task's routed runtime and model.
5. **You approve** — the contract and its opening plan.
6. **Start** — workers launch in your repo, in parallel.
7. **Supervise** — you steer, resolve attention items, and read digests.
8. **Engine review** — each finished batch is checked against the contract; unmet contracts generate the next batch.
9. **Finalize** — you get the receipt.

## Who does what

The mission agent — your chat session — plans, routes, launches, supervises, steers, and relays. It does **not** execute the mission's tasks itself.

The workers execute. Each is a fresh agent session on the runtime its task routed to.

The engine reviews. It holds the mission open until the contract is met, verifies the result, and proposes the remaining work. That review loop is why a mission survives a plan that turned out to be incomplete.

## Why the contract matters

Without a contract, an agent stops when it runs out of plan. With one, the engine has something to check the work against — so "done" means the outcome you named, not the last task in a list.

## Next steps

- [Missions vs sessions](../concepts/missions-vs-sessions.md) — the conceptual shift.
- [The attention queue](../concepts/attention-queue.md) — how your input gets requested without constant babysitting.
