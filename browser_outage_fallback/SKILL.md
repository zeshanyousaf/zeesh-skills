# Browser Outage Fallback

## Recognize a platform outage

- Treat a repeated browser failure with the same platform error as a platform outage, not as a failure in the task itself.

- Stop treating each blocked task as a separate bug when the same error blocks Blogger and TikTok and Gumroad and KDP and Whop work in the same window.

- Name the outage plainly in your report and name every queued item it blocks.

## Retry once and then stop

- Probe the browser once after the first failure and record the exact error that comes back.

- Stop autonomous retries after that one probe and do not run a chain of retries on the same outage.

- Tell the user that further retries are unlikely to help until the outage clears.

- Run one more single probe only when the user explicitly asks for another try, then report that result and stop again.

## Preserve the queue and hand over phone steps

- Leave every queued item in place with its position and state file untouched so nothing posts twice when the browser recovers.

- Record the blocked reason on the queued item instead of marking the item failed for a logic reason.

- Hand the user exact phone or manual steps for the one item that matters most when the item cannot wait for recovery.

- Keep the rest of the queue waiting and say when the next scheduled run will pick it up.

- Report the outage once per task and do not send a new status message for each retry you did not run.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Use a connector or an API route for the same task when one exists, since that route may stay up while the browser is down.

- Do the parts of the task that need no browser first, such as preparing the post text and the media file, so the queued item is ready to publish on recovery.
