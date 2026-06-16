# Writing Voice — Luca Braghieri

This is the canonical style guide for editing economics papers in Luca's voice. Any agent editing prose in this repo MUST read this file in full before making changes.

The guide has four parts:
1. **RAP** — the spine of every paper.
2. **Top-down writing** — the principle that governs every paragraph.
3. **Introduction structure** — the specific 5-6 page form that economics introductions take.
4. **Voice** — sentence-level style: classic, accessible, no padding.

When editing, channel Varanya Chaubey's *Little Book on Research Writing* and Barbara Minto's *Pyramid Principle*. When in doubt about sentence-level style, channel Bertrand Russell and Thomas & Turner's *Clear and Simple as the Truth*.

---

## 1. RAP — Research question, Answer, Positioning

Every paper has a **RAP** at its core. The spine. You should be able to state each in one sentence.

- **R (Research question):** the version of the research question the *reader* would naturally articulate. Phrased to make the reader recognize the paper as relevant to their interests. Not the writer's question — the reader's.
- **A (Answer):** the higher-level claim that summarizes the main findings. The task is to extract the *main message* from detailed findings, not to list them.
- **P (Positioning):** the space in the literature that R and A occupy. P should idly *lead* readers to A: it makes space for R, R is answered by A.

RAP runs through a paper like its spine. Abstract, introduction, section takeaways, paragraph topic sentences — all should reflect the same RAP.

When editing: if a passage doesn't serve R, A, or P, ask whether it belongs at all.

---

## 2. Top-down writing

The default sentence and paragraph structure is **descending**: the punchline first, then the support.

### Why
Academic papers are dense. Knowing the punchline makes details easier to absorb. The pyramid principle (Minto): analytical writing is a logical dialog where the reader prefers to descend from high level to detail.

### The onion
A paper is an onion of nested top-down structures:
- **Abstract** — most compressed RAP.
- **Introduction topic sentences** — RAP visible if you read just the first sentence of each paragraph.
- **Introduction paragraphs** — elaborate the topic sentences.
- **Body sections** — elaborate the introduction's "guided tour."
- **Appendix** — details too tedious for the main text.

A reader at any level should be able to stop and walk away with a coherent understanding.

### Topic sentences
Every body paragraph (and every introduction paragraph after the first 3-4 — see §3) opens with a sentence that:
1. **Carries the main message** of the paragraph (an *idea*, not a detail).
2. **Links to the overall story** — usually by carrying forward a phrase or key term from the previous paragraph's first sentence. Linguistic links signal logical links.
3. **Provokes the follow-up question** that the rest of the paragraph answers.

A reader should be able to read only the first sentence of each paragraph and follow the argument. Mankiw, Romer & Weil's "A Contribution to the Empirics of Economic Growth" (QJE 1992) is the canonical example. The first sentences of its introduction paragraphs read:

> 1. *This paper takes Robert Solow seriously.*
> 2. *This paper argues that the predictions of the Solow model are, to a first approximation, consistent with the evidence.*
> 3. *Yet all is not right for the Solow model.*
> 4. *We therefore augment the Solow model by including accumulation of human as well as physical capital.*
> 5. *To test the augmented Solow model, we include a proxy for human-capital accumulation as an additional explanatory variable in our cross-country regressions.*
> 6. *After developing and testing the augmented Solow model, we examine an issue that has received much attention in recent years: the failure of countries to converge in per capita income.*
> 7. *Finally, we discuss the predictions of the Solow model for international variation in rates of return and for capital movements.*
> 8. *Overall, the findings reported in this paper cast doubt on the recent trend among economists to dismiss the Solow growth model in favor of endogenous-growth models that assume constant or increasing returns to scale in capital.*

You can follow the entire argument from these eight sentences alone. That is the standard.

### Burying the lead
The most common defect is **burying the lead**: the core sentence sits in the middle or end of the paragraph instead of at the top. This happens because writers think their way *toward* the main idea while drafting. Edit by promoting the buried sentence to the topic sentence and demoting the throat-clearing.

### Paragraph length
Paragraph length matters along two dimensions: idea density (sentences) and visual weight (lines on the page). Both are red flags when violated.

- **Sentences.** RAP paragraphs run **5–6 sentences**. If a paragraph is longer, an idea is probably buried inside that the reader will miss — split it.
- **Lines on the page.** The visual-weight budget is strict:
  - **≤ 8 lines** — the default. Most paragraphs in the paper sit here.
  - **9–10 lines** — a few paragraphs per paper, when the argument genuinely needs the room.
  - **11–12 lines** — very few. Reserve for passages where the structure of the argument itself demands the length.
  - **> 12 lines** — at most one paragraph in the entire paper. If you find yourself writing a second one, you are burying ideas — split.

Structure matters more than either measure, but both are useful red flags. A 7-sentence paragraph at 9 lines is fine; a 4-sentence paragraph at 14 lines (long sentences) is suspect.

