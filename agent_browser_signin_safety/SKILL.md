# Agent Browser Sign In Safety

## Stop at the first verification challenge

- Stop the sign in attempt when a code request, a confirm identity prompt, a captcha, or a policy gate appears.

- Run no second sign in attempt in the same run after that challenge appears.

- Treat a challenge that repeats after a code was accepted as a failed sign in, not as a reason to try another code.

- Refuse a Continue button on a policy gate that flags automated access, and hand the step to the user on their own device.

- Report the challenge once in plain words and name the exact step where work stopped.

## Do not browse personal Meta accounts from the agent browser

- Do not sign in to Facebook or Instagram in the agent browser on the user personal Meta account.

- Treat a signed in Meta browser session as a lock risk because the agent browser reaches Meta from a United States datacenter address while the user is in Pakistan, and Meta treated that mismatch as suspicious access on 2026-11-12 and locked both Facebook and Instagram.

- Use the Facebook connector for Facebook reads and for posts on a Page itself, using the Page publishing commands, instead of a browser task.

- Use the Instagram connector for Instagram reads, posts, reels and schedules, instead of a browser task.

- Do not use the Facebook connector to post a book in a group, because the connector group post goes out as the personal profile and not as the managed Page.

- Hand a Facebook group book post to the user on their own device, with the prepared text, image and verified Amazon link, and do not post it from the agent browser or through the connector.

- Keep the Page only rule for group book posts, and never post a group book post as the personal profile when the Page route is unavailable.

- Read a pasted Facebook link with the Facebook connector instead of opening it in the browser.

- Hand a Meta step to the user on their own device when neither connector can do it as the Page or as the right account, and do not work around the gap with a browser sign in.

- Do not use the social publishing website carve outs from the agent browser, including a Facebook site post for a Group post the connector does not list and an Instagram site delete for a post the connector cannot delete.

- Hand a step that only the Facebook site or the Instagram site can do to the user on their own device instead of signing in to do it.

- Stop every Facebook and Instagram browser and connector attempt at once when a Meta lock appears, and do not retry, reauthorize or sign in again in that run.

- Pause every affected Facebook and Instagram schedule without deleting it, keep each queued item in its place, and report the lock once with the one phone step that can restore access.

- Resume a paused Meta queue only after the user says the account is unlocked, and confirm the account is open before the next scheduled run touches it.

- Follow this section over a browser sign in step in any task skill for Meta, but do not let it override the Page only identity rule for group book posts.

## Keep verification inside one browser session

- Complete any verification only inside the browser session that requested it.

- Treat verification completed on a phone or on another device as unusable for the agent browser session.

- Reuse a saved session or a saved access token while it remains valid instead of starting a fresh authorization.

- Start no fresh authorization in the middle of a run when a saved token or session already exists.

- Do not chase a wiped session with repeated sign ins after an environment replacement, and report the wipe once and wait for a fresh signed in session.

## Let the user create new accounts

- Do not create a marketplace seller account or any other trust gated account from the agent browser.

- Ask the user to create the account on their own device and to confirm the account is live before any agent listing step.

- Do not run repeated sign ins, captchas, or device checks to force a new account through.

## Do not reuse a rejected vault credential across runs

- Treat a saved password that a sign in rejects once as stale for every service that shares that sign in.

- Make no further attempt with that stale credential in a later run until the user updates the saved copy.

- Present no password card for a service that has no separate password, such as a service that signs in only through Google.

- Check the service sign in model before you present any credential prompt, and name the Google sign in route instead when that is the only route.

- Treat a sign in the user completes on their own device as unusable for a scheduled browser run until that run session itself is signed in, and say so plainly instead of retrying the stale credential.

- Hold every blocked queue in place while the credential stays stale, and name the one update that unblocks it, such as an updated saved credential or a fresh signed in session for that run.

## Preserve the queue and report once

- Save any prepared payload, draft, or listing text before you stop, so the next run can resume without rebuilding it.

- Leave every queued item in place with its position and state untouched, and mark it blocked on sign in rather than failed for a logic reason.

- Report the block once per run and do not send a new status message for each retry you did not run.

- Offer the one manual step that unblocks the work, such as signing in on the user own device, and name the next scheduled run that will pick the queue up.

## Available connectors

- [Facebook](/opt/hatch/connectors/facebook_cli/CONNECTOR.md) for reading Facebook and for posting on a Page through the CLI instead of the browser, and not for posting a book in a group as the profile.

- [Instagram](/opt/hatch/connectors/instagram/CONNECTOR.md) for reading and publishing on Instagram through the CLI instead of the browser.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Use an API or connector route for the same task when one exists, since that route may stay signed in while browser sign in is blocked.

- Use the Facebook and Instagram CLIs for Meta reads and Page posts instead of a browser task, and hand a step to the user on their own device when the CLI cannot do it as the Page.

- Do the parts of the task that need no sign in first, such as preparing payloads and checking queue state, so the work is ready when sign in returns.
