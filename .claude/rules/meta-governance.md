# Meta-Governance

**This repository is BOTH a working project AND (optionally) a template.**

## Decision Framework

When creating or modifying content, ask: **"Is this generic or specific?"**

**Generic (commit to repo):** Workflow patterns, design principles, templates, skill definitions, rules
**Specific (keep local or gitignore):** Machine-specific paths, tool versions, institutional requirements, API keys

## Memory: Two-Tier System

- **MEMORY.md** (committed): Generic learnings useful across projects and machines
- **`.claude/state/personal-memory.md`** (gitignored): Machine-specific and user-specific learnings

## Dogfooding

Follow the patterns you define:
- Plan-first for non-trivial tasks
- Spec-then-plan for ambiguous tasks
- Quality gates before commits
- Session logs for significant work
- Update documentation alongside implementation
