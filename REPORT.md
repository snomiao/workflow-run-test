# Report

## Scope

- Added minimal `workflow_run` experiment with `test-a` and `test-b` workflows.
- Added note describing options and decision in `docs/workflow-run-test.md`.
- Added `.gitignore` entry for `TODO.md` and created a local `TODO.md` scratch file.
- Created and checked out `branch-b`.

## GitHub Actions (gh CLI)

- `gh run list --limit 5` returned no output in this environment.
- Likely causes: no recent runs on this repo, not authenticated, or runs are not accessible locally.
- Once `branch-b` is pushed, `test-b` should run and then trigger `test-a` for a concrete result.

## Files

- `.github/workflows/test-a.yml`
- `.github/workflows/test-b.yml`
- `docs/workflow-run-test.md`
- `.gitignore`
- `TODO.md` (ignored)
