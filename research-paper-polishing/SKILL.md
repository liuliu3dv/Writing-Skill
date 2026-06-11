---
name: research-paper-polishing
description: Revise and polish CS/ML academic papers for clarity, readability, and contribution alignment using sentence-level edits, paragraph restructuring, active voice, and continuation markers. Use when editing, proofreading, or refining existing LaTeX/Markdown prose; fixing awkward paragraphs; reducing passive voice and ambiguous pronouns; or running a final language polish pass before submission.
---

# Research Paper Polishing

## Overview

Use this skill for **revision and polishing** of an existing draft.
For section drafting, story design, and claim-evidence checks, use `research-paper-writing` first; return here for language-level refinement.

Primary source: Sebastian Nowozin's [Ten Tips for Writing CS Papers (Part 1 & 2)](https://www.nowozin.net/sebastian/blog/ten-tips-for-writing-cs-papers-part-1.html).

## When to Use

- User asks to **polish**, **revise**, **proofread**, or **improve readability**
- A paragraph "does not flow" or feels dense
- Draft has passive voice, vague `this/that/which`, or overly complex sentences
- Paper lacks a clear contribution anchor across sections
- Final submission pass after content is stable

## Core Workflow

1. **Anchor the contribution** before sentence edits.
2. Classify requested changes as **substantial** or **minor** (see below).
3. Run **paragraph surgery** (reverse outline → split/merge → rewrite).
4. Run **language passes** (simple language, active voice, pronoun clarity).
5. Add or strengthen **continuation markers** at section boundaries.
6. Return revised text plus a compact polish report.

Load detailed rules only when needed:

- Full tip reference: `references/nowozin-tips.md`
- Scan checklist: `references/polish-checklist.md`

## Step 1: Anchor the Contribution

Before polishing prose, identify the paper's contribution type:

| Type | Meaning | Reader expectation |
|------|---------|------------------|
| **Insight** | Explains something that already exists | New understanding, analysis, or explanation |
| **Performance** | Does something better than prior work | Stronger numbers, efficiency, or quality |
| **Capability** | Enables something previously impossible | New task, setting, or functional ability |

State this explicitly (internally or in the report). Every section should read as a **facet of this contribution**:

- Introduction → motivates why the contribution matters
- Related Work → differentiates prior work from the contribution
- Method → describes the contribution
- Experiments → verifies the contribution works as claimed

Remove or relocate content that does not support the contribution (e.g., tutorial-style digressions on unrelated methods).

## Step 2: Substantial vs Minor Changes

**Substantial** (do first; may require rewrites beyond local edits):

- Add/remove/reorder sections
- Change contribution framing or scope
- Restructure argument order
- Split overloaded paragraphs that change section logic

**Minor** (polish passes; fix locally):

- Word order, typos, tense consistency
- Passive → active voice
- Clarify pronouns and noun references
- Shorten sentences; remove redundancy
- Strengthen transitions and continuation markers

If the user only asked for a light polish but substantial issues appear, flag them separately instead of silently restructuring the whole paper.

## Step 3: Paragraph Surgery

Use this recipe for any section or paragraph batch:

1. **Extract ideas**: list one bullet per idea or argument point.
2. **Order by dependency**: prerequisites before conclusions.
3. **One paragraph = one idea** (length may vary).
4. **Glue each paragraph**:
   - Opening sentence states the paragraph's job.
   - Closing sentence previews what follows or hands off to the next paragraph.
5. **Reverse outline** after rewriting:
   - Thesis / section claim
   - Each paragraph topic sentence
   - Evidence or explanation under each paragraph
   - Remove or split any paragraph that maps to multiple bullets.

If flow is still weak, add temporary subheadings or explicit transition phrases during revision, then remove unnecessary ones.

## Step 4: Language Passes

Run these passes in order on the target text:

### 4a. Simple language

- Prefer short sentences and direct structure.
- Minimize jargon; define terms before reuse.
- Cut ornate or translated-native phrasing (long nested clauses, abstract-before-concrete ordering).
- Prefer concrete nouns and verbs over nominalizations.

### 4b. Active voice

Default to active voice. Acceptable passive exceptions:

- Describing others' prior work (impersonal reporting)
- Reporting raw experimental observations without interpretation

Even then, prefer active when equally clear: "Miller and Smith studied …" over "… was studied by Miller and Smith."

### 4c. Ambiguous pronouns

Highlight every `this`, `these`, `that`, `which`, and bare `they/it`.
Replace with explicit nouns: "this approach" → "this enumeration approach".
Prefer restrictive "that" over non-restrictive "which" when appropriate for American English CS style.

### 4d. Continuation markers

At section and subsection openings, add two elements when missing:

1. **Roadmap**: what the reader will see next.
2. **Relevance**: why it matters for the contribution.

Example pattern: "We now describe our model for X. While Y is standard, Z is a novel contribution."

Do not rely only on an Introduction mini table-of-contents; markers must sit next to the content they introduce.

## Step 5: Visual and Page-1 Check (when figures are in scope)

If the user includes figures or asks about presentation:

- Consider a **page-1 teaser figure**: understandable in ~20 seconds, self-contained caption.
- Flag orthogonal figure content that distracts from the contribution.

## Execution Rules

1. Preserve technical meaning and claims unless the user asks to change content.
2. Keep terminology stable; do not rename core terms without reason.
3. Polish paragraph-by-paragraph; do not patch random sentences without checking section flow.
4. When co-authors' writing styles differ, prioritize **coherence and contribution alignment** over uniform voice.
5. For LaTeX input: preserve commands, labels, citations, and math; polish prose only.
6. If a claim sounds stronger after polishing, flag it for evidence review (defer to `research-paper-writing` claim-evidence checks).

## Output Contract

When polishing text, return:

1. **Contribution anchor** (type + one-sentence statement).
2. **Change class** (substantial items handled vs deferred minor items).
3. **Revised text** with brief inline notes only where a non-obvious rewrite happened.
4. **Polish report** using this template:

```markdown
## Polish Report

### Contribution anchor
- Type: Insight | Performance | Capability
- Statement: ...

### Paragraph changes
- [location]: split | merge | rewrite — reason

### Language fixes
- Passive → active: N instances
- Pronoun clarifications: N instances
- Continuation markers added: [locations]

### Remaining risks
- [ ] item needing author decision or evidence check
```

5. Optional: run `references/polish-checklist.md` and report unchecked items.

## Complementary Skills

- Drafting / section templates / claim-evidence alignment → `research-paper-writing`
- Paragraph flow deep dive → `research-paper-writing` → `references/does-my-writing-flow-source.md`
