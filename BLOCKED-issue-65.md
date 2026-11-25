# BLOCKED: issue #65

## Kind: design

Waits on a person: a maintainer has held the two chores #65 still asks for.

## What I was doing

Checking what is left of #65 after #66 (merged) deleted `chores.dependencies` from
`.claude/agent-fleet/agent-fleet.json`. Left: `security-audit` and `dependabot-cant-fix`,
both `off: true` in that file. `secret-scan` stays off by the issue's own terms.

## What rules out a change

A maintainer (e-gineer) commented on #65 after #66 merged: the issue stays open and held;
the security audit stays off until it can file findings in this public repo without spelling
out how to use them; "Dependabot can't fix" waits with it. That is a decision kept for a
person, and the filing behaviour it waits on is the fleet engine's, not this repo's settings.
Removing the two `off` entries now would go against that comment.

## Next step

When the engine can file audit findings in a public repo without exploit detail, a person
re-arms this issue. The fix is then to delete `off` from `security-audit` and
`dependabot-cant-fix` (and the entries, once empty) in the settings file.

Research done: read #65 and its comments, #66 and the settings file on main.
