---
name: human-writing-review
description: Review AI-like or overly polished prose and improve it into natural, human-written Japanese while preserving intended meaning and factual claims. Use for note posts, Notion articles, landing-page copy, business writing, owned-media articles, and similar prose when the user wants diagnosis, editing guidance, or a revised version.
---

# Human Writing Review

Review Japanese prose for patterns that make it feel AI-generated, generic, over-structured, or unnaturally polished, then improve it without changing the writer's intended meaning, factual claims, audience, or purpose.

## Scope

Use this Skill when the user wants one or both of these outcomes:

- review prose for AI-like, generic, padded, overly uniform, or logically weak writing
- revise the prose into a more natural version while preserving its substance

This Skill covers review and revision as one editorial workflow. Do not split them into separate responsibilities when the user needs both.

Do not expand the task into SEO strategy, keyword research, fact-checking, LLMO, article planning, source research, or content ideation. If those are needed, keep them separate from this Skill. You may improve how supplied facts and claims are expressed, but do not verify or invent them.

Do not simulate “human writing” by adding typos, fake hesitation, slang, filler, or arbitrary quirks.

## Runtime references

Load references only when they are useful for the current request.

- Read `references/review-patterns.md` when diagnosing why prose feels AI-like, when explaining findings, or when the relevant failure pattern is not obvious. Skip it for a straightforward rewrite where the issues are already clear.
- Read `references/medium-guidance.md` when the user identifies a medium such as note, Notion, landing page, business writing, or owned media and medium-specific editing choices materially affect the result.

Do not load references merely because they exist.

## Workflow

### 1. Establish context

Infer from the text and request when possible:

- intended reader
- purpose
- formality and voice
- facts, terminology, or claims that must remain unchanged
- whether the user wants review only, rewrite only, or both

Do not ask follow-up questions when the text already gives enough context. When uncertainty materially affects the edit, make the smallest conservative assumption and state it briefly.

### 2. Diagnose the highest-impact issues

Look first for problems that affect meaning and usefulness:

1. unclear or unsupported logical relationships
2. unnecessary or repetitive content
3. vague abstraction or generic claims
4. overly uniform sentence or paragraph rhythm
5. mechanical emphasis or excessive signposting
6. weak specificity where the source text actually supports a clearer statement

Prioritize root causes rather than annotating every stylistic symptom. Use `references/review-patterns.md` when a deeper rubric is needed.

### 3. Decide what to remove, clarify, or reshape

Prefer editorial changes in this order:

- remove points that add no new meaning
- merge overlapping claims
- clarify actor, action, condition, consequence, contrast, or limitation
- replace vague abstraction with concrete wording supported by the source
- vary sentence and paragraph rhythm according to meaning
- reduce formulaic transitions, summaries, and rhetorical emphasis

Do not add information merely to make the prose sound more human.

### 4. Revise with minimal semantic drift

When rewriting:

- preserve the intended claim unless the user asks for substantive reframing
- preserve uncertainty instead of making claims sound more confident
- preserve necessary domain terminology
- preserve the writer's evident level of formality and brand voice
- never invent facts, metrics, anecdotes, customers, quotes, evidence, or personal experience
- never turn a review into factual verification unless the user separately requests that task
- keep useful variation and imperfection when it supports a natural voice

If a proposed edit could materially alter meaning, prefer the safer wording or flag the assumption.

### 5. Match the requested output

#### Review only

Provide:

- a concise overall assessment
- a small number of high-impact findings
- the relevant excerpt or location
- why it feels weak or machine-like
- a concrete direction for improvement

#### Review plus rewrite

Provide:

- a concise diagnosis
- a revised version
- a short note on major editorial changes only when useful

#### Rewrite only

Return the revised text directly. Keep explanation minimal unless an assumption or meaning-sensitive change needs to be surfaced.

## Medium handling

For note, Notion, landing pages, business writing, and owned media, preserve the conventions of the medium rather than forcing one universal style. Load `references/medium-guidance.md` only when those conventions affect the edit.

## Quality gate

Before finishing, verify that:

- the revised text is easier to understand than the source
- the original meaning and factual content remain intact unless the user requested substantive changes
- no unsupported information was added
- redundant points were removed rather than merely paraphrased
- logical relationships are clear where they matter
- rhythm is more natural without becoming artificially casual
- the result still fits its audience, purpose, and medium

## Output style

Be specific and editorial. Avoid vague advice such as 「もっと自然に」「具体性を出す」「人間味を加える」 unless you show what should change and why.

When quoting problematic prose, use only the minimum excerpt needed to identify the issue. Prefer a few high-impact observations over exhaustive annotation.