### Consistent terminology
Do not use interchangeable terms for the same identity. If you call something "the treatment effect" in §3, do not call it "the impact" in §4 and "the causal estimate" in §5. Repetition is a feature, not a bug — it cues the reader to logical continuity.

### Grouping ideas (Minto's pyramid logic)
When a paragraph, section, or list pulls together multiple ideas, the grouping itself must follow rules.

- **MECE.** Sibling ideas at one level must be **M**utually **E**xclusive (no overlap) and **C**ollectively **E**xhaustive (no gaps). If two items in a list cover the same ground, merge them. If three reasons leave an obvious fourth unaddressed, surface it. The reader silently checks for overlaps and gaps; failing the test breaks trust.

- **Horizontal logic: deductive vs. inductive.** Sibling ideas relate to each other in one of two ways. *Deductive*: premise → premise → therefore conclusion (a chained argument). *Inductive*: a set of like things sharing a defining feature ("three reasons cross-partisan contact may fail to produce learning"). Mixing the two within one group leaves the reader unsure how the items connect — pick one mode per group.

- **Summary-statement discipline.** Any group of ideas you can only describe as "five things about X" is not yet a group. A real group is summarizable in one sentence that names the unifying claim. If you cannot write that sentence, the items don't belong together — find the actual structure or split. The summary sentence is also the natural topic sentence of the paragraph that introduces the group.

- **Vertical Q&A.** Each child idea answers a question implicitly raised by the parent. If a child does not answer the parent's "so what?" or "why?" or "how?", it doesn't belong there. This is the discipline behind the onion structure: every level descends to answer a question raised at the level above.

---

## 3. Introduction structure (economics)

Economics papers have a distinctive introduction: ~5–6 pages long, much more like an extended abstract than a one-page science-paper intro. It has six components in this order:

### Component A — Positioning paragraphs (2–3 paragraphs)
The first 2–3 paragraphs do three jobs:
1. **Hook** the reader's attention. Show the stakes are substantial, or pose a puzzle.
2. **Make space** for the paper by surfacing a gap in the literature or in our understanding.
3. **Funnel** the reader toward asking exactly one question — the paper's research question.

If the paper has theory, the positioning may include a motivating example.

**Stylistic exception for §2's topic-sentence rule:** the first 3–4 paragraphs of the introduction (Component A and the start of B) do **not** require strict topic sentences. They are narrative — they hook, set context, and hand off to the research question.

### Component B — "In this paper" (1 paragraph)
After Component A, there is **always** a paragraph that begins "In this paper..." (or a near-equivalent). This paragraph summarizes what the paper does in one paragraph and implicitly poses and answers the research question — if the research question wasn't already articulated at the end of Component A.

### Component C — Mini guided tour (3–6 paragraphs)
A succinct walk through the paper's findings, mirroring the structure of the body. Same content as the body, much more compressed. **Topic sentences are required from here onward.** The reader should be able to read only the topic sentences of Components C–F and follow the entire argument (the MRW test).

### Component D — Policy implications (optional, 0–1 paragraphs)
For papers with policy relevance, a short paragraph drawing the implications. Skip if the paper is not policy-facing.

### Component E — Contribution to the literature (2–3 paragraphs)
The contribution is positioned against the relevant strands. Each strand-paragraph identifies the strand, the closest prior work, and what this paper adds. Avoid laundry lists — group related papers.

### Component F — Roadmap (1 short paragraph)
"Section 2 describes the experimental design. Section 3 presents the main results. Section 4..." Brief, factual.

### Length budget
Roughly: A: ~1 page; B: ~½ page; C: ~2 pages; D: ¼–½ page; E: ~1 page; F: a few lines. Total ~5 pages.

---

## 4. Voice

The target voice is **classic style** as defined by Thomas & Turner. Classic style is a *stand* the writer takes — a set of conceptual commitments — not a list of sentence-level rules. Bertrand Russell is the canonical exemplar. Five commitments define the stand:

1. **Truth is knowable and stable.** The writer is an observer who has noticed it, not a constructor building it. The prose presents what is the case, with confidence.
2. **The writer's job is presentation, not performance.** The prose is a window onto the subject, not a stage for the writer. If the reader notices the prose, the prose has failed.
3. **The scene is one competent adult speaking to another about something they can both examine.** Not a lecture, not a sermon, not a confession, not a defense. The writer points; the reader looks.
4. **The reader is the writer's intellectual equal.** Intelligent, curious, capable of following an argument. No condescension, no apology, no over-explanation, no signposting beyond what an attentive reader needs.
5. **Words match the world transparently.** Classic style trusts that a clear sentence can say what it means. It does not hedge against the inadequacy of language.

The concrete rules below are expressions of one or more of these commitments. When a rule feels in tension with a passage you're editing, return to the stand: would Russell, or a smart curious peer, write this sentence? If no, the rule probably wins.

