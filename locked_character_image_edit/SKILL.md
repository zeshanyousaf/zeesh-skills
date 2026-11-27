# Fix a locked character image by editing, not re-prompting

## Stop re-prompting after two failures on the same detail

- Count a text-to-image attempt as failed on a detail when the same wrong anatomy or feature returns in the output.

- Stop rewriting the prompt after the same detail fails twice, and say plainly that the text route is stuck on that detail.

- Do not spend the session on a third rewrite of the same prompt for the same failing detail.

- Name the exact failing detail in one short sentence so the next attempt targets it.

## Edit the best reference image instead

- Pick the closest good image of the character as the edit base, whether it is the original reference or the best generation so far.

- Edit that image with one short prompt that names what stays exactly the same first and then the single change.

- Change one thing per edit, and show the result before you ask for the next change.

- Keep every locked trait of the character named in the edit prompt when the trait must survive, such as colour, shape and outfit.

## Build from the fixed image

- Keep the first edit that preserves the character as the new reference for the rest of the session.

- Use that reference as the base for the next image or video prompt instead of returning to text-only generation for the same character.

- Show one fixed image for approval before you build a batch of variants from it.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Ask the user for the original reference image when no generation is close, since an edit from the true reference beats another text guess.

- Offer the locked reference and the working edit prompt for user-side generation when direct generation stays blocked.
