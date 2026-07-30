---
title: The Medley Dashboard — Watch Every Worker Live
description: Open the local dashboard with /dashboard to stream each worker, see the mission graph, and clear approvals from one page on your own machine.
---

# The dashboard

Open it any time during a mission:

```
/dashboard
```

The dashboard runs on your machine. The engine daemon binds to `127.0.0.1:8730` only — it is never exposed off-host, and both `/api` and `/mcp` require a local bearer token or a same-origin browser request.

## What it shows

- **The mission graph** — every task, its dependencies, its routed runtime and model.
- **Live worker streams** — what each parallel worker is doing right now.
- **Approvals** — sign-off gates waiting on you, clearable from the page.
- **Progress** — which batch is running and how the contract review landed.

## When to use it instead of the chat

The chat gives you digests and lets you steer. The dashboard gives you the raw picture. Reach for it when a worker looks stuck, when you want to see the structure rather than read about it, or when several approvals are queued at once.

## Related

- [The statusline](statusline.md) — the smaller, always-visible view.
- [Steering a running mission](steering-missions.md)
