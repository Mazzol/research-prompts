# Which Prompt Should I Run When?

A one-page decision tree for the `research-prompts` toolkit.

---

## Quick Decision Tree

```text
START
 |
 |-- Are you reading or triaging someone else's paper?
 |      |
 |      `-- YES -> heilmeier-extractor/
 |               (structured paper notes: problem, novelty, evidence, impact, risks)
 |
 |-- Are you writing new text and want it to sound like YOU?
 |      |
 |      `-- YES -> writing-voice/
 |               Step 1: voice-analyzer.prompt (build VOICE CARD)
 |               Step 2: write-in-voice.prompt (draft + self-check loop)
 |
 |-- Is your manuscript near-final and close to submission?
 |      |
 |      `-- YES -> brutal-review/
 |               (must-fix vs nice-to-fix triage for correctness/logic/citations)
 |
 |-- Is your slide deck near-final and close to delivery?
 |      |
 |      `-- YES -> tough-crowd/
 |               (narrative clarity, cognitive load, slide-note alignment)
 |
 `-- None of the above?
        -> pick another package from the repo README (hallucination-detector,
           orphan-finder, chalk-talk, fail-fast, etc.)
```

---

## Fast “When to Run” Guide

### 1) `heilmeier-extractor/`
Run when you need fast, reviewer-style understanding of a paper.

- **Best for:** literature review, paper triage, mentoring students on critical reading.
- **Input:** PDF (best) or abstract+intro+evaluation text.
- **Output:** Overview, SOTA limits, contributions (with `CLEVER:`), impact, realism/risks.
- **Use timing:** early-stage project discovery or before proposing new work.

### 2) `writing-voice/`
Run when AI drafting is helpful but voice drift is unacceptable.

- **Best for:** proposals, paper paragraphs, recommendation drafts, polished posts/emails.
- **Input:** your non-AI exemplars (first), then a VOICE CARD + notes/draft.
- **Output:** style model + in-voice draft with rubric scoring and revisions.
- **Use timing:** whenever drafting/revising text that should sound recognizably like you.

### 3) `brutal-review/`
Run when your paper is almost done and deadline pressure is high.

- **Best for:** final 2–24 hour pre-submission pass.
- **Input:** near-final manuscript; ideally captions + references/BibTeX too.
- **Output:** IMPORTANT vs SUGGESTED changes, consistency table, citation audit, logic-cop summary.
- **Use timing:** after restructuring is complete, before final camera-ready/submission upload.

### 4) `tough-crowd/`
Run when your talk is almost done and audience comprehension is the main risk.

- **Best for:** final pass on slides + speaker notes.
- **Input:** deck text, notes/script, optional visual descriptions, audience/time constraints.
- **Output:** must-fix vs polish list, consistency report, cognitive-load/alignment audit.
- **Use timing:** final 2–24 hours before presentation delivery.

---

## Recommended End-to-End Sequences

### Sequence A: New research direction
1. `heilmeier-extractor/` on key papers.
2. Draft concept notes with `writing-voice/`.
3. Before submission: `brutal-review/`.
4. Before talk: `tough-crowd/`.

### Sequence B: Deadline week
1. `writing-voice/` for fast, in-voice polishing.
2. `brutal-review/` for paper risk triage.
3. `tough-crowd/` for deck readiness.

---

## Input Quality Checklist (applies to all)

- Include constraints (audience, venue, page/time limits, style rules).
- Provide complete context where possible (captions, references, notes).
- Treat outputs as decision support, not autopilot.
- Never accept invented facts/citations—verify externally before shipping.
