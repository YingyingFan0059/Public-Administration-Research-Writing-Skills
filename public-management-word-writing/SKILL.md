---
name: public-management-word-writing
description: Word-first academic writing support for public administration, public policy, emergency management, and computational social science. Use when revising, translating, humanizing, structuring, or diagnosing manuscript text for journal submission while preserving claim strength, methods, variables, citations, and policy interpretation boundaries.
---

# Public Management Word Writing

## Quick Start

- Treat the user's material as Word-native prose unless they explicitly ask for LaTeX.
- Default to plain paragraphs with no Markdown emphasis, no bulletized body text, and no decorative formatting inside the revised prose.
- Infer the task mode first: `polish`, `humanize`, `zh-to-en`, `en-to-zh`, `zh-to-zh`, `lit-review`, `design-check`, `results-discussion`, or `reviewer-diagnosis`.
- Always identify the manuscript section for section-sensitive tasks. The default section set is `Introduction`, `Literature Review`, `Research Design`, `Results`, `Discussion`, and `Conclusion`.
- If the user does not name the section, infer it from cues in the text and state the inference briefly when it matters.
- Infer or briefly confirm the minimum context only when needed: target journal, manuscript section, method, and must-preserve terms.

## Section-First Operation

Treat this skill as a two-axis system:

- Axis 1: task mode
- Axis 2: manuscript section

For routine revision tasks, section handling should drive the editing priorities:

- `Introduction`: sharpen the puzzle, gap, and contribution
- `Literature Review`: organize by debate, mechanism, and positioning
- `Research Design`: protect identification logic, variables, assumptions, and sample definitions
- `Results`: separate reported findings from interpretation
- `Discussion`: interpret patterns, limits, and implications without overstating evidence
- `Conclusion`: state the contribution, boundary conditions, and restrained implications

If the user asks for `polish` without a section, infer the section before making large edits.

## Core Workflow

1. Classify the task mode and manuscript section.
2. Read [`references/core-rules.md`](./references/core-rules.md) for every task.
3. Read [`references/task-modes.md`](./references/task-modes.md) for the selected mode.
4. Read [`references/section-guidance.md`](./references/section-guidance.md) for section-specific priorities, failure patterns, and preservation rules.
5. Read [`references/prompt-library.md`](./references/prompt-library.md) when the user wants a copy-paste prompt for another model.
6. Produce Word-safe output that preserves empirical meaning and field conventions.

## Section Routing Heuristics

Use these cues when the section is not stated explicitly:

- `Introduction`: research question, real-world importance, gap, contribution, roadmap
- `Literature Review`: author-year density, schools of thought, competing explanations, theoretical framing
- `Research Design`: data, sample, variables, measures, models, identification, assumptions
- `Results`: coefficients, tables, figures, effect sizes, robustness, heterogeneity
- `Discussion`: what the findings mean, mechanism interpretation, broader implications, limits
- `Conclusion`: summary takeaway, contribution, boundary conditions, future research, policy implications

## Default Output

- For revision and rewriting tasks, default to:
  - `Part 1 [Revised Text]`
  - `Part 2 [Translation]`
  - `Part 3 [Modification Log]`
- For diagnostic tasks, return findings first, then targeted fixes.
- Keep abbreviations such as `IV`, `DID`, `RDD`, `FE`, `NLP`, and `LLM` unless the user explicitly asks to expand them.
- Do not invent citations, mechanisms, policy claims, or robustness checks.

## Field Guardrails

- Preserve claim strength. Do not upgrade association to causation or suggestion to proof.
- Preserve variables, model names, datasets, institutions, scale labels, table and figure numbering, and citation markers.
- Preserve the author's intended level of caution, especially in policy implications and external-validity statements.
- Prefer simple, formal academic English over inflated or promotional phrasing.
- Prefer precise Chinese academic prose over literal calques when writing in Chinese.

## Preferred Input Template

Use or infer this structure:

```text
Target Journal:
Section:
Task Mode:
Method / Design:
Must-Preserve Terms:
Special Constraints:
Text:
```

## Escalation Rules

- Ask the user before changing journal target, section purpose, method framing, or substantive interpretation.
- If the text is already strong, do not rewrite for the sake of movement. Say so and keep the original.
