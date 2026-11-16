---
name: traffic-overview
description: Summarize how a site is doing in OpenRevenue. Use when the user asks how their site or traffic is doing, wants visitors, pageviews or sessions for a period, asks for a trend or chart over time, or wants to compare this period with the last one. Not for sources, pages, audiences, funnels, goals or page speed.
---

# Traffic overview

Report headline traffic for one site from the user's OpenRevenue account, using the OpenRevenue connector.

1. **Pick the site.** Sites are addressed by `domain` (for example `example.com`), never by an id. If the user named one, use it. Otherwise call `list_projects`: with one project, use it; with several, ask which.
2. **Pick the period.** Use what the user said, else `7d`. Accepted values include `today`, `24h`, `7d`, `30d`, `90d`, `12m`, `this_week` and `this_month`.
3. Call `get_project_stats` with `domain` and `period` for pageviews, visitors, sessions and average visit duration.
4. If the user asked about a trend, a chart, or "over time", also call `get_timeseries` with the same `domain` and `period`, and describe the shape: the peak, the low, and whether it is rising or falling.
5. To compare periods, call `get_project_stats` once per period and state the change as both an absolute number and a percentage.

## Answering

- Lead with the number the user asked about, then one or two supporting figures. Keep it to a few sentences unless they asked for a report.
- Name the site and the period in the answer, so the figures cannot be misread.
- Use only numbers the tools returned. Never estimate, round up a guess, or fill a gap.
- If a tool returns an error or the account has no access to that site, say so plainly and stop. Do not retry with a different domain you made up.
