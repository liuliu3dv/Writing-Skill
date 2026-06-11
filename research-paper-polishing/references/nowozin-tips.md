# Nowozin: Ten Tips for Writing CS Papers

Source: Sebastian Nowozin, 2015.
- Part 1: https://www.nowozin.net/sebastian/blog/ten-tips-for-writing-cs-papers-part-1.html
- Part 2: https://www.nowozin.net/sebastian/blog/ten-tips-for-writing-cs-papers-part-2.html

Recommended book: Jean-Luc Lebrun, *Scientific Writing: A Reader and Writer's Guide*.

---

## 1. Use Simple Language

Complex ideas do not require complex sentences.

- Short sentences, clear logical structure, minimal jargon.
- CS writing is often clearer than other fields, but junior authors may copy non-English rhetorical patterns (long sentences, abstract-before-concrete).
- Oppenheimer (2006): needless long words reduce perceived quality.

**Polish action**: shorten sentences; move concrete facts before interpretation; replace nominalizations with verbs.

---

## 2. State Your Contribution

Most CS papers contribute exactly one of:

1. **Insight** — explain something already there
2. **Performance** — do something better
3. **Capability** — do something new

State the category early (ideally in the abstract) to set reader expectations.

**Polish action**: verify abstract/intro opening matches the category; align superlatives with evidence.

---

## 3. See Everything as a Facet on the Contribution

Once the contribution is clear, every section supports it.

Common failures:

- Contribution never stated → reader finishes agreeing with details but unsure of the point.
- Long orthogonal tutorial on another method → interesting but negative value; cut or move to appendix.

**Polish action**: for each section, ask "Which facet of the contribution does this paragraph show?"

---

## 4. Consider a Page-1 Figure

Popularized in SIGGRAPH; spreading to other areas.

Good page-1 figure:

- **Simple**: grasp in ~20 seconds
- **Self-contained**: caption carries necessary context; caption stays short

Exceptions: some theory papers may not need one.

**Polish action**: suggest teaser figure/caption rewrites when visuals are in scope.

---

## 5. Avoid the Passive Voice

Active voice is easier to read and more engaging; modern style guides favor it.

Passive may be acceptable when:

- Reporting others' work impersonally
- Reporting experimental observations without interpretation

**Before (passive-heavy)**:
> Such a linear program can be solved efficiently … the hypothesis whose constraint is violated the most is identified and added … Each time a hypothesis is added, the optimal solution is updated …

**After (active)**:
> We can solve such a linear program efficiently … we identify the hypothesis with the largest constraint violation and add it to the hypothesis set … Each time we add a hypothesis, we also update the optimal solution …

**Polish action**: rewrite passives unless the impersonal tone is intentional.

---

## 6. Ideal Structure of a Paragraph

Formal structure (sections, paragraphs, sentences) should mirror content structure.

Rules:

1. One paragraph = one idea or one argument point.
2. Paragraph **beginning** and **end** glue it to surrounding content.

**Recipe**:

1. Bullet-list ideas for the section (one bullet = one idea).
2. Order bullets by dependency.
3. Write one paragraph per bullet.
4. Optionally add opening/closing bridge paragraphs for the section.

**Bad example** (two ideas in one paragraph):
> As already mentioned to our knowledge (Argyriou et al., 2006) were the first … We will defer … We denote with g the objective value …

Problems: redundant/apologetic opening; notation motivation unclear.

**Better** (split + explicit glue):
> (Argyriou et al., 2006) first recognized … and we now discuss the connection to our work.
>
> To make the connection explicit we first establish the notation … We use g to denote …

**Polish action**: reverse outline → split overloaded paragraphs → rewrite openings/closings.

---

## 7. Avoid Ambiguous Relative Pronouns

`this`, `these`, `that`, `which`, bare `they` often seem clear to the writer but ambiguous to readers.

**Fix**: add the noun being referred to.

**Before**:
> Most of them are optimization methods, which detect one pattern … They are different from our approach … they do not have a minimum support constraint. Instead they try to find …

**After**:
> Most of them are optimization methods, detecting one pattern … These optimization methods are different from our approach … other methods do not have a minimum support constraint and instead try to find …

Note: American colleagues often prefer restrictive **that** over **which** when appropriate.

**Polish action**: highlight all relative pronouns in a pass; replace or delete.

---

## 8. Provide Continuation Markers

Continuation markers tell the reader **what comes next** and **why it matters**.

Example (Method opening):
> We now describe our model for tracking fast moving objects. While the motion model is standard, the observation model for raw ToF captures is a novel contribution.

Two elements:

1. Roadmap (what will be presented)
2. Relevance to contribution

Why it matters:

- Enables efficient navigation (especially for reviewers)
- Provides re-entry points after partial misunderstanding

Co-locate markers with the content — an Introduction-only section roadmap is insufficient.

**Polish action**: add/strengthen markers at section and subsection openings.

---

## 9. Multiple Authors (Revision Discipline)

Content coordination:

- Avoid splitting by section among authors for the first full draft → incoherent voice and balance problems.
- Prefer one drafter, then group iteration.

When iterating:

- **Minor changes**: local clarifications, word order, typos → full-paper polish passes.
- **Substantial changes**: section add/remove, reorder, contribution resize → do early.

Technology tips (for human authors):

- Version control with readable diffs (e.g., git + web UI)
- LaTeX: one sentence per line to ease merges

**Polish action**: treat agent edits as minor unless user requests structural rework; flag substantial issues separately.

---

## 10. Authorship and Author Ordering

Not a language-polishing topic. Defer to team/lab policy when users ask about author lists.

---

## Quick Before/After Patterns

| Pattern | Weak | Stronger |
|---------|------|----------|
| Opening | "As already mentioned to our knowledge …" | "(Author et al., YEAR) first …; we now connect this to our work." |
| Passive chain | "X is computed and Y is updated …" | "We compute X and update Y …" |
| Vague this | "This shows …" | "This ablation shows …" |
| Section start | Jump into equations | "We now describe … While A is standard, B is novel." |
| Overloaded ¶ | Related work + notation + method detail | Split; one idea per paragraph |
