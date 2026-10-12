# Tasks

## 1. Exclude agent-specific directories from the update PR

- [x] 1.1 Add `.claude` and `.agents` exclusions to `.github/workflows/skills-updates.yaml` and verify both pathspecs are present in `add-paths`.

## 2. Remove checked-in agent-specific copies

- [x] 2.1 Delete `.claude/` and `.agents/` and verify neither directory remains in the repository.

## 3. Validate the change

- [ ] 3.1 Run `openspec validate exclude-agent-skill-directories --json` and confirm the change validates successfully.
