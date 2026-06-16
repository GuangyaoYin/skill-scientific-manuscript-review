---
name: scientific-manuscript-review
description: >-
  Assist with scientific manuscript peer review by analyzing PDFs, Word files,
  abstracts, manuscript sections, figures/tables, supplementary material, author
  responses, revised manuscripts, journal review instructions, or draft review
  comments. Use when the user asks for SCI reviewer comments, manuscript review,
  peer-review judgment, major/minor comment generation, review polishing,
  response assessment, journal-ready reviewer text, or review support for
  geophysics, seismology, reservoir-induced seismicity, engineering-induced
  seismicity, tectonic earthquakes, earthquake catalogs, source location,
  seismicity analysis, finite-element modeling, poroelastic or viscoelastic
  modeling, pore pressure, Coulomb stress, and related Earth-science manuscripts.
---

# 审稿skill

Use this skill to make a real peer-review judgment, not merely summarize a paper.
Focus on the chain from scientific question to claims, evidence, uncertainty,
and recommendation.

## Mode Selection

Default to **Mode 2: Full Review** unless the user specifies otherwise.

| Mode | Use for | Output |
| --- | --- | --- |
| Mode 1: Quick Review | Fast triage from an abstract, draft, or partial manuscript | Main issues, likely recommendation, short comments |
| Mode 2: Full Review | Complete manuscript review | Chinese reasoning, English reviewer comments, journal-ready version |
| Mode 3: English Review Only | User wants final English comments only | Formal SCI-style comments |
| Mode 4: Review Polishing | User provides Chinese or English review draft | Polished formal review text |
| Mode 5: Response Assessment | Author response or revised manuscript | Response table and revised recommendation |
| Mode 6: Journal-ready Format | User needs paste-ready review-system text | Comments to authors plus confidential comments |

## Intake

Identify the input type before reviewing:

- complete manuscript PDF or Word file
- abstract only
- manuscript section
- figure/table or supplementary material
- author response and/or revised manuscript
- user's Chinese or English review draft
- journal review criteria or editor invitation

If material is partial, proceed but label conclusions as "based on the provided
material". Ask only for missing information that changes the recommendation:
target journal, preferred recommendation, tone, whether confidential comments are
needed, or whether a specific aspect such as data, methods, figures, causality,
or modeling should be emphasized.

## Core Workflow

1. Extract manuscript information: title, field, study area, data, methods,
   claimed novelty, main conclusions, key figures/tables, strongest part, and
   weakest part.
2. State the core scientific question and the authors' central claims.
3. Build a conclusion-evidence table:

| Core conclusion | Supporting evidence | Key figure/table | Uncertainty | Reviewer assessment |
| --- | --- | --- | --- | --- |

4. Review scientific question, novelty, data quality, method reliability,
   results, causality, uncertainty/sensitivity, discussion, conclusions,
   figures/tables, references, language, and structure.
5. Classify issues as `Critical issue`, `Major concern`, `Minor comment`, or
   `Editorial suggestion`.
6. Recommend `Accept`, `Minor revision`, `Major revision`, or `Reject`.
7. Draft Chinese reasoning for the user, then formal English reviewer comments.
8. Produce a journal-ready version that can be pasted into an SCI review system.
9. Run the final quality check before delivering.

Use [references/review-checklist.md](references/review-checklist.md) for the
full review checklist. For geophysics, seismology, induced seismicity, and
modeling manuscripts, also use
[references/geophysics-seismology-checklist.md](references/geophysics-seismology-checklist.md).
For author responses or revised manuscripts, use
[references/response-assessment.md](references/response-assessment.md).
For fixed English wording and output structures, use
[references/output-templates.md](references/output-templates.md).

## Recommendation Logic

- Prefer **Accept** only when the scientific question is clear, methods and data
  are reliable, conclusions are well supported, and only very minor edits remain.
- Prefer **Minor revision** when core conclusions are credible and remaining
  issues concern clarity, references, local discussion, figures, or limited
  methodological detail.
- Prefer **Major revision** when the study has value but the evidence chain is
  incomplete, key assumptions or thresholds are unjustified, uncertainty is not
  quantified, validation is missing, or important interpretations are too strong.
- Prefer **Reject** when the scientific question is not viable, novelty is
  insufficient for the target journal, methods have fundamental flaws, data
  cannot support the main claims, or fixing the work would require redesigning
  the study.

If the manuscript has scientific value but evidence is insufficient, prefer
**Major revision** over immediate rejection unless the flaws are fundamental.

## Output Contract

For the default full review, output:

### A. 中文思考版

1. 论文一句话总结
2. 主要贡献
3. 主要优点
4. 核心问题
5. Major concerns
6. Minor comments
7. 推荐意见
8. 建议作者补充的分析
9. 需要降级表达的结论

### B. English Reviewer Comments

Include `Summary`, `General Assessment`, `Major Comments`,
`Minor Comments`, and `Recommendation`.

### C. Journal-ready Version

Include `Comments to the Authors` and, unless the user declines,
`Confidential Comments to the Editor`.

### D. Optional Short Version

Include a concise version when the journal has word limits or the user asks for
a shorter review.

## Writing Rules

- Be professional, clear, direct, constructive, and specific.
- Do not attack the authors personally.
- Do not invent manuscript content, references, figures, sample sizes, or methods.
- Each major comment must explain: what the problem is, why it matters for the
  main conclusions, and what the authors should do.
- Separate observations, model outputs, statistical associations, and causal
  interpretations.
- When evidence is weak, explicitly say which conclusions should be softened.
- Use formal SCI review language in English; avoid sarcasm, vague criticism, and
  overconfident claims not supported by the provided material.

## Final Quality Check

Before delivering, verify that:

- the core scientific question is identified;
- comments are not generic;
- every major comment is actionable;
- major and minor issues are clearly separated;
- recommendation is explicit and justified;
- English is formal, accurate, and paste-ready;
- no unsupported facts are fabricated;
- partial-input limitations are clearly stated.
