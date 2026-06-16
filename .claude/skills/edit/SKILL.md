---
name: edit
description: Edit prose in Luca's voice. Channels Chaubey/Minto top-down writing and the economics intro structure (RAP, "In this paper" paragraph, mini guided tour, contribution, roadmap). Supports suggest/direct modes, long-target triage, and LaTeX-safe direct edits.
---

# /edit — Prose editing in Luca's voice

Use `/edit` to run the **prose-editor** agent over a passage, section, or whole file. The agent reads `.claude/references/writing-voice.md`, samples exemplar passages from `master_supporting_docs/voice/` when useful, and either proposes edits (Suggest mode) or applies them directly (Direct mode).

## Usage

```
/edit <target> [--mode suggest|direct] [--focus <focus>] [--exemplar <paper>] [--full]
```

### Arguments

- **`<target>`** — what to edit. One of:
  - A file path: `/edit paper_new.tex`
  - A file + section label: `/edit paper_new.tex#sec:instrumentalvalue`
  - A line range: `/edit paper_new.tex:256-340`
  - A short label of a recently drafted passage in this conversation (e.g., `/edit the intro I just wrote`).

- **`--mode suggest`** *(default)* — agent returns an edit report; no file changes.
- **`--mode direct`** — agent applies edits via `Edit` and returns a summary of changes + items still flagged for the author.
- **`--direct`** — legacy shorthand for `--mode direct`; normalize it before dispatch.

- **`--focus <focus>`** *(optional)* — narrows the pass to one of:
  - `intro` — only the introduction, with the 6-component check (positioning → "In this paper" → guided tour → policy → contribution → roadmap).
  - `topic-sentences` — only the first sentence of each paragraph; the MRW test.
  - `voice` — sentence-level voice only (filler, nominalizations, hedging).
  - `rap` — only the RAP visibility check (returns the paper's R, A, P as currently legible from the prose).
  - `length` — only paragraph length / split-or-merge calls.
  - If omitted, the agent runs the full checklist.

- **`--exemplar <paper>`** *(optional)* — name a specific exemplar paper from `master_supporting_docs/voice/` to anchor the voice. E.g., `--exemplar news_slant`. If omitted, the agent picks one when needed.

- **`--full`** *(optional)* — allow exhaustive paragraph-by-paragraph treatment of a long target. Without this flag, whole files, introductions, and targets longer than 12 prose paragraphs receive a triage report rather than a sprawling edit report.

### Examples

```
/edit paper_new.tex --focus intro
```
Run a full intro pass on the main paper in suggestion mode.

```
/edit paper_new.tex:256-340 --mode direct --focus topic-sentences
```
Rewrite the topic sentences of paragraphs in lines 256–340 directly; report what was changed.

```
/edit paper_new.tex --focus rap
```
Tell me what R, A, P are currently legible from the prose. No edits.

```
/edit the contribution paragraph I just drafted --mode suggest
```
Run a one-paragraph edit on a passage in conversation context.

## How the skill runs

1. **Resolve target.** Identify the file and lines to edit. If the target is in conversation context (a recently drafted passage), capture it verbatim.
2. **Spawn the prose-editor agent.** Pass: target, mode, focus, exemplar selection. Tell the agent to read `writing-voice.md` first, then act.
3. **Respect long-target triage.** If the target is a whole file, an introduction, or more than 12 prose paragraphs and `--full` is absent, ask the agent for triage: RAP check, 5-8 highest-value issues, at most three representative rewrites, and a suggested next pass.
4. **Preserve LaTeX boundaries.** Tell the agent not to edit inside tables, figures, equations, macro definitions, bibliography declarations, citation keys, labels, refs, or generated-value commands. LaTeX commands and their arguments should remain byte-for-byte identical unless explicitly in scope.
5. **Preserve project terms.** Tell the agent to keep core terms such as "cross-partisan contact," "same-party conversations," "information aggregation," "affective polarization," "hedonic value," and "selection against cross-partisan contact" unless the user explicitly asks for terminology changes.
6. **Return the report.** In Suggest mode, surface the agent's edit or triage report verbatim. In Direct mode, surface the change summary and confirm the file was modified.
7. **Verify direct edits.** Direct mode requires a diff check confirming that citations, labels, refs, numbers, macros, and protected LaTeX regions did not change unless requested. If `paper_new.tex` was edited and shell access is available, compile the paper; report clearly if compilation was skipped or failed.
8. **Offer a follow-up.** After Suggest mode, ask whether to re-run in Direct mode applying all/some/none of the proposed edits. After Direct mode, ask whether to run a second pass on the items flagged for author attention.

## What this skill does NOT do

- It does **not** invent or strengthen claims. The editor flags missing support; it does not paper over gaps.
- It does **not** edit tables, figures, regression specifications, or identification strategies. Use `/review` for substantive critique, `/strategize` for identification, `/analyze` for code.
- It does **not** change numbers, p-values, or citations.
- It does **not** edit protected LaTeX regions: tables, figures, equations, macro definitions, bibliography declarations, labels, refs, citation keys, or generated-value commands.
- It does **not** rewrite passages in someone else's voice. The exemplars are Luca's prior papers; the goal is consistency with that voice, not a generic academic style.

## When to use this skill vs. others

- **`/edit`** — sharpen prose that already exists. Topic sentences, paragraph structure, voice.
- **`/write`** — draft new prose from scratch (then run `/edit` over the draft).
- **`/review`** — get a critical read on substance, not style.
- **`/revise`** — respond to referee comments in an R&R cycle.

A typical sequence: `/write` to draft → `/edit --mode suggest` to see proposed sharpenings → review the suggestions → `/edit --mode direct` to apply the ones you like → final read.
