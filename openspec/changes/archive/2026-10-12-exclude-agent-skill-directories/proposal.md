# Proposal

## Why

The skills update workflow stages repository-wide changes, which can include generated content in `.claude` and `.agents`. These agent-specific directories should not be included in automated skills-update pull requests, and their checked-in copies should be removed.

## What Changes

- Exclude `.claude` and `.agents` from the skills-update pull request.
- Delete the `.claude` and `.agents` directories.

## Capabilities

### New Capabilities

None.

### Modified Capabilities

None. This is a repository workflow and content cleanup change, with no spec-level behavior changes.

## Impact

- `.github/workflows/skills-updates.yaml` pull request path selection.
- Removal of `.claude/` and `.agents/`.
