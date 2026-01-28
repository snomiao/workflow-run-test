# Report

## Scope

- Added minimal `workflow_run` experiment with `test-a` and `test-b` workflows.
- Added note describing options and decision in `docs/workflow-run-test.md`.
- Added `.gitignore` entry for `TODO.md` and created a local `TODO.md` scratch file.
- Created and checked out `branch-b`.

## GitHub Actions (gh CLI)

- Pushed `main` and `branch-b`.
- Latest `test-b` run log confirms checkout on `branch-b`:
  - `ref=refs/heads/branch-b`
  - `## branch-b...origin/branch-b`
- `gh run list --workflow test-a` reported no runs yet (not found at time of check).

## Files

- `.github/workflows/test-a.yml`
- `.github/workflows/test-b.yml`
- `docs/workflow-run-test.md`
- `.gitignore`
- `TODO.md` (ignored)
