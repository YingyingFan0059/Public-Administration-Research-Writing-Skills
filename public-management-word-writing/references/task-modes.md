# Task Modes

Pick the mode that best matches the user's request. If the request mixes modes, prioritize the main deliverable and keep the others secondary.

## Section-Sensitive Defaults

These defaults apply when the user gives a section name but does not specify the best mode:

| Section | Default mode | Secondary mode when needed |
| --- | --- | --- |
| Introduction | `polish` | `humanize` |
| Literature Review | `lit-review` | `polish` |
| Research Design | `polish` | `design-check` |
| Results | `results-discussion` | `polish` |
| Discussion | `results-discussion` | `humanize` |
| Conclusion | `polish` | `humanize` |

Use `design-check` whenever the user is really asking about inferential validity rather than prose.

## `polish`

Use when the user has an English Word passage and wants journal-ready language.

- Improve syntax, clarity, flow, grammar, punctuation, and article usage.
- Keep the original claim strength, method meaning, and citation structure.
- Rewrite sentences only when the gain in clarity is real.
- Let the section determine what counts as a useful edit:
  - `Introduction`: move the question, gap, and contribution forward
  - `Research Design`: improve auditability and precision, not rhetorical smoothness alone
  - `Conclusion`: improve synthesis and restraint
- Default output:
  - `Part 1 [Revised Text]`
  - `Part 2 [Translation]`
  - `Part 3 [Modification Log]`

## `humanize`

Use when the user wants to remove obvious AI tone or make the passage sound more like a careful human scholar.

- Remove empty transitions, inflated novelty claims, repetitive sentence rhythm, and mechanical parallel structures.
- Keep the prose restrained and journal-like rather than conversational.
- If the original passage already reads naturally, keep it and say so in `Part 3`.
- Use this carefully in `Research Design` and `Results`; style cleanup must never blur operational definitions or empirical claims.
- Default output:
  - `Part 1 [Revised Text]`
  - `Part 2 [Translation]`
  - `Part 3 [Modification Log]`

## `zh-to-en`

Use when the user provides Chinese notes, outlines, or rough prose and wants English academic writing.

- Convert fragmented ideas into coherent journal prose.
- Preserve the author's intended meaning, empirical boundaries, and key terms.
- Keep the English output simple, formal, and Word-safe.
- Let the section define the paragraph architecture:
  - `Introduction`: puzzle -> gap -> contribution
  - `Literature Review`: debate -> limit -> positioning
  - `Research Design`: data -> measurement -> identification
  - `Results`: finding -> support -> restraint
  - `Discussion`: interpretation -> limits -> implications
  - `Conclusion`: contribution -> boundary -> implication
- Default output:
  - `Part 1 [Revised Text]`
  - `Part 2 [Translation]`
  - `Part 3 [Modification Log]`

## `en-to-zh`

Use when the user wants a faithful Chinese translation for reading, logic checking, or discussion.

- Translate closely enough that the user can map the Chinese back to the English source.
- Remove formatting artifacts that do not matter for reading.
- Do not silently improve the underlying logic unless the user explicitly asks.
- Default output:
  - `Part 1 [Translation]`
  - `Part 2 [Key Terms]` when needed
  - `Part 3 [Notes]` only if necessary

## `zh-to-zh`

Use when the user has colloquial or fragmented Chinese notes and wants formal Chinese academic prose.

- Rebuild logic, clean up tone, and remove spoken-language habits.
- Keep one paragraph focused on one central point.
- Preserve technical terms that are already standard in the field.
- Default output:
  - `Part 1 [Refined Text]`
  - `Part 2 [Logic Flow]`

## `lit-review`

Use when the user wants help rewriting or reorganizing a literature review, theory section, or contribution framing.

- Organize by debate, mechanism, or explanatory gap rather than by loose author listing.
- Clarify what the manuscript adds relative to the literature without overselling novelty.
- Preserve all author-year references supplied by the user.
- Use this mode by default for `Literature Review`, theory framing inside `Introduction`, and contribution positioning in the opening pages.
- Default output:
  - `Part 1 [Revised Text]`
  - `Part 2 [Translation]`
  - `Part 3 [Positioning Notes]`

## `design-check`

Use when the user wants a design, methods, or identification logic diagnosis.

- Prioritize flaws in question-design alignment, identification strategy, variable construction, assumption handling, and overclaiming.
- Separate substantive design problems from pure writing problems.
- Be concrete about what is missing or weak.
- Use this mode for `Research Design` first, and optionally for `Results` when interpretation outruns design.
- Default output:
  - findings first
  - then targeted revisions or experiments
  - only then optional rewritten text if the user asks for it

## `results-discussion`

Use when the user wants help on results, interpretation, or discussion sections.

- Tighten the distinction between reported findings and interpretation.
- Keep interpretations proportional to the evidence.
- Make policy implications explicit but restrained.
- Split the section mentally before editing:
  - `Results`: what the model or analysis shows
  - `Discussion`: what those results plausibly mean
  - `Conclusion`: what the manuscript can defensibly claim overall
- Default output:
  - `Part 1 [Revised Text]`
  - `Part 2 [Translation]`
  - `Part 3 [Modification Log]`

## `reviewer-diagnosis`

Use when the user wants a reviewer-style critique of a section or full draft.

- Lead with findings, ordered by severity.
- Focus on weaknesses that would materially affect review outcomes.
- Distinguish writing problems, design problems, and contribution-positioning problems.
- When the text is only one section, judge it by that section's job rather than by whole-paper completeness.
- Default output:
  - `Part 1 [Review Report]`
  - `Part 2 [Revision Priorities]`
  - `Part 3 [Optional Rewrite Targets]`
