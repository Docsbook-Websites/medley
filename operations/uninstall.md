---
title: Uninstall Medley and Clean Up Everything
description: Removing the plugin is enough — the orphaned service tears itself down. Or run the uninstaller first to purge mission history and every edit Medley made.
---

# Uninstalling

Just removing the plugin is enough. Medley cleans up after itself.

Neither host has a plugin-uninstall hook, so the running background service notices it has been orphaned — within about a minute, and never mid-mission — and tears itself down: its LaunchAgent, its launcher, and every downloaded engine binary on every host, around 250 MB in all.

```
/plugin uninstall medley                    # Claude Code
codex plugin remove medley@medley           # Codex
```

## What is kept

Your mission history, provider config, and any BYOK keys stay, so reinstalling picks up where you left off. If you never ran a mission, `~/.medley` is removed too and nothing is left behind.

## Removing everything immediately

To purge mission history plus the `/etc/hosts`, statusline, and shell-alias edits, run the uninstaller **first** — it lives inside the plugin, so the host command above would delete it:

```
~/.claude/plugins/cache/medley/medley/*/scripts/uninstall.sh
```

Then run the host uninstall command.

Flags:

- `--dry-run` shows the plan and touches nothing.
- `--keep-data` keeps the mission database, `config.toml`, and your BYOK keys. The background service is removed either way — it is part of the plugin.

To see exactly what a purge would remove:

```
medley-engine service purge-plan
```

## Related

- [Security and privacy](security-and-privacy.md)
