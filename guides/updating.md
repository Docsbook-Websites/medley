---
title: Update Medley and Its Mission Engine
description: Refresh the plugin, let the pinned engine version download itself, and understand how the running daemon rolls forward without ever rolling back.
---

# Updating Medley

Engine updates ship by bumping the plugin. Refresh the marketplace, then update:

```
/plugin marketplace update medley
/plugin update medley
```

On Codex:

```
codex plugin marketplace update medley
codex plugin add medley@medley
```

Then start a **new thread** on Codex — it binds plugin tools at thread start and runs its cached copy.

## What happens next

The next session detects the new pinned engine version and downloads it automatically. The running engine daemon rolls itself forward to the new version on next use — only ever forward, never back to an older one — then prunes the superseded binaries so only the current engine remains.

## The version handshake

Sessions send the plugin's pinned engine version to the daemon, so a daemon serving an older engine than the session expects knows to roll forward. Worker sessions send it too, but a worker never triggers a roll of its own parent daemon.

## Related

- [Changelog](../reference/changelog.md)
- [Troubleshooting](../operations/troubleshooting.md)
