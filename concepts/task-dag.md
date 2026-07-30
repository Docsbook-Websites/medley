---
title: The Medley Task DAG — Decomposition and Routing
description: How Medley breaks a goal into a dependency graph, scopes context per step, and routes each task to the runtime and model that fits it.
---

# The task DAG

Medley decomposes a goal into a directed graph of tasks with explicit dependencies. That structure is what makes parallel agents safe instead of chaotic.

## Decomposition

The graph is built to the **information frontier** — as far as what is actually known supports, and no further. Tasks past that point get planned later, once earlier work reveals what they should be. This is why the opening plan is not the whole mission.

## Dependencies and scoped context

Each task carries its own scope. Parallel agents work on separate sub-tasks with clear handoffs, so two workers do not fight over the same edit. Dependencies decide what may run now and what waits.

## Per-task routing

Every task is routed to a runtime and a model:

- One model used many times, when consistency matters.
- Different models on different steps, when the steps differ in kind.
- Parallel or sequential, depending on the dependency edges.

Medley auto-discovers which runtimes are installed and logged in, and routes only among those. See [runtimes and routing](runtimes-and-routing.md).

## Why multi-agent beats one model alone

A single model doing everything carries the whole problem in one context window and one strategy. A graph lets each step get the context it needs and the model that suits it, and lets independent steps run at the same time.

## Related

- [How a mission works](../getting-started/how-missions-work.md)
- [Steering a running mission](../guides/steering-missions.md)
