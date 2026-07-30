---
title: Runtimes and Routing — Claude Code, Codex, and Cursor Workers
description: Medley auto-discovers the agent CLIs installed on your Mac and routes mission tasks among them, using your existing subscription auth.
---

# Runtimes and routing

Medley coordinates the agents you already use. It does not replace them and it does not ask for your credentials.

## Supported worker runtimes

- **Claude Code** — workers spawn via the Claude Agent SDK, using your subscription auth.
- **Codex** — add Codex workers to the pool with the `codex` CLI, logged in via `codex login`.
- **Cursor** — add Cursor workers with the `agent` CLI, logged in via `agent login`.

Any subset works. Medley auto-discovers whichever of these are installed and logged in, and routes only among the runtimes actually present.

## What a worker inherits

Each worker is a fresh agent session that starts with your full setup: skills, MCP servers, project memory, permission grants, and subscription auth. That is why a worker behaves like you would in that repo, not like a blank assistant.

## Bring your own keys

Medley is BYOK. Missions run on the models you already have access to. The plugin itself is free; the cost is your own agent usage.

## Where routing is decided

Routing is part of the plan you approve — each task in the graph shows the runtime and model it will use, before anything runs. See [the task DAG](task-dag.md).

## Related

- [Running Claude Code and Codex together](../guides/claude-code-and-codex.md)
- [Requirements](../operations/requirements.md)
