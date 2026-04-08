# clo-author-template

A Claude Code workflow template for academic research papers. Provides a complete AI-assisted research pipeline from idea to submission, with 18 specialized agents, 10 unified skills, simulated peer review, and R&R cycle management.

## Quick Start

1. **Use this template** (or clone/fork) to create a new repository for your paper
2. Fill in `CLAUDE.md` — project name, institution, field, analysis languages
3. Fill in `.claude/references/domain-profile.md` — your field's conventions, data sources, seminal references
4. (Optional) Connect to **Overleaf** via GitHub sync — see below
5. Start working: `claude` in the project directory

## What's Included

### 10 Unified Skills (Commands)

| Command | What It Does |
|---------|-------------|
| `/new-project [topic]` | Full pipeline: idea to paper (orchestrated) |
| `/discover [interview\|lit\|data]` | Research spec, literature review, or data discovery |
| `/strategize [question]` | Identification strategy + adversarial review |
| `/analyze [dataset]` | End-to-end analysis: scripts, output, code review |
| `/write [section]` | Draft paper sections + humanizer pass |
| `/review [file]` | Multi-agent quality review + simulated peer review |
| `/revise [report]` | Route referee comments, draft response letter |
| `/talk [format]` | Beamer presentation from paper (4 formats) |
| `/submit [journal]` | Journal targeting, replication package, final audit |
| `/tools [subcommand]` | commit, compile, validate-bib, journal, context |

### 18 Research Agents

| Agent | Role |
|-------|------|
| **orchestrator** | Pipeline manager, dependency graph, escalation routing |
| **editor** | Journal editor: desk review, referee selection, editorial decisions |
| **domain-referee** | Blind reviewer (substance, literature, contribution) |
| **methods-referee** | Blind reviewer (identification, estimation, inference) |
| **librarian** + critic | Literature search and synthesis |
| **explorer** + critic | Data discovery and feasibility assessment |
| **data-engineer** | Data cleaning pipeline |
| **strategist** + critic | Identification strategy design |
| **coder** + critic | Analysis scripts (R/Stata/Python/Julia) |
| **writer** + critic | Paper drafting and polishing |
| **storyteller** + critic | Beamer talk creation |
| **verifier** | Compilation, execution, replication checks |

### 30+ Journal Profiles

Pre-configured referee calibration for journals across Economics (Top-5, AEJ, field), Finance, Accounting, Marketing, and Management. Each profile includes focus, bar, referee adjustments, typical concerns, and referee pool weights.

### Quality Pipeline

- Weighted scoring: Literature 10% + Data 10% + Identification 25% + Code 15% + Paper 25% + Polish 10% + Replication 5%
- Gates: 80 (commit), 90 (PR), 95 (submission)
- Worker-critic pairing with three-strikes escalation
- Context survival hooks (pre-compact state capture, post-compact restore)

## Customization Checklist

After creating your repo from this template:

- [ ] `CLAUDE.md` — Fill in project name, institution, field, languages, folder structure
- [ ] `.claude/references/domain-profile.md` — Your field's journals, data, notation, seminal papers
- [ ] `.claude/settings.json` — Add language-specific permissions (e.g., `Bash(stata *)` for Stata)
- [ ] `Bibliography_base.bib` — Seed with your initial references
- [ ] `paper/main.tex` — Your paper's LaTeX source (optional — `/new-project` and `/write` create this for you)
- [ ] `paper/preambles/` — Your .bst file and LaTeX headers (optional — needed only for compilation)

## Architecture

```
User provides task
    |
    v
Orchestrator checks dependency graph
    |
    v
Dispatches worker-critic pair(s) — parallel when independent
    |
    v
Critic scores output (0-100)
    |
    +--> Score >= threshold? --> Advance to next phase
    |
    +--> Score < threshold? --> Worker revises (max 3 rounds)
    |
    +--> 3 strikes? --> Escalate per routing table
```

## Overleaf Integration

This template works seamlessly with Overleaf's GitHub sync:

1. Create your repo from this template on GitHub
2. In Overleaf: **New Project → Import from GitHub** → select your repo
3. Overleaf syncs the `paper/` directory (and everything else) bidirectionally
4. Edit in Overleaf for real-time collaboration; use Claude Code for AI-assisted drafting, analysis, and review

**Workflow:** GitHub is the backbone. Overleaf pulls/pushes via GitHub sync. Claude Code reads/writes the same files locally. Both always stay in sync through git.

## Two-Template System

This template is for **research papers**. For **teaching/lecture slides** (Beamer + Quarto), see [claude-code-my-workflow](https://github.com/pedrohcgs/claude-code-my-workflow).

| Use Case | Template |
|----------|----------|
| Research paper | **This repo** (clo-author-template) |
| Course lectures | claude-code-my-workflow |
| Paper talks | **This repo** (via `/talk` skill — Beamer talks from paper) |

## Requirements

- [Claude Code](https://claude.ai/claude-code) CLI
- LaTeX distribution (TeX Live recommended) with XeLaTeX
- Your analysis language(s): R, Stata, Python, and/or Julia

## License

MIT
