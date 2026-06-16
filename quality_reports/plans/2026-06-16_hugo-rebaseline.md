# Plan — Re-baseline onto Hugo's upstream template

**Status:** DRAFT (awaiting approval)
**Date:** 2026-06-16
**Author:** Claude (Opus 4.8) with Luca
**Goal:** Bring this repo up to date with `hugosantanna/clo-author` (current `main`, commit `d36c408`, past `v4.2.0`) while preserving all of Luca's customizations.

---

## Background

- Local repo (`lucabrag/clo-author-template`) is an **unrelated-history** copy of Hugo's template, frozen at ≈ **v3.1.1**.
- Hugo's `main` is far ahead: **181 files** we lack, **43** updated since our snapshot.
- Of the 43 "modified" files, only a handful were genuinely edited by Luca; the rest differ only because our snapshot sits a few commits off the v3.1.1 tag → safe to take Hugo's versions.

## What must be preserved (Luca's work — none of it exists in Hugo)

**Committed:**
- `master_supporting_docs/voice/` — 9 voice PDFs + README (voice corpus for prose-editor)
- `README.md` → "Overleaf Integration" section + quick-start tweaks (Hugo's README has no Overleaf content)
- `CLAUDE.md` → one-line note ("syncs with Overleaf")
- `.gitignore` → policy: ignore build PDFs but track `master_supporting_docs/**`

**Untracked (newest, not yet in git anywhere):**
- `.claude/agents/prose-editor.md`, `.claude/references/writing-voice.md`, `.claude/skills/edit/`
- `.agents/skills/` — Codex skills mirror (incl. `edit`)
- `.codex/` — Codex port (agents `*.toml`, hooks, hooks.json) — no secrets found

## History strategy

Approach **A**: one re-baseline commit on top of current history. **No force-push** needed; `origin` stays a simple fast-forward. Fully reversible via a backup branch. (Alternative B — reset onto Hugo's history for frictionless future pulls — rejected: requires force-push / history rewrite.)

The `hugo` remote stays configured so future updates repeat this overlay.

---

## Steps

### Phase 0 — Safety
1. Commit untracked custom work first so it is tracked and captured:
   `git add .agents .codex .claude/agents/prose-editor.md .claude/references/writing-voice.md .claude/skills/edit && git commit -m "Save custom work (Codex port, prose-editor, writing-voice, edit skill) before re-baseline"`
2. Create backup branch: `git branch backup/pre-hugo-rebaseline-2026-06-16`

### Phase 1 — Overlay Hugo's tree
3. `git checkout hugo/main -- .` — brings all 181 new files + Hugo's versions of the 43 updated files. Does NOT delete untracked or non-Hugo files, so voice PDFs and the custom work above are retained automatically.

### Phase 2 — Re-apply Luca's intentional customizations
4. `README.md` — re-insert the "Overleaf Integration" section + the two quick-start line tweaks into Hugo's newer README.
5. `.gitignore` — adopt Hugo's, then re-apply Luca's PDF policy (uncomment `*.pdf`, add `!master_supporting_docs/**`).
6. `CLAUDE.md` — adopt Hugo's newer template; add back the "syncs with Overleaf" one-liner on the `paper/` line.

### Phase 3 — Verify
7. Confirm all custom artifacts present: `master_supporting_docs/voice/`, `.claude/skills/edit/`, `.claude/agents/prose-editor.md`, `.claude/references/writing-voice.md`, `.agents/`, `.codex/`.
8. Confirm Hugo's additions present: new skills (`careful`, `checkpoint`, `dashboard`, `freeze`), new agents (`theorist*`, `guide-writer`), hooks, references, rules.
9. `git diff --name-only main hugo/main` should now show only Luca's intentional deltas (voice corpus, README Overleaf, .gitignore policy, CLAUDE one-liner, .agents/.codex).
10. No LaTeX compile needed — `paper/` is an empty template (no `main.tex` yet).

### Phase 4 — Commit & (optional) push
11. `git add -A && git commit` — message documents source commit `hugo/main@d36c408` and preserved customizations.
12. Ask Luca before pushing to `origin`.

---

## Decisions (defaults; Luca can override at approval)
- **.agents/.codex tracking:** commit to repo (no secrets; backs up the Codex port). Alternative: gitignore instead.
- **docs/ + guide/ website (~80 files):** include for fidelity. Alternative: drop if Luca doesn't want the rendered guide site.
- **Push to origin:** ask after commit.

## Rollback
`git reset --hard backup/pre-hugo-rebaseline-2026-06-16` restores the exact pre-operation state.
