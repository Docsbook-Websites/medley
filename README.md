---
title: Medley Documentation — Missions for Claude Code and Codex
description: Learn how Medley turns one goal into a supervised team of agents inside Claude Code and Codex. Install, run your first mission, and steer parallel workers from one place.
---

# Medley

Medley turns a complex, multi-step goal into a supervised swarm. You type `/mission <your goal>` inside Claude Code, and your session becomes the mission agent: it interviews you, decomposes the goal into a task graph with per-task model routing, and supervises parallel workers that run in your repo.

Those workers inherit your full setup — skills, MCP servers, project memory, permission grants, subscription auth. A live localhost dashboard streams every worker, surfaces approvals, and lets you steer in plain language.

Medley is free, local-first, and runs on your Mac with your own keys.

## Start here

- [Install Medley](getting-started/install.md) — three commands in Claude Code or Codex.
- [Your first mission](getting-started/first-mission.md) — from a goal to a running team of agents.
- [How a mission works](getting-started/how-missions-work.md) — the interview, the contract, the plan, the review loop.

## Understand the model

- [Missions vs sessions](concepts/missions-vs-sessions.md) — why the unit of AI work is changing.
- [The task DAG](concepts/task-dag.md) — decomposition, dependencies, and per-task routing.
- [The attention queue](concepts/attention-queue.md) — the human-in-the-loop layer that scales with your fleet.
- [Runtimes and routing](concepts/runtimes-and-routing.md) — Claude Code, Codex, and Cursor workers in one pool.

## Run it day to day

- [Steering a running mission](guides/steering-missions.md) — plain-language control while work is in flight.
- [The dashboard](guides/dashboard.md) — live worker streams, approvals, mission structure.
- [The statusline](guides/statusline.md) — a one-line mission ticker in Claude Code.
- [Running Claude Code and Codex together](guides/claude-code-and-codex.md) — coordination without conflicting edits.
- [Updating Medley](guides/updating.md) — how engine versions roll forward.

## Operations

- [Security and privacy](operations/security-and-privacy.md) — what runs on your machine, stated plainly.
- [Uninstalling](operations/uninstall.md) — full cleanup, including what is kept.
- [Requirements](operations/requirements.md) — supported hosts, CLIs, and platforms.
- [Troubleshooting](operations/troubleshooting.md) — engine not up, tools missing, Codex threads.

## Reference

- [FAQ](reference/faq.md) — product basics, privacy, and honest comparisons.
- [Changelog](reference/changelog.md) — what shipped in each plugin release.

Medley is a plugin, not a replacement. You stay in Claude Code; Medley adds mission planning, multi-agent execution, and a URL where the structure is visible.
