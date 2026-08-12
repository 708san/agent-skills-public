# Human Writing Review Eval Cases

## Positive triggers

### Case 1 — review and rewrite
Prompt: `この記事、AIっぽく見えるところを指摘して自然に直して。`
Expected: review highest-impact issues, then provide a revision while preserving meaning and supplied facts.

### Case 2 — rewrite only
Prompt: `このNotion文章を、人が書いた感じに自然に直して。内容は変えないで。`
Expected: rewrite directly; preserve substance; use medium guidance only if useful.

### Case 3 — landing page
Prompt: `このLPの文章が抽象的でAIっぽいので改善して。`
Expected: improve specificity and rhythm without inventing proof, customer results, or conversion claims.

### Case 4 — business writing
Prompt: `この社内文書、回りくどくてAIっぽい。読みやすくして。`
Expected: clarify actor, request/decision, reason, and next action when present; do not add missing operational facts.

### Case 5 — owned media
Prompt: `この記事のAIっぽい言い回しと冗長なところをレビューして。`
Expected: diagnose a small number of high-impact issues; no unrelated SEO or fact-checking work.

## Negative / near-miss triggers

### Case 6 — SEO strategy
Prompt: `この記事で上位表示するためのSEOキーワード戦略を作って。`
Expected: do not treat as human-writing-review; route to a different capability.

### Case 7 — fact-checking
Prompt: `この記事の数字と引用が正しいか検証して。`
Expected: do not perform as this Skill; factual verification is outside scope.

### Case 8 — article planning
Prompt: `生成AIについての記事構成をゼロから企画して。`
Expected: do not treat as human-writing-review unless the user later supplies prose for review/revision.

### Case 9 — fake human errors
Prompt: `AI判定を避けるためにわざと誤字や口癖を入れて。`
Expected: do not simulate humanness with arbitrary errors; offer natural editorial revision instead.

## Known-good behavior

- Review and revision can occur in one workflow.
- Review-only requests do not force a rewrite.
- Rewrite-only requests do not force a long diagnostic report.
- The result may vary sentence rhythm but remains appropriate to the medium.
- Facts, claims, uncertainty, terminology, and intended meaning remain unchanged unless the user explicitly requests substantive changes.
- References are loaded only when needed.

## Known-bad behavior

- Exhaustively listing every pattern regardless of impact.
- Inventing facts, examples, metrics, quotes, or customer evidence to make prose feel human.
- Adding typos, slang, or fake hesitation merely to evade AI-like style.
- Expanding the task into SEO, LLMO, fact-checking, article planning, or research.
- Moving so much judgment into references that the core workflow cannot execute without loading them.

## Regression expectations

- note, Notion, landing pages, business writing, and owned-media prose remain supported.
- The core SKILL.md remains sufficient for straightforward review or rewrite requests.
- Detailed pattern diagnosis can use `references/review-patterns.md` conditionally.
- Medium-specific adaptation can use `references/medium-guidance.md` conditionally.
- No scripts or assets are required for correct execution.
