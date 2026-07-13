---
name: grill-to-brief-r
description: Interview the user about a feature idea — weighing UX, backend, and UI implications together for each decision — then close with a lens-tagged summary, capture any new knowledge, and produce a shareable context briefing. Use when the user wants to design or stress-test a feature and get the team on the same page, mentions "grill me on this feature", "grill to brief", "interview me about a feature", or wants cross-cutting UX/backend/UI coverage in one pass.
---

Interview the user about their feature idea. Treat the plan as a decision tree and resolve dependencies one branch at a time.

## Step 1 — Sync to the latest main

Before exploring or asking anything, pull the latest `main` (or `master`) so the interview reasons about the current version of the code, not a stale local copy. Check out the default branch and `git pull` first. If the working tree has uncommitted changes or the user is intentionally on a feature branch, don't clobber their work — tell them what you found and let them decide whether to stash, switch, or continue as-is.

## Step 2 — Run the lensed interview

For each question or decision point, consider three lenses: UX (flows, states, edge cases, user intent), backend (data model, API, business logic, constraints), and UI (layout, components, visual states, design-system alignment). Not every question touches all three. Apply only the lenses that are actually relevant to that specific decision, and say which lens or lenses a question belongs to when it's not obvious.

If a decision has consequences across more than one lens, surface those consequences together in the same question rather than splitting them into separate questions later. For example, "how should a failed save be handled" should raise the UX question (what does the user see), the backend question (does it retry, does it get logged, does it revert), and the UI question (what does the error state look like) as one connected decision, not three disconnected ones.

Explore the codebase before asking anything answerable by exploration. Propose a recommended answer for each question so the user can just confirm. Ask one question at a time. Summarize resolved decisions periodically, tagged by lens, so the user can see UX/backend/UI coverage building up as the interview progresses.

## Step 3 — Close the interview

When all questions are exhausted, present a final summary of every answer, grouped and tagged by lens (UX/backend/UI). Flag each answer so the user can see, at a glance, which decisions are settled and which surfaced new knowledge — insight that wasn't already recorded in the codebase or existing docs (a resolved ambiguity, an agreed constraint, a design decision, a non-obvious rationale).

If any new knowledge was created during the interview, ask: "Would you like to add these <items> to our knowledge base?" — where `<items>` names the specific new pieces of knowledge (e.g. "these 3 decisions", "this data-model constraint and error-handling flow"). If nothing new was created, skip this question.

The knowledge base is the "Buddy knowledge base" Notion page: https://app.notion.com/p/Buddy-knowledge-base-39ba86b45b848010931cc6f19685706c (page id `39ba86b45b848010931cc6f19685706c`). If the user says yes, append the confirmed new knowledge to that page via the Notion tools — each item written as a clear, self-contained entry (what was decided and the rationale), tagged by lens where relevant. Only write the items the user approved.

## Step 4 — Create a context briefing

After closing, offer to produce a context briefing that distills what was just scoped into a plain-language, shareable onboarding document for a teammate with zero prior context. Follow the logic of the `context-briefing-r` skill (https://github.com/remipjp/Skillset/tree/master/context-briefing-r): settle scope, audience, and jargon first; then write it in that skill's structure and voice — lead with the user and the problem, not the data model. The interview just completed is exactly the "already researched and scoped" input that skill expects, so draw on the resolved decisions rather than doing new discovery. If the `context-briefing-r` skill is available in the session, invoke it directly.

## When to use this vs. plain grilling

Reach for this lensed variant when the thing being designed spans product surface, data/logic, and visual design at once — i.e. a real feature. For plans that are purely architectural or purely visual, a single-lens interview is less noisy.
