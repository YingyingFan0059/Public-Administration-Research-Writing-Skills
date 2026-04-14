# Core Rules

Use these rules for every task in this skill.

## 1. Preserve Meaning First

- Do not change the research question, main claim, mechanism, or contribution unless the user explicitly asks for substantive reframing.
- Do not add evidence, literature, policy implications, mechanisms, or robustness claims that are not already supported by the source text.
- Do not remove limitations, uncertainty, or scope conditions when polishing.

## 2. Protect Causal And Empirical Boundaries

- Do not turn correlational language into causal language.
- Do not turn cautious verbs such as `suggest`, `indicate`, `is associated with`, `is linked to`, or `may reflect` into stronger verbs such as `demonstrate`, `prove`, or `cause` unless the original text already justifies that move.
- Keep moderation, mediation, heterogeneity, and robustness claims at the same strength as the source.
- Distinguish empirical findings from normative conclusions and policy recommendations.

## 3. Preserve Methods, Variables, And Citations

- Keep variable names, treatment labels, outcome labels, dataset names, institution names, sample descriptions, and scale anchors stable.
- Keep model and design terms stable, including but not limited to `IV`, `DID`, `RDD`, `event study`, `fixed effects`, `matching`, `survey experiment`, `case study`, `text-as-data`, `topic model`, `network analysis`, `classifier`, and `LLM`.
- Keep citation markers, author-year references, table numbers, figure numbers, appendix references, and note references unless the user explicitly asks to change them.
- Do not expand standard field abbreviations unless asked.

## 4. Word-First Formatting

- Treat the target output as prose that should paste cleanly into Word.
- Avoid Markdown emphasis, LaTeX syntax, itemized body text, and decorative formatting inside the revised passage.
- Keep revised prose in complete paragraphs unless the user explicitly asks for bullets, outlines, or notes.
- When the output includes labeled parts such as `Part 1 [Revised Text]`, keep the labels outside the revised prose itself.

## 5. Preferred Language Style

- Use formal academic prose.
- Prefer simple, precise, widely understood vocabulary over ornate synonyms.
- Avoid contractions in English academic output.
- Avoid obvious AI filler such as empty intensifiers, generic novelty claims, and decorative transitions.
- Avoid overused words and phrases when they add no precision, including examples such as `leverage`, `delve into`, `tapestry`, `it is worth noting that`, `first and foremost`, and `needless to say`.
- Vary sentence structure enough to sound natural, but do not chase novelty for its own sake.

## 6. Public Management And Social Science Norms

- Keep the prose compatible with public administration, public policy, emergency management, political science, and computational social science journals.
- Prefer explicit institutional and empirical language over vague management cliches.
- Make practical implications restrained and evidence-led.
- Do not overstate generalizability beyond the observed case, dataset, setting, or identification strategy.

## 7. Chinese Output Rules

- Use clean academic Chinese rather than literal machine-style calques.
- Do not place English glosses in parentheses after Chinese terms unless the user explicitly asks for bilingual output.
- Use full-width Chinese punctuation in Chinese prose when appropriate.
- Keep the meaning aligned closely enough that the Chinese output can be used for logic checking against the English text.
