# Paid Clipping Campaigns

## Screen a campaign before you join it

- Join only free campaigns and never pay for a join or a VIP tier.

- Read the brief and category before you join and skip gambling, casino and case opening campaigns.

- Skip a campaign that asks for a deposit or any payment before work starts.

- Skip a campaign that pays only viewers in regions that exclude the user location.

- Skip a campaign marked adult only or 18 plus, even when its brief looks harmless.

- Flag a campaign for the user and do no work on it when it promotes cannabis, peptides, a memecoin or another restricted product.

- Record every skipped campaign with its reason in the same run.

## Check the persistent skip list before you join

- Read the persistent skip and pending list at ~/workspace/goals/whop-content-rewards-campaigns/files/clipping-skip-list.md before you open any campaign page, and create the file with empty skip and pending sections when it does not exist yet.

- Never join a campaign on the skip list, even when the listing describes it in new words or under a new category.

- Never join a campaign on the pending list while the user decision is still open, and flag it for the user instead of joining it.

- Match a campaign by name and by creator or brand name, since the same campaign can return under a new title or a new category description.

- Add a skipped campaign to the skip list with its reason in the same run, and add a flagged campaign to the pending list with the question the user must decide.

- Add a campaign to the skip list when the user says to skip it or to leave it alone, even when you did not join it.

- Remove a campaign from the pending list only after the user says to join it or to skip it, and record that decision with the date.

## Check budget and brief before you build

- Read the remaining budget and fill level at build time and build first for campaigns with budget left.

- Do not build for a campaign that is filled or delisted.

- Read the rate, the minimum payout and the per clip view minimum from the brief before you cut.

- Tell the user what each clip needs to earn to reach the minimum payout.

- Submit each clip within 30 minutes of posting when the brief asks for that timing.

## Verify a budget figure before you sound an alarm

- Read the remaining budget and creator count at least twice in separate reads before you report a filling fast alarm.

- Treat two readings that agree as the figure to report, and name both readings in the report.

- Treat readings that disagree as an unresolved range, report the range without a filling fast alarm, and read again before you build on the figure.

- Correct the earlier figure in the same run when a later reading supersedes it, and name the superseded figure so it is not reused.

- Do not copy a budget figure into memory or a standing report until two readings agree on it.

## Cut only from a verified HD source

- Check the source with ffprobe before you cut and record its width and height.

- Cut only from a 1080p VOD source such as a Twitch, Kick or YouTube VOD.

- Reject a soft live capture and rebuild from the HD VOD when the capture is soft.

- Never upscale a 720p or 360p frame to 1080p and never call an upscaled clip HD.

## Lay out the facecam and check the finished clip

- Keep the creator face and reaction visible in every clip and never crop the facecam out.

- Put the facecam on top at full width with the gameplay below when the source has a facecam.

- Put one short hook line on top for each moment and keep it readable at phone size.

- Watch the full finished clip and check sharpness, facecam, captions and audio.

- Run ffprobe on the finished file and confirm 1080x1920, a non empty file and a clean decode before you report it delivered.

- Report the exact file path and the source resolution with every delivered clip.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Repurpose a built clip for a different live campaign only when its brief and footage rules allow it.

- Build the highest rate campaign with budget left first when several campaigns share the same footage.
