---
name: site-performance
description: Report a site's Core Web Vitals and page speed from OpenRevenue real-visitor data. Use when the user asks whether their site is fast, about Core Web Vitals, LCP, INP, CLS, TTFB or FCP, or whether performance got better or worse after a release.
---

# Site performance (Core Web Vitals)

Report page-speed metrics measured from real visitors, using the OpenRevenue connector.

1. **Pick the site** by `domain`. If it is unclear, call `list_projects` and ask when there is more than one.
2. **Pick the period.** Use what the user said, else `7d`. To judge a release, compare the period before it with the period after it.
3. Call `get_performance` with `domain` and `period`.

## Reading the numbers

Rate each metric against Google's published Core Web Vitals thresholds:

| Metric | Good | Needs improvement | Poor |
| --- | --- | --- | --- |
| LCP (Largest Contentful Paint) | up to 2.5 s | up to 4 s | above 4 s |
| INP (Interaction to Next Paint) | up to 200 ms | up to 500 ms | above 500 ms |
| CLS (Cumulative Layout Shift) | up to 0.1 | up to 0.25 | above 0.25 |
| FCP (First Contentful Paint) | up to 1.8 s | up to 3 s | above 3 s |
| TTFB (Time to First Byte) | up to 0.8 s | up to 1.8 s | above 1.8 s |

The tool returns `avg_lcp`, `avg_inp`, `avg_fcp` and `avg_ttfb` in milliseconds, `avg_cls` as a unitless score, and `sample_count`, the number of measurements behind them. Convert milliseconds to seconds where the table uses seconds.

These are averages for the period. Google assesses the 75th percentile, so say that these are averages when you give a rating, and mention the sample count when it is small.

## Answering

- Give each returned metric with its value, its unit and its rating. Lead with the worst one.
- Report only metrics the tool returned. If a metric is missing, the site has no measurements for it in that period; say so.
- Offer one concrete next step for the worst metric only if the user asks what to do.
- If the tool returns an error or access is denied, say so plainly and stop.
