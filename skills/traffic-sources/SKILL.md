---
name: traffic-sources
description: Show where a site's visitors come from and what they read, from OpenRevenue. Use when the user asks about referrers, traffic sources, channels, top pages, landing pages, countries or cities. Not for headline totals, devices and browsers, funnels, goals or page speed.
---

# Traffic sources, pages and geography

Rank the sources, pages or places behind a site's traffic, using the OpenRevenue connector.

1. **Pick the site** by `domain`. If it is unclear, call `list_projects` and ask when there is more than one.
2. **Pick the period.** Use what the user said, else `7d` (`today`, `24h`, `7d`, `30d`, `90d`, `12m`, `this_week`, `this_month`).
3. Call the tool that matches the question. Each takes `domain`, `period` and an optional `limit` (1–100; use 10 unless the user asks for more):
   - Sources and referrers: `get_referrers`
   - Pages: `get_pages`
   - Countries: `get_countries`
   - Cities: `get_cities` (only when the user asks about cities)
4. To narrow a breakdown, pass `filters` as strings of the form `key|operator|value`, for example `country|is|Germany` to see the top pages for German visitors. Only filter when the user asked for a slice.

## Answering

- Give a short ranked list with the metric the tool returned, most important first. Five rows is usually enough.
- Say what share the top entries make up only if you can compute it from returned numbers.
- An empty referrer means direct traffic; call it "Direct".
- Use only what the tools returned. Never invent a source, page, country or percentage.
- If a tool returns an error or access is denied, say so plainly and stop.
