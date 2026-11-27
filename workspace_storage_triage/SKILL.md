# Workspace Storage Triage

## Re-verify the disk reading at decision time

- Check free space again in the same run before you ask the user to delete anything.

- Treat a free space reading from an earlier message as stale when other builds have run since that reading.

- Record the time of the fresh reading and the exact free space it shows before you decide.

## Separate transient pressure from a persistent full disk

- List the large files that appeared or changed since the last check and name the builds that are still running.

- Treat the disk as transiently full when running builds hold large intermediates that will clear when they finish.

- Wait for running builds to finish or pause new encodes before you call the disk full.

- Treat the disk as persistently full only when a fresh reading after builds finish still shows too little free space for the next file.

## Free space safely before you touch a master

- Clear disposable intermediates first, such as stale stills in the temporary folder and finished render intermediates.

- Encode new work into the temporary folder first when the workspace is tight, then copy the finished file in once.

- Ask the user before you delete any master, alternate version, or source render, and name each file with its size.

- Never delete a master on a transient reading, and report that the pressure was transient when a later reading shows space again.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Split a large encode into a smaller delivery copy when the master is too large for the next step, and keep the master untouched.

- Schedule heavy builds one at a time when several builds in parallel keep filling the workspace.
