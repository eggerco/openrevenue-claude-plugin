---
description: Write a short analytics report for a site (traffic, sources, pages, funnels, speed)
argument-hint: "[domain] [period]"
---

Write a short analytics report for an OpenRevenue site.

Arguments: $ARGUMENTS

Treat the first argument as the site's domain and the second as the period. If the domain is missing, call `list_projects` and ask which site when there is more than one. If the period is missing, use `7d`.

Gather, with the OpenRevenue connector:

1. `get_project_stats` for the period and for the period before it, to show the change.
2. `get_referrers` and `get_pages` with a limit of 5.
3. `list_funnels`; for each funnel (at most three), `get_funnel_report`.
4. `get_performance`.

Then write the report with these sections, each two or three sentences or a short list: **Summary**, **Traffic**, **Sources and pages**, **Funnels** (omit if the site has none), **Speed**. Use only numbers the tools returned, name the site and period at the top, and note any section where a tool returned an error instead of leaving it out silently.
