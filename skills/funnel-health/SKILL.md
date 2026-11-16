---
name: funnel-health
description: Report funnel conversion and drop-off from OpenRevenue. Use when the user asks how a funnel converts, where visitors drop off, which step loses the most people, or how signup or checkout conversion changed. Not for creating, editing or deleting funnels or goals.
---

# Funnel health

Report conversion and step-by-step drop-off for a funnel, using the OpenRevenue connector. This skill only reads.

1. **Pick the site** by `domain`. If it is unclear, call `list_projects` and ask when there is more than one.
2. Call `list_funnels` with the `domain`.
   - No funnels: say so, and offer to set one up (the `manage-goals-and-funnels` skill covers that).
   - One funnel, or one whose name clearly matches what the user said: use its `funnelId`.
   - Otherwise list the funnel names and ask which one.
3. Call `get_funnel_report` with `domain`, `funnelId` and `period` (what the user said, else `30d`).
4. To compare periods, call `get_funnel_report` once per period.

## Answering

- State the overall conversion rate first, with how many visitors entered and how many completed.
- Name the step with the largest drop-off, and give the drop as both a count and a percentage of the step before it.
- Use only figures from the report. Do not guess at why visitors leave; if the user asks why, say which step to look at and suggest checking that page's speed or sources with the other OpenRevenue skills.
- If a tool returns an error or access is denied, say so plainly and stop.
