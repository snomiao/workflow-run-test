# Report

## Scope

- Added minimal `workflow_run` experiment with `test-a` and `test-b` workflows.
- Added note describing options and decision in `docs/workflow-run-test.md`.
- Added `.gitignore` entry for `TODO.md` and created a local `TODO.md` scratch file.
- Created and checked out `branch-b`.

## GitHub Actions (gh CLI)

- Pushed `main` and `branch-b` and triggered `test-b` via `gh workflow run`.
- `test-b` (push) log confirms checkout on `branch-b`:
  - `ref=refs/heads/branch-b`
  - `## branch-b...origin/branch-b`
- `test-a` (workflow_run) log shows default checkout on `main`, even though head branch is `branch-b`:
  - `ref=refs/heads/main`
  - `head_branch=branch-b`
  - `## main...origin/main`

## Files

- `.github/workflows/test-a.yml`
- `.github/workflows/test-b.yml`
- `docs/workflow-run-test.md`
- `.gitignore`
- `TODO.md` (ignored)
