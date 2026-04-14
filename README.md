# Public Administration Research Writing Skillset

> Word-first writing support for public administration, emergency management, and computational social science.

This workspace turns the original generic AI-writing collection into a local, reusable skill package for long-form Word drafting and revision in the social sciences. It is designed for journal-oriented writing in venues such as `Public Administration Review`, `American Political Science Review`, `Journal of Computational Social Science`, and adjacent public policy, governance, and crisis-management outlets.

## What This Version Optimizes For

- Word-first drafting and revision rather than LaTeX-first conference workflows
- Public management, emergency management, and computational social science prose conventions
- Section-aware revision for `Introduction`, `Literature Review`, `Research Design`, `Results`, `Discussion`, and `Conclusion`
- Strong protection of causal language, research design meaning, and policy interpretation boundaries
- Clear, restrained academic English instead of inflated or mechanical model-style prose
- Long-term reuse as a local `SKILL.md`, not just a one-off prompt dump

## Core Principles

1. Preserve evidence boundaries. Do not turn association into causation, suggestion into proof, or empirical findings into policy claims that the text does not support.
2. Preserve methods and terms. Keep variables, model names, identification strategies, datasets, citations, table numbers, figure numbers, and domain abbreviations stable unless explicitly asked to change them.
3. Prefer simple, formal academic prose. Use clear journal-style English rather than ornate vocabulary or obvious AI filler.
4. Stay Word-native. Output clean paragraphs that can be pasted into Word without Markdown clutter, bulletized body text, or LaTeX artifacts.
5. Do not rewrite good text for movement alone. If the original paragraph is already strong, preserve it.

## Repository Structure

- `public-management-word-writing/SKILL.md`: the agent-facing skill entry point
- `public-management-word-writing/references/core-rules.md`: shared writing guardrails for every task
- `public-management-word-writing/references/task-modes.md`: task-specific modes such as polishing, de-AI rewriting, design checking, and reviewer diagnosis
- `public-management-word-writing/references/section-guidance.md`: section-specific guidance for abstracts, introductions, literature reviews, methods, results, discussion, and rebuttals
- `public-management-word-writing/references/prompt-library.md`: copy-paste prompts for use in general LLM chat interfaces
- `public-management-word-writing/agents/openai.yaml`: UI metadata for skill discovery

## Main Use Cases

| Use case | What it does |
| --- | --- |
| English polishing | Bring Word prose to submission-ready journal English without changing substantive claims |
| De-AI rewriting | Remove mechanical phrasing, inflated transitions, and over-produced model tone |
| Chinese-to-English drafting | Turn Chinese notes or rough drafts into formal English journal prose |
| English-to-Chinese reading translation | Produce faithful Chinese translations for close reading and logic checking |
| Literature review and theory framing | Reorganize literature by debate, mechanism, and contribution rather than by loose summary |
| Research design checking | Diagnose identification logic, variable alignment, assumption gaps, and overclaiming |
| Results and discussion rewriting | Tighten interpretation, keep empirical restraint, and sharpen the contribution |
| Reviewer-style diagnosis | Surface the most likely weaknesses before submission or revision |

## Section-First Usage

This version is designed to be called with two coordinates:

- `Task Mode`
- `Section`

Recommended section names:

- `Introduction`
- `Literature Review`
- `Research Design`
- `Results`
- `Discussion`
- `Conclusion`

Recommended defaults:

| Section | Recommended task mode |
| --- | --- |
| Introduction | `polish` |
| Literature Review | `lit-review` |
| Research Design | `polish` or `design-check` |
| Results | `results-discussion` |
| Discussion | `results-discussion` |
| Conclusion | `polish` |

## How To Use

### 1. Use It As A Local Skill

Open [`public-management-word-writing/SKILL.md`](./public-management-word-writing/SKILL.md) in any agent workflow that supports local skills. The skill itself will route the task to the right mode and reference file.

For auto-discovery in a local skills system, place the `public-management-word-writing` folder in the skills directory used by your toolchain.

### 2. Use It As A Prompt Library

If you are working in a generic chat interface, open [`public-management-word-writing/references/prompt-library.md`](./public-management-word-writing/references/prompt-library.md) and copy the prompt that matches your task.

## Recommended Input Template

When you invoke the skill or paste a prompt into a model, this structure gives the best results:

```text
Target Journal:
Section:
Task Mode:
Method / Design:
Must-Preserve Terms:
Special Constraints:
Text:
```

Minimal examples:

```text
Target Journal: Public Administration Review
Section: Results
Task Mode: results-discussion
Method / Design: two-way fixed effects DID
Must-Preserve Terms: administrative burden; response capacity; county-level panel
Text: [paste the draft]
```

```text
Target Journal: Journal of Computational Social Science
Section: Literature Review
Task Mode: lit-review
Method / Design: text-as-data + classifier
Must-Preserve Terms: crisis informatics; emergency governance
Text: [paste the draft]
```

```text
Target Journal: Public Administration Review
Section: Research Design
Task Mode: design-check
Method / Design: instrumental variables
Must-Preserve Terms: IV; treatment intensity; county fixed effects
Text: [paste the draft]
```

## What Changed From The Original Project

- Removed the LaTeX-first and machine-learning-conference bias
- Replaced generic writing prompts with Word-first social-science writing modes
- Added section-specific routing and section-specific revision priorities
- Added public management, emergency management, and computational social science domain guardrails
- Added stronger controls for causal language, identification logic, and policy implication overreach
- Removed time-sensitive model ranking advice so the package remains stable over time

## Practical Scope

This package is especially suited to:

- journal articles
- revise-and-resubmit cycles
- methods sections that need claim discipline
- literature reviews that need sharper positioning
- results and discussion sections that need cleaner interpretation
- reviewer-style pre-submission diagnosis

It is less suitable for:

- heavy LaTeX formatting tasks
- bibliography repair
- fully automated citation discovery
- domain-specific quantitative verification that requires the original data and code
