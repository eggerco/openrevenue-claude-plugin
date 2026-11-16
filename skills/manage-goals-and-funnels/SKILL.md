---
name: manage-goals-and-funnels
description: Create, change or delete goals and funnels in OpenRevenue. Use when the user wants to set up a conversion goal, track an event or page as a goal, build or edit a funnel, or remove a goal or funnel. Not for reading funnel conversion; use funnel-health for that.
---

# Manage goals and funnels

Change the goals and funnels configured on a site, using the OpenRevenue connector. These tools write to the user's account and need an owner or admin on the project.

## Before any change

1. **Pick the site** by `domain`. If it is unclear, call `list_projects` and ask when there is more than one.
2. Look at what exists first: `list_goals` or `list_funnels` with the `domain`. Do not create a duplicate of something already there; point it out instead.
3. Tell the user exactly what you are about to create, change or delete, and wait for them to agree. Do this every time, including when the request seemed clear.

## Goals

- **Create:** `create_goal` with `domain`, `name` (up to 80 characters) and `type`. Types: `event`, `page`, `pageviews`, `visitors`, `visits`, `bounce_rate`, `visit_duration`, `views_per_visit`, `revenue`.
  - `event` needs `value` set to the event name; `page` needs `value` set to the page path (for example `/pricing`).
  - Add `target` (a positive number) when the user gives a target to reach.
- **Delete:** find the goal's id with `list_goals`, confirm with the user by name, then call `delete_goal` with `domain`, `goalId` and `confirm: true`.

## Funnels

- **Create:** `create_funnel` with `domain`, `name` and `steps`: between 2 and 8 steps, in order. Each step is `{ "type": ..., "value": ... }` where `type` is `pageview` (value: a page path), `event` (value: an event name), `outbound` (value: a link URL) or `exit` (value: a page path).
- **Change:** `update_funnel` with `domain`, `funnelId`, `name` and the complete new list of `steps`. It replaces all steps, so include the ones that stay.
- **Delete:** find the id with `list_funnels`, confirm with the user by name, then call `delete_funnel` with `domain`, `funnelId` and `confirm: true`.

## Rules

- Only set `confirm: true` after the user has agreed to that specific deletion in this conversation. Deleting cannot be undone.
- If you are unsure which event name or page path the user means, ask. Do not guess: a goal on the wrong event silently counts nothing.
- After a change, report what was created, changed or deleted, using the tool's response.
- If a tool reports missing permission, tell the user an owner or admin has to do it, and stop.
