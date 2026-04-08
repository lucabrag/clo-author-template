# CLAUDE.MD -- Empirical Social Science Research with Claude Code

**Project:** [YOUR PROJECT NAME]
**Institution:** [YOUR INSTITUTION]
**Field:** [YOUR FIELD — e.g., Labor Economics, Development, IO, Political Economy]
**Branch:** main

---

## Core Principles

- **Plan first** -- enter plan mode before non-trivial tasks; save plans to `quality_reports/plans/`
- **Verify after** -- compile and confirm output at the end of every task
- **Single source of truth** -- Paper `paper/main.tex` is authoritative; talks and supplements derive from it
- **Quality gates** -- weighted aggregate score; nothing ships below 80/100; see `quality.md`
- **Worker-critic pairs** -- every creator has a paired critic; critics never edit files
- **Auto-memory** -- corrections and preferences are saved automatically via Claude Code's built-in memory system

---

## Folder Structure

```
[YOUR-PROJECT]/
├── CLAUDE.MD                    # This file
├── .claude/                     # Rules, skills, agents, hooks
├── Bibliography_base.bib        # Centralized bibliography
├── paper/                       # Main LaTeX manuscript (source of truth)
│   ├── main.tex                 # Primary paper file
│   ├── sections/                # Section-level .tex files
│   ├── figures/                 # Generated figures (.pdf, .png)
│   ├── tables/                  # Generated tables (.tex)
│   ├── talks/                   # Beamer presentations
│   ├── preambles/               # LaTeX headers / .bst files
│   ├── supplementary/           # Online appendix and supplements
│   └── replication/             # Replication package for deposit
├── data/                        # Project data
│   ├── raw/                     # Original data (never modify)
│   └── cleaned/                 # Processed datasets ready for analysis
├── scripts/                     # Analysis code
│   ├── R/                       # R scripts
│   ├── stata/                   # Stata .do files
│   └── python/                  # Python scripts
├── quality_reports/             # Plans, session logs, reviews, scores
├── explorations/                # Research sandbox (see rules)
├── templates/                   # Session log, quality report templates
└── master_supporting_docs/      # Reference papers, survey instruments
```

---

## Commands

```bash
# Paper compilation (3-pass, XeLaTeX only)
cd paper && TEXINPUTS=preambles:$TEXINPUTS xelatex -interaction=nonstopmode main.tex
BIBINPUTS=..:$BIBINPUTS bibtex main
TEXINPUTS=preambles:$TEXINPUTS xelatex -interaction=nonstopmode main.tex
TEXINPUTS=preambles:$TEXINPUTS xelatex -interaction=nonstopmode main.tex

# Talk compilation (adjust filename)
# cd paper/talks && TEXINPUTS=../preambles:$TEXINPUTS xelatex -interaction=nonstopmode [YOUR_TALK].tex
```

---

## Quality Thresholds

| Score | Gate | Applies To |
|-------|------|------------|
| 80 | Commit | Weighted aggregate (blocking) |
| 90 | PR | Weighted aggregate (blocking) |
| 95 | Submission | Aggregate + all components >= 80 |
| -- | Advisory | Talks (reported, non-blocking) |

See `quality.md` for weighted aggregation formula.

---

## Skills Quick Reference

| Command | What It Does |
|---------|-------------|
| `/new-project [topic]` | Full pipeline: idea to paper (orchestrated) |
| `/discover [mode] [topic]` | Discovery: interview, literature, data, ideation |
| `/strategize [question]` | Identification strategy or pre-analysis plan |
| `/analyze [dataset]` | End-to-end data analysis |
| `/write [section]` | Draft paper sections + humanizer pass |
| `/review [file/--flag]` | Quality reviews (routes by target: paper, code, peer) |
| `/revise [report]` | R&R cycle: classify + route referee comments |
| `/talk [mode] [format]` | Create, audit, or compile Beamer presentations |
| `/submit [mode]` | Journal targeting, package, audit, final gate |
| `/tools [subcommand]` | Utilities: commit, compile, validate-bib, journal, etc. |

---

## Output Organization

Output organization: by-purpose

---

## Analysis Languages

- **Primary:** [YOUR PRIMARY LANGUAGE — e.g., R, Stata, Python, Julia]
- **Secondary:** [YOUR SECONDARY LANGUAGE, if any]

---

## Current Project State

| Component | File | Status | Description |
|-----------|------|--------|-------------|
| Paper | `paper/main.tex` | [not started / draft / advanced draft / complete] | [Brief description] |
| Data | `data/raw/` | [not started / in progress / complete] | [Datasets used] |
| Analysis | `scripts/` | [not started / in progress / complete] | [Analysis description] |
| Replication | `paper/replication/` | [not started / in progress / complete] | [Replication status] |
| Talk | `paper/talks/` | [not started / in progress / complete] | [Talk description] |
