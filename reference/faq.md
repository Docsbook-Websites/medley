---
title: Medley FAQ — Product, Privacy, and Comparisons
description: Straight answers to the questions founders ask before delegating real work to agents: what /mission does, where data lives, what it costs, and what it does not replace.
---

# FAQ

## Product basics

**What does `/mission` actually do?**
You give Medley a prompt — like "get my first 10 customers." `/mission` turns it into a full multi-agent plan: the target, the budget, the deadline, and what to check with you first. Then it runs a coordinated team of agents on the steps.

**Do I need to know how to code?**
No. Medley is built for delegating work — research, outreach, reporting, hiring, ops, and engineering. You describe outcomes; your agents carry out the steps.

**Which agents does Medley work with?**
Medley is a Claude Code and Codex plugin. Missions run multi-agent plans using the models you already have access to.

**How many agents can I run at once?**
Medley is built for parallel missions across multiple agents and projects. The attention queue scales with your fleet — you see only what needs you.

**How do you prevent agents from conflicting?**
Medley decomposes work with explicit dependencies and scopes context per step, so parallel agents work on separate sub-tasks with clear handoffs.

## Privacy and control

**Does Medley act without my permission?**
No. Agents run inside the guardrails you set, and Medley asks before anything sensitive — publishing, sending outbound, spending, or contacting people. You grant more autonomy at your own pace.

**Where does my data live?**
On your Mac. Medley is local-first and bring-your-own-keys — your missions, keys, and agent conversations stay on your device, not on our servers. See [security and privacy](../operations/security-and-privacy.md).

## Comparisons and objections

**Is Medley a replacement for Claude Code?**
No. Medley is a plugin for Claude Code. You still work in Claude Code — Medley adds mission planning, multi-agent execution, and a URL to see the structure.

**Does Medley replace my terminal?**
No. You stay in your host. Medley adds `/mission` — planning, coordination, and a URL for the structure.

**How is this different from a project dashboard?**
A dashboard shows status. Mission control also routes work to agents, enforces sign-off gates, and keeps mission context alive across sessions — so agents can act, not just report.

**How is this different from CI/CD or Zapier?**
Those tools run deterministic scripts. Multi-agent workflows involve agents making judgment calls, producing variable outputs, and needing human review. Medley orchestrates that kind of work.

**What does it cost?**
Medley is free. It uses the models you already have access to. The cost is your own agent usage.

## Related

- [Install Medley](../getting-started/install.md)
- [Missions vs sessions](../concepts/missions-vs-sessions.md)
