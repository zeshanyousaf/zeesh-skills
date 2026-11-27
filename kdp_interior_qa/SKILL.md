# Check a KDP book interior before you call it clean

## Scan the full interior text

- Extract the full text from the source files before you report any result.

- List every question title and heading in order and compare the normalized wording of each one against every other one.

- Flag every exact duplicate and every near duplicate that asks the same question in different words.

- Replace each duplicate with a new question on a different subject and record the page where the replacement sits.

- Count the questions or items against the promised total and report any shortfall before you call the count complete.

## Check every illustration against its text

- Open each illustration beside the text on its page and name the subject in the text and the subject in the image.

- Flag any page where the image shows a different subject from its text and treat that page as blocked.

- Do not reuse an old illustration for a new question when its subject does not match the new text.

- Hold the book from upload while any page carries a mismatched illustration and name the blocked pages in your report.

## Report only what the full scan verified

- Report the book as clean only after the full scan and the illustration check both pass.

- Name the scan you ran and the pages you checked when you report a clean result and name any check you could not run.

- Do not call a book clean from a spot check or a sample of pages.

- Rebuild from the source files after any fix and run the full scan again on the rebuilt files before you report the result.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Check the next book in the queue with the same scan before its upload day so one fix helps the whole batch.

- Fix the source file and re-export it rather than patching a flattened export when a duplicate or a mismatch is found.

- Ask the user to approve one corrected page before you rebuild a whole batch when several pages need new art.
