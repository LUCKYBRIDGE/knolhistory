# AGENTS.md

## Mission

Build `knolhistory` as a reliable history-learning web service. Optimize for factual accuracy, clear learning flow, maintainable code, and simple UX.

## Before changing code

Read the relevant parts of:

- `GOALS.md`
- `PLANS.md`
- `docs/PRODUCT_SPEC.md`
- `docs/ARCHITECTURE.md`
- `docs/HISTORY_CONTENT_STANDARD.md` for any historical/content change

Do not invent missing product requirements. If a decision is not settled, preserve it as an explicit open decision rather than silently hard-coding an assumption.

## Historical-content rules

- Never present an unverified historical claim as established fact.
- Distinguish **fact**, **interpretation**, **legend/tradition**, and **fictional reconstruction**.
- Preserve source metadata separately from learner-facing copy.
- Dates, names, places, titles, maps, clothing, tools, architecture, and social customs require the same verification standard as prose.
- When sources disagree, record the disagreement instead of flattening it into certainty.
- Prefer authoritative primary/official/academic sources over unsourced secondary summaries.
- For child-facing content, simplify language without changing the underlying meaning.

Use the repository skill `history-content-review` for substantial history-content work.

## Engineering rules

- Keep domain/content data separate from presentation components.
- Prefer the simplest architecture that satisfies current requirements.
- Do not add authentication, databases, analytics, or third-party dependencies without a concrete product need.
- Avoid duplicated state and duplicated content.
- Preserve accessibility: keyboard operation, semantic controls, readable contrast, meaningful labels, and touch-friendly targets.
- Design responsively; do not fix layouts to a single desktop viewport.
- Treat loading, empty, error, and unavailable states as first-class UI states.

## Change discipline

- Make the smallest coherent change that solves the requested problem.
- Do not rewrite unrelated working code.
- Update relevant docs when behavior, data shape, or architecture changes.
- Run the applicable verification defined by the project. If no automated checks exist yet, state that explicitly.
- For non-trivial code changes, use the `code-change-verification` skill before considering the task complete.

## Product decisions

Record durable decisions in `docs/PRODUCT_SPEC.md` or `docs/ARCHITECTURE.md`. Do not bury important decisions only in commit messages or chat history.
