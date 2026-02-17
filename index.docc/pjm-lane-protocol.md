# PJM lane protocol

> Canonical source: `todo3/provisioned/.wrkstrm/requests/...` (this file).

@Metadata {
  @TechnologyRoot
  @CallToAction(
    url: "https://discord.com/channels/1407786883773104278/1473414684513407026/1473414717564260474",
    label: "Discuss in chat"
  )
}

Status: [Backlog]
Owner: todo3/pjm

## Purpose

Create a repeatable, low-friction daily operating rhythm for the `#pjm-todo3` lane so:

- Work is always summarized as Now / Next / Blocked / Shipped.
- The day starts with a prebuilt "next actions" list.
- The triage state is captured in a provisioned artifact (deterministic, regenerable).

## Scope

In scope:

- Daily triage and status reporting for todo3 PJM lane.
- A provisioned triage artifact generated daily at 5:00am America/Los_Angeles.
- Posting the triage summary into `#pjm-todo3`.

Out of scope:

- Implementing feature work itself (coding requests live elsewhere and link back here).
- Release announcements outside this lane.

## Rollout Plan

- v0 (today):
  - Define the canonical triage format.
  - Generate and post a daily triage snapshot.
- v1:
  - Add topic taxonomy (process vs code) and stable topic slugs.
  - Add a lightweight archive view (by day) in provisioned output.
- Adoption gate:
  - 5 consecutive days of a 5:00am triage post with <= 1 manual fix per day.
- v2:
  - Pull canonical sources (request bundles, issues) automatically and reduce manual edits.

## Key Health Metrics

- Usage/compliance:
  - Daily 5:00am post present.
  - Same-day updates captured (no "orphan" work).
- Throughput:
  - Count of shipped items per day/week.
- Quality:
  - Oldest blocked age trending down.
  - No broken links in triage items.
- Sentiment:
  - "Can start work immediately after reading triage" (yes/no).

## Procedure

### Daily operations

1) 5:00am daily: generate provisioned triage output.
2) Post summary into `#pjm-todo3`.
3) During the day: any update in-lane must include:
   - next action
   - eta
   - blocker (or "none")

### Request workflow (new adoption rule)

4) When a new DocC request/protocol is created, also create a **dedicated discussion chat** (thread) in the **Requests channel**.
   - Thread name: `req: <request-slug>`
   - First message must include:
     - link to the DocC request (provisioned share URL)
     - a short summary (purpose + next action)
     - current status
5) The DocC request should include an external CTA that links to its discussion thread.
   - Use the DocC design system `@CallToAction(url: "…", label: "Discuss in chat")` pattern.
6) When a change is a process change, create/extend a protocol request under `todo3-protocols`.
7) When a change is implementation, create a coding request and link back to the protocol request that motivated it.

## Change Log

- 2026-02-17T19:10:00.072Z: Created.
