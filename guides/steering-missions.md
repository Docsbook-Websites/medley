---
title: Steer a Running Medley Mission in Plain Language
description: Redirect a task, kill a stuck worker, or change an approach while the mission is in flight — without restarting the plan or rewriting a prompt.
---

# Steering a running mission

A mission is not fire-and-forget. While workers run, you stay in the chat and steer with ordinary sentences.

## Things you can say

- "Tell the UI task to use shadcn."
- "Kill the flaky one."
- "Hold the deploy step until I review the migration."
- "This is going the wrong way — re-plan the second half."

Medley relays your intent to the right worker or adjusts the graph. You do not need to know task ids.

## Resolving attention items

When a worker hits a sign-off gate, it lands in [the attention queue](../concepts/attention-queue.md). Answer it and the mission continues. Unanswered gates hold that branch, not the whole mission.

## Reading digests

Rather than streaming every worker into your chat, Medley relays digests — what finished, what the engine's review said, what needs you next. For the raw stream, open [the dashboard](dashboard.md).

## When the plan was wrong

Say so. The engine re-plans against the contract rather than forcing the original graph to completion. Changing direction mid-mission is expected, not a failure state.

## Related

- [How a mission works](../getting-started/how-missions-work.md)
- [The dashboard](dashboard.md)
