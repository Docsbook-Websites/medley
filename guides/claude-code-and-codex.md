---
title: Run Claude Code and Codex Together Without Conflicts
description: Coordination patterns for parallel coding agents — scoped context, explicit dependencies, and an edit-conflict gate that keeps two workers off the same file.
---

# Running Claude Code and Codex together

Running several coding agents at once fails in predictable ways: two workers edit the same file, context gets lost between tabs, and nobody notices a silent failure. Medley addresses each one structurally rather than by discipline.

## Scoped context per task

Each task in the graph carries its own scope. A worker sees what its step needs, not the whole mission — which is also why parallel workers do not blur into each other's problems.

## Explicit dependencies

Work that must be sequential is sequential because the graph says so. Work that is genuinely independent runs at the same time. You approve that shape before anything starts.

## Edit-conflict gating

The plugin ships an edit-conflict gate so parallel workers are kept off colliding edits rather than trusting them to coordinate.

## Mixed runtimes in one mission

A single mission can route one task to Claude Code and the next to Codex or Cursor, based on what fits. Medley routes only among the runtimes you actually have installed and logged in.

## Codex specifics

- The skill is `$medley:mission` — Codex plugins cannot register slash commands.
- Approve every hook Codex prompts for; the `Stop` hook is how supervision continues on that host.
- After a plugin update, start a **new thread**. Codex binds a plugin's tools at thread start and runs its cached copy, not the source.

## Related

- [Runtimes and routing](../concepts/runtimes-and-routing.md)
- [Updating Medley](updating.md)
