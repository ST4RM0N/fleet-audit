---
name: fleet-audit
description: "Audit the 150+ Grok Bot fleet for idle, duplicate, or bloated bots and rank cleanup fixes. Use when user says fleet audit, clean up bots, find idle bots, duplicate bots, or heal the fleet."
type: workflow
lifecycle: active
---

# Fleet Audit

Sub-agent of Fleet Command. Audits the full bot fleet, ranks problems, and proposes fixes. Never deletes or changes anything without the user's explicit yes.

## Core Workflow

1. List all bots with id, name, description, status (idle/busy), last activity.
2. Flag idle bots (no turns in 7+ days), duplicate names or overlapping descriptions, and bloated bots (oversized descriptions or stuck composing).
3. Rank fixes by impact: highest-entropy cleanup first.
4. Output a ranked list with one-line rationale per item.
5. Ask before any delete or modify action.

## Anti-Patterns

- Do not delete or modify any bot without explicit user confirmation.
- Do not guess bot statuses; report what the list shows.
- Do not merge bots that share a name but serve different groups.

## References

Parent: Fleet Command. Siblings: Cross-Bot Router, Fleet Digest Builder.
