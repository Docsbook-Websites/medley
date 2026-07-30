---
title: Medley Security and Privacy — What Runs on Your Machine
description: A plain statement of what Medley downloads, what the daemon binds to, where mission state lives, and what telemetry does and does not contain.
---

# Security and privacy

What this plugin does on your machine, stated plainly.

## It downloads and runs a compiled binary

On session start the plugin downloads the Medley engine — a closed-source, self-contained executable — from `engine.getmedley.ai` (Cloudflare R2), falling back to the public GitHub Release. The version is pinned in `plugin/engine/version`, the download is verified against the release's `SHA256SUMS`, and the binary is Developer ID code-signed.

It is not notarized: a CLI fetched with `curl` is never quarantined, so Gatekeeper's notarization check does not apply.

## It runs a background daemon

The engine installs a single launchd LaunchAgent (`ai.getmedley.daemon`) so missions keep running between sessions. It binds to `127.0.0.1:8730` only. The MCP server and dashboard are never exposed off-host, and `/api` and `/mcp` both require a local bearer token or a same-origin browser request.

## Local state

Mission state lives in SQLite under `~/.medley/`. Nothing is synced anywhere.

## Telemetry is consent-gated and content-free

Usage telemetry (PostHog) and crash reports (Sentry) are sent only with consent, and events carry enums, counts, durations, and exit codes — never prompts, file contents, paths, or repo names. The pipeline currently ships disabled.

## Workers run with your own auth

Spawned workers use the `claude`, `codex`, and `agent` CLIs already installed and logged in on your machine. The plugin never handles your credentials.

## Permission gates

Agents run inside the guardrails you set, and Medley asks before anything sensitive — publishing, sending outbound, spending, or contacting people. See [the attention queue](../concepts/attention-queue.md).

## Licensing

The code in the public repository — the plugin shim of scripts, hooks, skills, and manifests — is MIT-licensed. Medley itself is not open source: the mission engine is proprietary software distributed only as a compiled binary and licensed for use with Medley. The MIT grant does not extend to the engine.

## Related

- [Uninstalling](uninstall.md)
