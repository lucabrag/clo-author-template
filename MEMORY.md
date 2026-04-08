# Project Memory

Corrections and learned facts that persist across sessions.
When a mistake is corrected, append a `[LEARN:category]` entry below.

---

<!-- Append new entries below. Most recent at bottom. -->

## Workflow Patterns

[LEARN:workflow] Requirements specification phase catches ambiguity before planning. Reduces rework 30-50%. Use spec-then-plan for complex/ambiguous tasks (>1 hour or >3 files).

[LEARN:workflow] Spec-then-plan protocol: AskUserQuestion (3-5 questions), create spec with MUST/SHOULD/MAY requirements, declare clarity status (CLEAR/ASSUMED/BLOCKED), get approval, then draft plan.

[LEARN:workflow] Context survival before compression: (1) Update MEMORY.md with [LEARN] entries, (2) Ensure session log current, (3) Active plan saved to disk, (4) Open questions documented.

[LEARN:workflow] Plans, specs, and session logs must live on disk (not just in conversation) to survive compression and session boundaries.

## Documentation Standards

[LEARN:documentation] When adding new features, update documentation immediately to prevent drift.

[LEARN:documentation] Documentation should be generic (framework-oriented) not prescriptive. Provide templates with examples, let users customize.

## Design Philosophy

[LEARN:design] Framework-oriented > Prescriptive rules. Provide templates users customize to their domain.

[LEARN:design] Generic means working for any academic workflow: pure LaTeX, pure R, Python/Jupyter, any domain.

## File Organization

[LEARN:files] Specifications go in `quality_reports/specs/YYYY-MM-DD_description.md`.

[LEARN:files] Templates belong in `templates/` directory with descriptive names.

## Constitutional Governance

[LEARN:governance] Constitutional articles distinguish immutable principles (non-negotiable) from flexible user preferences. Keep to 3-7 articles max.

[LEARN:governance] Amendment process: distinguish "amending Article X (permanent)" from "overriding for this task (one-time exception)".
