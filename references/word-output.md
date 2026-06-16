# Word Review Report Output

Use this reference whenever the skill produces its default final deliverable.
The final deliverable is a formatted, editable `.docx` file unless the user
explicitly asks for text-only output.

Coordinate with the Documents skill/plugin workflow for creating, editing,
rendering, and visually checking DOCX files.

## Default Delivery

After completing the review:

1. Output only a brief Chinese summary in chat:
   - recommendation;
   - top major concerns;
   - generated Word file link/path.
2. Generate a complete Word report as the primary deliverable.
3. If Markdown or plain text is useful, provide it only as an additional output;
   the Word report remains the default final deliverable.

## File Naming

Use a normalized lowercase English slug with words separated by underscores.
Remove unsafe path characters and keep the slug short.

Default:

```text
review_report_[short_title]_[yyyy-mm-dd].docx
```

Example:

```text
review_report_reservoir_induced_seismicity_2026-06-17.docx
```

If the short title cannot be inferred:

```text
review_report_manuscript_[yyyy-mm-dd].docx
```

For author response or revised-manuscript assessment:

```text
response_assessment_[short_title]_[yyyy-mm-dd].docx
```

## Page and Typography

Use:

- page size: A4;
- margins: 2.54 cm on all sides;
- body Chinese font: SimSun;
- body English font: Times New Roman;
- body size: 12 pt, equivalent to Chinese small four when applicable;
- line spacing: 1.5;
- moderate spacing before and after paragraphs;
- no decorative colors;
- overall style: concise, formal, suitable for research archiving.

Heading levels:

- level 1: bold, 14 pt;
- level 2: bold, 12 pt;
- level 3: bold or italic;
- make `Major Comments` and `Recommendation` visually prominent with bold text.

Header and footer:

- header: `Scientific Manuscript Review Report`;
- footer: page number.

Tables:

- use three-line tables or clean grid tables;
- enable automatic text wrapping;
- fit table width to page;
- keep the core conclusion-evidence table readable.

## Required Word Sections

Use this structure:

```text
Scientific Manuscript Review Report

Section 1. Chinese Reasoning Version
1.1 Manuscript Summary
1.2 Main Contributions
1.3 Strengths
1.4 Core Issues
1.5 Major Concerns
1.6 Minor Comments
1.7 Recommendation
1.8 Analyses Required from the Authors
1.9 Conclusions That Should Be Softened

Section 2. English Reviewer Comments
Summary
General Assessment
Major Comments
Minor Comments
Recommendation

Section 3. Core Conclusion-Evidence Chain
[table]

Section 4. Journal-ready Version
Comments to the Authors
Confidential Comments to the Editor

Section 5. Reviewer Checklist

Section 6. Required Author Revision List
```

If the input is partial, add this note near the beginning of the Word document:

```text
This review is based on the provided material rather than the full manuscript.
```

For missing information, write `Not provided`. Do not infer unsupported details.

## Section 4 Rules

Section 4 must be titled exactly:

```text
Section 4. Journal-ready Version
```

This section must contain only English text that the user can copy directly into
an SCI journal review system. Do not include Chinese notes, internal analysis,
or informal framing such as "the following is" or "I think".

Use this structure:

```text
Comments to the Authors

[One-paragraph summary]

[One-paragraph general assessment]

Major Comments

[Title]
[Detailed comment]

[Title]
[Detailed comment]

Minor Comments

[Comment]
[Comment]

Recommendation

I recommend [major revision/minor revision/rejection/acceptance] because [brief justification].

Confidential Comments to the Editor

[Confidential comments]
```

## Response Assessment Reports

For author response checks, use the `response_assessment_...docx` naming pattern
and include:

- response assessment table;
- unresolved major concerns;
- new issues introduced by revision;
- final recommendation after revision;
- journal-ready second-round comments.

## DOCX Self-Check

Before delivering, verify:

- Word file exists and opens or renders when possible;
- report contains all required sections;
- title levels are clear;
- Chinese and English sections are separated;
- `Section 4. Journal-ready Version` is standalone;
- major comments are numbered clearly;
- minor comments are numbered clearly;
- recommendation is explicit;
- confidential comments are separate;
- tables are neat and fit page width;
- internal analysis is not mixed into formal English reviewer comments;
- missing manuscript information is marked `Not provided`;
- no unsupported manuscript facts are invented;
- style is formal and suitable for research archiving.
