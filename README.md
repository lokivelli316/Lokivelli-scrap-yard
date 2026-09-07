# Lokivelli Scrap Yard

Temporary public build staging for Custom GPTs, external builders, audits, and short-lived handoffs.

## What this repo is

This repository is a **public working window**, not a vault and not a canonical archive.

- `main` stays small and permanent.
- Active work goes on a disposable build branch.
- A build branch contains only the files needed for the current job.
- Every deliberate/named build version must be copied to the private `Lokivelli-garage` before the public branch is purged.
- The next job starts from a fresh build branch.

## Authority rule

**Nothing in this repository is canonical merely because it is here.**

Canonical masters remain in their actual project repository, private/local storage, Drive, or other designated master location. Material from this repo becomes authoritative only after it is audited and deliberately promoted.

## Public exposure rule

Everything committed here must be treated as permanently public, even if its branch is later deleted. Do not commit:

- passwords, API keys, tokens, credentials, or private keys;
- private master material that must remain private;
- personal or sensitive data;
- secrets embedded in config files, logs, exports, environment files, or archives.

Branch deletion is cleanup, **not retroactive privacy**.

## Garage-before-purge rule

A public build branch must not be deleted until its deliberate/named build version has completed the following transfer gate:

1. Freeze the current named build version in the Scrap Yard.
2. Copy/clone that version into the private `lokivelli316/Lokivelli-garage`.
3. Verify the Garage copy contains the expected files and entry points.
4. Record the source branch, source commit/SHA, version identifier, Garage destination, and verification result.
5. Mark the Garage intake as accepted only after verification passes.
6. Only then may the corresponding public Scrap Yard branch be purged.

**No verified Garage copy + no receipt = no purge.**

For this rule, a "version" means a deliberate build snapshot such as `v0.3.0`, `RC2`, `ticker-v4`, or another explicitly named handoff state. It does **not** mean every autosave or tiny intermediate commit.

If a build contains very large binary assets, the Garage receipt may point to the private canonical asset location plus hashes instead of duplicating unchanged binaries into every version. The public build slice still must remain recoverable from the Garage record.

## Build-branch layout

Each disposable build branch should use this small structure:

```text
CURRENT_BUILD.md
HANDOFF.md
build/
refs/
staging/
```

### `CURRENT_BUILD.md`
The machine-readable/human-readable front door: project name, exact target, branch status, authoritative files inside the branch, and what must not be changed.

### `HANDOFF.md`
Instructions for the GPT/builder: objective, constraints, expected output, acceptance checks, and return instructions.

### `build/`
The actual current working build or source slice.

### `refs/`
Only the references required to understand or modify the current build.

### `staging/`
Optional short-lived pieces for a larger build. Do not use it as an archive.

## Recommended branch names

```text
build-gate-closing
build-friday-runtime
build-pdf-editor
build-physics-site
```

Use one active target per branch. Do not pile unrelated jobs into the same branch.

## Custom GPT rule

When handing work to a Custom GPT or other builder, provide the **specific build-branch URL**, not merely the repository root, and tell it:

> Treat this branch as the complete public working handoff for this job. Follow `CURRENT_BUILD.md` and `HANDOFF.md`. Do not infer canonical status from any other branch or external version.

## Lifecycle

```text
real master / private source
        ↓
select + sanitize current working slice
        ↓
disposable public build branch
        ↓
GPT / builder / auditor
        ↓
freeze named version
        ↓
copy/clone to private Lokivelli-garage
        ↓
verify + receipt
        ↓
promote accepted work as appropriate
        ↓
purge disposable public branch
        ↓
start next fresh branch
```

**Scrap Yard means temporary. The good parts leave. The yard gets cleared.**
