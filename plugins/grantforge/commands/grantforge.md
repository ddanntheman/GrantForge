---
description: Run the full GrantForge lifecycle for a grant opportunity
argument-hint: [grant announcement, URL, or "discover"]
---

Orchestrate the full GrantForge workflow. `$ARGUMENTS` may contain a grant
announcement (pasted text or reference to an uploaded file), a URL to a
funding opportunity, the word "discover", or nothing.

1. Check whether a `.grantforge/` profile exists in the connected folder.
   If not, run the grant-setup skill first — nothing else works without
   the org profile.
2. If `$ARGUMENTS` is empty, read `.grantforge/tracker.md` and ask the user
   whether to resume an in-flight application (show the pipeline with
   deadlines) or start something new (discover or intake).
3. If the user wants discovery (or `$ARGUMENTS` is "discover"), run the
   grant-discover skill and stop after presenting ranked opportunities;
   resume from step 4 for any opportunity the user selects.
4. Run grant-intake on the announcement. Present the requirements matrix
   and the go/no-go recommendation. Stop for the user's decision.
5. On "go": run grant-research (both evidence base and funder
   intelligence), then grant-draft section by section with user feedback
   between sections, and grant-budget when the project design is stable
   enough to cost.
6. When all sections are drafted, run grant-review. Present blockers and
   the mock score. Loop revisions through grant-draft until blockers are
   clear and the user is satisfied.
7. Finalize: produce the deliverables the requirements matrix calls for
   (Word documents, portal-ready text files, budget workbook, compliance
   matrix), update the tracker, and remind the user of the deadline and
   submission mechanism.

Keep the user informed of which phase is active. Update
`.grantforge/tracker.md` at every status change. Apply the house-style
skill to all prose.
