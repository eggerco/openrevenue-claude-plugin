---
name: audience-devices
description: Break down a site's audience by device, browser and operating system in OpenRevenue. Use when the user asks what devices visitors use, the mobile versus desktop split, which browsers or operating systems to support or test, or whether a problem is specific to one browser. Not for countries, sources, funnels or page speed.
---

# Audience by device, browser and OS

Describe the technology mix of a site's visitors, using the OpenRevenue connector.

1. **Pick the site** by `domain`. If it is unclear, call `list_projects` and ask when there is more than one.
2. **Pick the period.** Use what the user said, else `30d`, since device mixes need a larger sample than a week (`7d`, `30d`, `90d`, `12m` and others are accepted).
3. Call what the question needs:
   - Mobile, desktop and tablet split: `get_devices`
   - Browsers: `get_browsers` (optional `limit`, 1–100)
   - Operating systems: `get_os` (optional `limit`, 1–100)
4. To look at one slice, pass `filters` as `key|operator|value` strings, for example `device|is|Mobile` to see the browsers of mobile visitors.

## Answering

- Give shares as percentages computed from the returned counts, alongside the counts.
- For "what should we support or test" questions, list the browsers or systems that together cover most visitors and say what share that is.
- Use only what the tools returned. If the sample is small, say so rather than drawing a conclusion.
- If a tool returns an error or access is denied, say so plainly and stop.
