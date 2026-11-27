# KDP Book Quality Check

## Check the cover before upload

- Measure the cover against the exact trim size and bleed that KDP requires for that book before you open any upload form.

- Confirm the interior page count and binding so the spine width in the file matches the spine width KDP calculates.

- Confirm every image is at least 300 DPI at its printed size and that no placeholder text remains anywhere on the cover.

- Confirm the author name, title and imprint on the cover match the metadata you will enter so the cover and the listing agree.

- Scan the full cover for every possible failure, not only the issue KDP flagged on a previous book.

- Check that all text sits at least 180 px inside the trim on every edge and that no text crosses a fold, spine edge or bleed edge.

- Rebuild the barcode area as a solid white rectangle of 600 by 360 px with no border and no ISBN placeholder text inside it.

- Leave a narrow spine blank when the spine is too narrow for safe spine text rather than squeezing text to its edges.

- Check the back cover, spine and front cover together at full size for cropping, low resolution, dark muddy areas and title text that a thumbnail could hide.

## Scan the full interior before you call it clean

- Extract the full text from the source files before you report any result.

- List every question title and heading in order and compare the normalized wording of each one against every other one.

- Flag every exact duplicate and every near duplicate that asks the same question in different words.

- Replace each duplicate with a new question on a different subject and record the page where the replacement sits.

- Count the questions or items against the promised total and report any shortfall before you call the count complete.

- Open each illustration beside the text on its page and name the subject in the text and the subject in the image.

- Flag any page where the image shows a different subject from its text and treat that page as blocked.

- Do not reuse an old illustration for a new question when its subject does not match the new text.

- Hold the book from upload while any page carries a mismatched illustration and name the blocked pages in your report.

- Do not call a book clean from a spot check or a sample of pages.

- Rebuild from the source files after any fix and run the full scan again on the rebuilt files before you report the result.

## Verify in the previewer and after review

- Run the KDP Print Previewer and clear every issue it shows before you submit the book.

- Record the previewer result and the exact cover file you submitted so a later check compares the same file.

- After review completes, open the live bookshelf thumbnail and the live product page and confirm the title stays readable and nothing looks cropped.

- Reupload a corrected high resolution cover when the live thumbnail still looks cropped or wrong after review ends.

- Report the book as done only after the previewer is clean, the full interior scan and the illustration check pass, and the post review thumbnail check passes.

- Name the scan you ran and the pages you checked when you report a clean result and name any check you could not run.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Fix the source cover file and re-export it rather than patching a flattened export when a dimension or barcode area is wrong.

- Fix the source file and re-export it rather than patching a flattened export when a duplicate or a mismatch is found.

- Check the next book in the queue with the same scan before its upload day so one fix helps the whole batch.

- Ask the user to approve one corrected page before you rebuild a whole batch when several pages need new art.
