# Workflow_run checkout behavior test

Goal: validate whether a workflow triggered by `workflow_run` checks out the default branch or the triggering branch when `actions/checkout` is used without `ref`.

## Options

Option A: Minimal `workflow_run` + default checkout (chosen)

Pros:
- Matches real-world default behavior with no extra configuration.
- Directly answers the disputed point with minimal variables.
- Low maintenance and easy to delete after conclusion.

Cons:
- Might require reading logs to interpret branch state.
- Does not attempt to “fix” behavior if default is undesired.

Best when:
- We want ground truth for default checkout behavior.

Option B: Explicit checkout of triggering branch

Pros:
- Forces checkout to match the originating workflow run.
- Useful if the desired behavior is to test PR branch contents.

Cons:
- Does not validate default behavior; it assumes a fix.
- Adds extra logic that can mask the behavior in question.

Best when:
- We already concluded default checkout is wrong and need the workaround.

## Decision

Choose Option A first. It is the minimal experiment that directly answers whether default checkout follows the default branch or the triggering branch. Option B can be added only if Option A shows default checkout is not acceptable.

## Minimal experiment outline

- `test-b` runs on `branch-b` push or manual dispatch.
- `test-a` is triggered via `workflow_run` from `test-b`.
- `test-a` uses default `actions/checkout` and prints ref, head branch, git status, branch name, and repo listing.
