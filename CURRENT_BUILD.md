# Current Build

STATUS: TEMPLATE

PROJECT: <project name>
BRANCH: <branch name>
STARTED: <YYYY-MM-DD>
OWNER: Lokivelli

## Exact target

<Describe the one build target for this branch.>

## Authoritative files inside this branch

- `build/`
- <add exact paths if only some files are authoritative>

## Required references

- `refs/`

## Temporary staging

- `staging/`

## Do not change

- <frozen behavior, UI, interfaces, contracts, or lineage that must be preserved>

## Known broken / unfinished

- <known defects or incomplete mechanisms>

## Acceptance gate

- <what must be true before this build is considered finished>

## Status meanings

- `TEMPLATE` — reusable branch skeleton only.
- `ACTIVE` — current public working handoff.
- `AUDIT` — implementation is frozen for verification.
- `DONE` — accepted work has been promoted out; branch may be deleted.

Nothing here becomes canonical until explicitly audited and promoted to its real project/master location.
