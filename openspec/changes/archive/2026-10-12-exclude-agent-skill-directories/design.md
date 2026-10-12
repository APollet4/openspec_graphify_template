# Design

## Context

The workflow's pull-request action stages `.` and excludes `.github/workflows`, so other generated paths are eligible for inclusion. The `.claude` and `.agents` trees currently contain skill copies. See proposal.md for motivation.

## Goals / Non-Goals

**Goals:**
- Prevent both directories from entering skills-update pull requests, including if they are regenerated.
- Remove their currently checked-in contents.

**Non-Goals:**
- Change which skills are installed in other project locations.
- Change OpenSpec update behavior or workflow triggers.

## Decisions

- Add explicit Git exclude pathspecs for `.claude` and `.agents` to the pull-request action's `add-paths`, following the existing `.github/workflows` exclusion pattern. This preserves the broad staging behavior for other generated files while protecting these paths; narrowing the staging allowlist could unintentionally omit unrelated updates.
- Remove both directories from the repository. The exclusions remain necessary so later workflow runs do not reintroduce regenerated copies.

## Risks / Trade-offs

- Updates under these directories will not be proposed by this automation → Other intended skill update paths remain staged as before.

## Migration Plan

Delete the two directories and add their exclusions in the same change. To roll back, restore the directories and remove the corresponding exclusions.
