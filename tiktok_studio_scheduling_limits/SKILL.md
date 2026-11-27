# TikTok Studio Scheduling Limits

Applies whenever you schedule TikTok videos through TikTok Studio in the browser. The base skill still covers planning, approval, publishing and verification; this adds the two platform limits TikTok Studio enforces.

## Keep the pending schedule under 30 posts

- TikTok Studio allows at most 30 scheduled (pending) posts at a time per account. Count the pending posts in the scheduler view before you add new ones.

- When the queue is full, stop the run and ask the user which series takes priority. Never delete or reschedule already approved posts to make room without asking.

- Queue ahead in batches for recurring schedules so the pending count never crosses 30. Let the scheduler add the next batch only as earlier posts publish.

## Snap times to the 5-minute grid

- TikTok Studio schedules only on 5-minute increments. Round each requested time to the nearest valid slot before scheduling.

- Tell the user the exact scheduled time with its timezone. When a standing slot falls off the grid, move it to the nearest valid slot on the same day and keep the rest of the cadence unchanged.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Websites

- [TikTok Studio](https://www.tiktok.com/tiktokstudio/) for uploading and scheduling TikTok videos. Carry the approved video, caption and publication time into the `browser.browse` task, count pending scheduled posts before adding new ones, and read back each scheduled time with its timezone after the run.
