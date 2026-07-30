---
title: Install Medley in Claude Code or Codex
description: Add the Medley plugin to Claude Code or Codex in three commands, then let your next session download the mission engine automatically. No Node, no build step.
---

# Install Medley

Medley ships as a plugin. The mission engine is a separate self-contained binary that the plugin downloads for you on first run, so there is no repository to clone and no build toolchain to set up.

## Claude Code

Inside a Claude Code session:

```
/plugin marketplace add Spine-AI/medley
/plugin install medley
```

That is the whole install. Your **next session** downloads the engine automatically — a single code-signed binary from `engine.getmedley.ai`, with the public GitHub Release as a fallback. No token, no npm, no `--plugin-dir`.

## Codex CLI

Codex 0.145 or newer:

```
codex plugin marketplace add https://github.com/Spine-AI/medley
codex plugin add medley@medley
```

Two differences to expect on Codex:

- The skill is invoked as `$medley:mission`, because Codex plugins cannot add slash commands.
- Codex asks you to approve Medley's hooks the first time each one fires. Approve them all — the `Stop` hook is how a mission keeps supervising itself on that host.

## What happens on first session

1. The plugin resolves an engine path and downloads the pinned engine version.
2. The download is verified against the release `SHA256SUMS`.
3. A single background daemon starts and binds to `127.0.0.1:8730`.
4. In Claude Code, a mission statusline is wired into your settings — see [the statusline guide](../guides/statusline.md).

Once that settles, type `/mission` and go to [your first mission](first-mission.md).

## Next steps

- [Requirements](../operations/requirements.md) — check your Mac and CLIs are supported.
- [Your first mission](first-mission.md) — run something real.
- [Troubleshooting](../operations/troubleshooting.md) — if the `medley` tools are not registered yet.
