---
title: The Medley Statusline in Claude Code
description: A one-line mission ticker showing title, state, and task progress — how Medley sets it up, how it stays fast, and how to turn it off.
---

# The statusline

In Claude Code, Medley shows a one-line mission ticker:

```
medley ▸ <title> · RUNNING · 4/9
```

It is empty when no mission is active. Codex has no user-supplied statusline, so this is Claude Code only.

## How it gets configured

A `statusLine` entry cannot ship in a plugin manifest — Claude Code ignores it. So on the first session Medley writes one into your `~/.claude/settings.json`, pointing at a stable copy it refreshes each session at `~/.medley/statusline.sh`. That copy survives plugin-cache pruning and plugin updates.

Medley heals an older Medley statusline that still points into the versioned plugin cache. It never touches a statusline you configured yourself, and it never re-adds one you removed.

## Why it stays fast

Claude Code re-invokes the statusline on a roughly 300 ms throttle. Medley serves a short-TTL per-repo cache — a file read — within `MEDLEY_STATUSLINE_TTL` seconds (default 2, set `0` to disable), cold-starting the engine only on a cache miss. The cache is keyed and verified per repo, so one repo's mission can never show up in another.

## Turning it off

Delete the `statusLine` block from your `settings.json`. Medley will not re-add it. A full uninstall strips it out for you — see [uninstalling](../operations/uninstall.md).

## Related

- [The dashboard](dashboard.md)
