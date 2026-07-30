---
title: Medley Requirements — Supported Macs, Hosts, and CLIs
description: What Medley needs to run: an Apple Silicon Mac, the claude CLI, and optionally the codex and agent CLIs to widen the routing pool.
---

# Requirements

## Platform

- **macOS on Apple Silicon (arm64).** The engine is a self-contained binary, so Node is not required.
- Intel Macs are not supported. On other platforms the plugin no-ops cleanly rather than half-working.

## Required CLI

- **`claude`** on your `PATH`. Workers spawn through the Claude Agent SDK so they use your subscription auth.

## Optional CLIs

Each one you add widens the routing pool:

- **`codex`** — run `codex login` to add Codex workers.
- **`agent`** — from `cursor.com/install`, run `agent login` to add Cursor workers.

Any subset works. Medley auto-discovers which of these are installed and logged in, and routes only among those.

## Cost

Medley is free. The only cost is your own model usage through the agents you already have.

## Related

- [Install Medley](../getting-started/install.md)
- [Runtimes and routing](../concepts/runtimes-and-routing.md)
