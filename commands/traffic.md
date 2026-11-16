---
description: Summarize a site's traffic for a period (default last 7 days)
argument-hint: "[domain] [period]"
---

Summarize traffic for an OpenRevenue site using the `traffic-overview` skill.

Arguments: $ARGUMENTS

Treat the first argument as the site's domain and the second as the period (for example `30d`). If the domain is missing, call `list_projects` and ask which site when there is more than one. If the period is missing, use `7d`. Include the trend from `get_timeseries`.
