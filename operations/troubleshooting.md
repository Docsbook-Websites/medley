---
title: Medley Troubleshooting — Engine, Tools, and Host Issues
description: What to do when the medley MCP tools are not registered, the engine has not booted yet, or a Codex thread is running a stale cached plugin.
---

# Troubleshooting

## The `medley` tools are not registered

Everything a mission does runs through the `medley` MCP tools. On a fresh install the engine binary and daemon may not be up yet, so those tools are not registered — and planning against absent tools wastes the whole interview.

Tool names are host-specific:

- Claude Code namespaces plugin MCP tools as `mcp__plugin_medley_medley__<tool>`.
- Codex uses `mcp__medley__<tool>`.

Probe the form matching your host before planning. Whichever form you find, keep using that prefix.

## Tools absent in Claude Code or Codex

This is recoverable, not a dead end — the engine simply is not up yet. On Codex the MCP server starts lazily, so the first call also pays daemon boot and, on a fresh install, the engine download. Start a new thread once setup settles, then run the mission.

## Tools absent on some other host

Medley runs behind the plugin wiring of Claude Code or Codex. On any other host its MCP server cannot connect, and no reconnect, restart, or `/mcp` changes that. Do the task directly instead.

## Codex is running an old version after an update

Codex binds a plugin's tools at thread start and runs its cached copy, not the source. After `codex plugin add medley@medley`, start a **new thread**.

## A worker looks stuck

Open [the dashboard](../guides/dashboard.md) to see the raw stream, then steer or kill that worker in plain language — see [steering a running mission](../guides/steering-missions.md).

## Related

- [Install Medley](../getting-started/install.md)
- [Updating Medley](../guides/updating.md)
