# OpenRevenue for Claude

Ask Claude about your [OpenRevenue](https://www.openrevenue.com) web analytics in plain language. The plugin connects Claude to your own OpenRevenue account and teaches it how to answer questions about traffic, sources, audiences, funnels, goals and page speed with your real numbers.

## What you can ask

- "How did example.com do this week compared with last week?"
- "Where is our traffic coming from this month, and which pages do they land on?"
- "What share of visitors are on mobile, and which browsers should we test?"
- "Where do people drop off in the signup funnel?"
- "Are our Core Web Vitals good? Did they change after Tuesday's release?"
- "Create a goal for the `signup` event with a target of 200."

## What is included

| Skill | Use it for |
| --- | --- |
| `traffic-overview` | Visitors, pageviews, sessions, trends, period comparisons |
| `traffic-sources` | Referrers, top pages, countries and cities |
| `audience-devices` | Device, browser and operating system mix |
| `funnel-health` | Funnel conversion and drop-off by step |
| `site-performance` | Core Web Vitals from real visitors |
| `visitor-activity` | Recent anonymous visitors and their journeys |
| `manage-goals-and-funnels` | Creating, changing and deleting goals and funnels |

Commands: `/openrevenue:traffic`, `/openrevenue:sources`, `/openrevenue:report` and `/openrevenue:sites`. Each takes an optional domain and period, for example `/openrevenue:report example.com 30d`.

## Install

In Claude Code:

```text
/plugin install openrevenue --marketplace eggerco/openrevenue-claude-plugin
```

On claude.ai and in Cowork, add the plugin from the plugin directory once it is listed there.

## Set it up

1. Add the plugin, then connect the **OpenRevenue** connector it brings along. On claude.ai and in Cowork that is on the plugin's Connectors tab; in Claude Code, run `/mcp`.
2. Sign in to OpenRevenue and approve access. You need an OpenRevenue account with at least one project.
3. Ask a question, or run `/openrevenue:sites` to check the connection.

## Data and permissions

- The plugin talks to one service: the OpenRevenue connector at `https://mcp.openrevenue.com/mcp`. It runs no code on your computer and contacts nothing else.
- You sign in with OAuth. Claude never sees your OpenRevenue password, and the plugin contains no credentials. You can revoke access at any time under Account → API in OpenRevenue.
- Claude can read analytics for the projects your OpenRevenue account can access. Visitor data in OpenRevenue is anonymous.
- Creating, changing or deleting goals and funnels requires an owner or admin on the project. Claude asks you to confirm before every such change, and deletions need your explicit approval.
- The questions you ask and the analytics returned are part of your conversation with Claude and are handled under Anthropic's terms. OpenRevenue's handling of your data is described in its [privacy policy](https://www.openrevenue.com/privacy).

## Support

- Documentation: <https://www.openrevenue.com/docs/api/mcp>
- Email: <support@openrevenue.com>

## License

MIT. See [LICENSE](LICENSE).
