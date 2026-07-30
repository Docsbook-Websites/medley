---
title: Medley Changelog — Plugin and Engine Releases
description: What shipped in each Medley plugin release, including statusline auto-configuration, the engine version handshake, and atomic engine-path writes.
---

# Changelog

The plugin version tracks the engine version it pins. This project follows semantic versioning.

## 0.6.4 — 2026-07-21

Plugin-only maintenance release, tracking engine v0.6.3 with no engine change.

### Changed

- **The statusline is auto-configured for every user.** `statusLine` cannot ship in a plugin manifest — Claude Code ignores it — so `session-start.sh` writes it into `~/.claude/settings.json` on first session, pointing at the stable `~/.medley/statusline.sh` copy it refreshes each run. It heals an older Medley statusline still pointing into the versioned plugin cache, never touches one you configured yourself, and never re-adds one you removed. A full uninstall strips it back out.
- **The statusline slow path serves a short-TTL per-repo cache.** Claude Code re-invokes the statusline on a roughly 300 ms throttle, and each call previously cold-started the engine binary and opened SQLite. It now serves a cached line within `MEDLEY_STATUSLINE_TTL` seconds (default 2, `0` disables), cold-starting the engine only on a miss. The cache is keyed and verified per repo.

### Fixed

- `session-start.sh` initialized the `--suggest` gate so the SessionStart starter menu is emitted as intended.

## 0.4.10 — 2026-07-16

Tracks engine v0.4.10 — steadier auto-updates, a redesigned settings dashboard, and a contract-anchored mission review loop.

### Changed

- **`mcp-headers.sh` sends an `X-Medley-Engine-Pin` header** — the plugin's pinned engine version — so the daemon can detect it is serving an older engine than the session expects and roll forward. Worker sessions send it too, but a worker never triggers a roll of its own parent daemon.
- **`ensure-engine.sh` writes `~/.medley/engine-path` atomically** (tmp plus rename) so the daemon's stable launcher can never read a torn path.

## Related

- [Updating Medley](../guides/updating.md)
