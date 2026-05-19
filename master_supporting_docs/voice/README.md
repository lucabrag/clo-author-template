# Voice exemplars

Reference passages for the [`prose-editor`](../../.claude/agents/prose-editor.md) agent. The agent samples from these PDFs when it needs to anchor its tonal calls in concrete examples of Luca's voice (or, in the MRW case, in the canonical example of clear topic sentences).

## What's here

### Luca's own papers (the voice ground truth)
| File | Use as exemplar for |
|---|---|
| [`Talking_across_the_aisle.pdf`](Talking_across_the_aisle.pdf) | Naturalistic experiment writeup; current revision style |
| [`NewsSlant.pdf`](NewsSlant.pdf) | Empirical IO / political economy intro structure |
| [`NewsFrictions.pdf`](NewsFrictions.pdf) | Theory + empirics balance |
| [`Social_Media_and_Mental_Health.pdf`](Social_Media_and_Mental_Health.pdf) | Causal identification writeup |
| [`FacebookEffects_Paper.pdf`](FacebookEffects_Paper.pdf) | Field experiment / RCT writeup |
| [`Learning_from_the_past.pdf`](Learning_from_the_past.pdf) | Belief-updating / behavioral writeup |
| [`Threshold_paper.pdf`](Threshold_paper.pdf) | Earlier-career voice; useful for general style |

### Style guides
| File | What it is |
|---|---|
| [`Chaubey_Research_Writing.pdf`](Chaubey_Research_Writing.pdf) | Distilled bullet summary of Varanya Chaubey's *Little Book on Research Writing* — the gold-standard guide for economics paper writing. RAP framework, top-down writing, intro architecture. |
| [`MRW_topic_sentences_exemplar.pdf`](MRW_topic_sentences_exemplar.pdf) | Mankiw, Romer & Weil (QJE 1992). The canonical example of an introduction whose argument can be followed by reading only the first sentence of each paragraph. |

## Not included (and why)

The full text of Barbara Minto's *Pyramid Principle* and Thomas & Turner's *Clear and Simple as the Truth* are not in this folder — they are copyrighted books. Their principles are already distilled into [`writing-voice.md`](../../.claude/references/writing-voice.md). If a passage from either book is genuinely needed, paste an excerpt into chat at edit time.

## How the editor uses this folder

The agent does **not** need to read every PDF on every call. The default flow is:
1. Always read [`writing-voice.md`](../../.claude/references/writing-voice.md) (lightweight).
2. When uncertain about voice, sample one passage (intro, contribution paragraph, or section opening) from one of Luca's papers — chosen to match the genre of what's being edited.
3. When uncertain about topic sentences specifically, glance at the MRW intro.
