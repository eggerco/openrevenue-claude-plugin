---
name: visitor-activity
description: Look at recent individual visits in OpenRevenue. Use when the user asks who visited recently, wants the latest visitors or sessions, asks what a particular visitor did, or wants to trace one visitor's journey through the site.
---

# Visitor activity

List recent visitors and walk through one visitor's journey, using the OpenRevenue connector. Visitors in OpenRevenue are anonymous: there are no names or email addresses.

1. **Pick the site** by `domain`. If it is unclear, call `list_projects` and ask when there is more than one.
2. For recent visitors, call `list_visitors` with `domain`, `period` (what the user said, else `24h`) and `limit` (10 unless the user asks for more, at most 100). Use `offset` to page further only when asked.
3. For one visitor's journey, call `get_visitor` with `domain` and the `visitorId` taken from a `list_visitors` row. Never make up a visitor id.

## Answering

- For a list, show a compact table: when, country, device, source and pages viewed, using the fields the tool returned.
- For a journey, give the pages in order with times, and where the visitor came from.
- Do not speculate about who a visitor is, and do not try to identify a person from location or device details.
- If a tool returns an error or access is denied, say so plainly and stop.
