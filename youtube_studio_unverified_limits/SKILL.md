# YouTube Studio Unverified Channel Limits

## Count the uploads already made today

- Open YouTube Studio before you plan a batch and count the videos already uploaded and scheduled that day for that channel.

- Treat an unverified channel as capped for the day once Studio refuses a new upload and name the count you reached before you plan more.

- Keep Shorts and long videos in the same daily count and keep the scheduled times you already set in the same list.

## Plan the batch inside the remaining allowance

- Put the highest priority video first in the batch and schedule the rest only while the daily allowance remains.

- Stop the batch at the first refusal and do not retry the same upload again that day.

- Schedule a refused video with an automatic thumbnail when its custom thumbnail cannot be set and add the custom thumbnail after verification.

- Tell the user the exact videos that went up with their scheduled times and the exact videos that remain with their planned times.

## Ask the owner for the one time verification

- Ask the user to complete the one time verification in YouTube Studio under Settings then Channel then Feature eligibility then Intermediate features and verify by phone number.

- Name verification as the only unblocker for the remaining uploads and custom thumbnails and do not promise the remaining uploads until the user confirms it is done.

- Resume the remaining queue in the same order once the user confirms verification and report each new scheduled time with its timezone.

## Available connectors

- [vidIQ](/opt/hatch/connectors/vidiq_mcp/CONNECTOR.md) for YouTube titles thumbnails and scripts.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Websites

- [YouTube Studio](https://studio.youtube.com/) for uploading and scheduling videos. Carry the approved video title description and publication time into the `browser.browse` task, count the uploads already made that day before you add new ones, and read back each scheduled time with its timezone after the run.

## Alternatives for better results

- Verify the channel before a launch day so a large batch does not meet the daily cap in the middle of the schedule.

- Upload the launch day long video before the later Shorts when only part of the batch can go up that day.
