# Builder Handoff

## Objective

<What the GPT/builder is being asked to build, repair, audit, or wire up.>

## Working authority

For this job, use this branch only. Start with `CURRENT_BUILD.md`.

Do not assume files from `main`, old branches, other repositories, or remembered prior versions override this handoff unless this document explicitly says so.

## Inputs

- `build/` — current working source/build slice.
- `refs/` — references required for this job.
- `staging/` — optional temporary large-build pieces.

## Constraints

- Preserve working behavior unless the target explicitly requires changing it.
- Do not redesign or flatten deliberate structure merely to simplify implementation.
- Do not remove apparent redundancy without demonstrating that it is obsolete.
- Do not introduce credentials, secrets, private master material, or sensitive data into this public branch.
- Surface unresolved assumptions instead of silently inventing missing authority.

## Expected return

<Exact files, patch, branch, ZIP, report, or other return artifact expected from the builder.>

## Acceptance checks

1. <check>
2. <check>
3. <check>

## Completion rule

A builder result is not canonical merely because it works. It must be audited and deliberately promoted back to the real project/master location. After promotion, this disposable branch may be deleted.