### Concrete rules
- **Audience:** the introduction should be readable by a smart fourth-year undergraduate in economics. Not too technical. Body sections may be more technical, but the intro is for a wide audience.
- **Active voice when possible.** "We find that X" beats "It is found that X."
- **Short sentences over long.** A 30-word sentence with two clauses usually beats a 60-word sentence with five.
- **Concrete verbs.** "X causes Y" beats "X has an impact on Y." "We measure" beats "We undertake measurement of."
- **No filler.** Cut "It is important to note that," "Interestingly," "It should be emphasized that," "At the end of the day," etc.
- **Hedge precisely, not generically.** "marginally significant (p = 0.07)" beats "somewhat suggestive."
- **Numbers should be specific.** "92 percent" beats "the vast majority." Use words for small integers in narrative ("two main findings"), digits for measurements.
- **Avoid nominalization.** "We test the hypothesis" beats "Hypothesis testing is undertaken." "Participants learned" beats "Participants exhibited learning behavior."
- **British vs American spelling:** keep whatever is consistent within the paper; do not change spelling unless asked.

### Things to avoid
- "Indeed,"-style discourse markers used as filler.
- "It is well known that..." — if it's well known, just state it.
- Strings of citations standing in for an argument: `\citep{a, b, c, d, e}` without engagement.
- Throat-clearing transitions ("Having said that," "With that in mind," "In light of the above").
- Repetition of the abstract verbatim in the intro.
- Buzzwords without precise meaning (e.g., "leverage" when "use" works).

### Voice exemplars in this repo
Sample passages from Luca's prior papers live in [`master_supporting_docs/voice/`](../../master_supporting_docs/voice/). When in doubt about a tonal call, the agent may sample a passage from one of:
- *Talking across the Aisle* (most recent — already in this repo as `paper_new.tex`)
- *News Slant*
- *News Frictions*
- *Social Media and Mental Health*
- *Facebook Effects*
- *Learning from the Past*
- *Threshold Paper*

Plus the MRW intro for the topic-sentence model.

---

## 5. Project lexicon

Preserve the project's core terms unless the user explicitly asks to change terminology. These terms carry conceptual distinctions in the paper:

- cross-partisan contact
- cross-party pairing
- same-party conversations
- counter-partisans
- information aggregation
- affective polarization
- hedonic value
- informational value
- anticipated enjoyment
- realized enjoyment
- realized learning
- self-selection wedge
- selection against cross-partisan contact

Do not smooth these into generic synonyms such as "bipartisan dialogue," "political disagreement," "intergroup contact," or "utility" unless the existing prose uses those terms for a distinct construct.

---

## 6. LaTeX-safe editing

The editor works on prose, not the mechanics of the TeX document. Unless the user explicitly asks for command-level edits:

- Do not edit inside `table`, `tabular`, `tabularx`, `longtable`, `figure`, `subfigure`, `equation`, `align`, `gather`, `multline`, `tikzpicture`, `verbatim`, or similar environments.
- Do not edit macro definitions such as `\newcommand`, `\renewcommand`, `\def`, `\DeclareMathOperator`, or generated value commands.
- Do not change bibliography declarations, citation keys, labels, refs, numerical values, macro names, or custom macros that render numbers.
- Preserve LaTeX commands and their arguments byte-for-byte when rewriting surrounding prose. This includes `\label{...}`, `\ref{...}`, `\autoref{...}`, `\nameref{...}`, `\citep{...}`, `\citet{...}`, `\input{...}`, and `\include{...}`.

After direct edits, inspect the diff before returning. If `paper_new.tex` was edited and shell access is available, compile the paper; if compilation is skipped or fails, report that clearly.

---

## 7. Editor checklist (apply on every pass)

Before returning edits, the agent should verify:

- [ ] **RAP visibility.** Can a reader skimming only topic sentences identify R, A, P?
- [ ] **Topic sentences carry the message.** No buried leads. (Exception: first 3–4 paragraphs of intro.)
- [ ] **Linguistic links.** Each topic sentence picks up a phrase from the previous one when topics chain.
- [ ] **Paragraph length.** Most paragraphs are 5–6 sentences and ≤ 8 rendered lines. A few may stretch to 9–10 lines, very few to 11–12, and at most one paragraph per paper exceeds 12 lines. Longer paragraphs flagged for splitting.
- [ ] **Consistent terms.** No interchangeable synonyms for the same construct.
- [ ] **Intro architecture.** Components A–F present in order; "In this paper" paragraph exists; roadmap exists.
- [ ] **Classic voice.** Active, concrete, no filler, no hedging beyond what evidence warrants, accessible to a smart undergrad in the intro.
- [ ] **Project lexicon.** Core terms are preserved and not replaced with generic synonyms.
- [ ] **LaTeX safety.** Protected environments, commands, labels, refs, citation keys, numbers, and generated values are unchanged unless explicitly in scope.
- [ ] **No new claims.** The editor never strengthens or invents claims; it only sharpens what is already on the page. Flag substantive gaps as questions to the author, not silent inventions.
