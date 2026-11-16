---
description: Show a site's top referrers and pages for a period (default last 7 days)
argument-hint: "[domain] [period]"
---

Show where an OpenRevenue site's traffic comes from, using the `traffic-sources` skill.

Arguments: $ARGUMENTS

Treat the first argument as the site's domain and the second as the period. If the domain is missing, call `list_projects` and ask which site when there is more than one. If the period is missing, use `7d`. Call `get_referrers` and `get_pages` with a limit of 10 and give two short ranked lists.
