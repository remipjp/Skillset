---
name: grill-me-lensed
description: Interview the user about a feature idea, weighing UX, backend, and UI implications together for each decision rather than in sequential phases. Use when the user wants to design or stress-test a feature, mentions "grill me on this feature", "interview me about a feature", or wants cross-cutting UX/backend/UI coverage in one pass.
---

Interview the user about their feature idea. Treat the plan as a decision tree and resolve dependencies one branch at a time.

For each question or decision point, consider three lenses: UX (flows, states, edge cases, user intent), backend (data model, API, business logic, constraints), and UI (layout, components, visual states, design-system alignment). Not every question touches all three. Apply only the lenses that are actually relevant to that specific decision, and say which lens or lenses a question belongs to when it's not obvious.

If a decision has consequences across more than one lens, surface those consequences together in the same question rather than splitting them into separate questions later. For example, "how should a failed save be handled" should raise the UX question (what does the user see), the backend question (does it retry, does it get logged, does it revert), and the UI question (what does the error state look like) as one connected decision, not three disconnected ones.

Explore the codebase before asking anything answerable by exploration. Propose a recommended answer for each question so the user can just confirm. Ask one question at a time. Summarize resolved decisions periodically, tagged by lens, so the user can see UX/backend/UI coverage building up as the interview progresses.

## Closing the interview

Once all questions are exhausted, present a final summary of every answer, grouped and tagged by lens (UX/backend/UI). Flag each answer so the user can see, at a glance, which decisions are settled and which surfaced new knowledge — insight that wasn't already recorded in the codebase or existing docs (a resolved ambiguity, an agreed constraint, a design decision, a non-obvious rationale).

If any new knowledge was created during the interview, make the last question: "Would you like to add these <items> to our knowledge base?" — where `<items>` names the specific new pieces of knowledge (e.g. "these 3 decisions", "this data-model constraint and error-handling flow"). If nothing new was created, skip this question and just close with the summary.

The knowledge base is the "Buddy knowledge base" Notion page: https://app.notion.com/p/Buddy-knowledge-base-39ba86b45b848010931cc6f19685706c (page id `39ba86b45b848010931cc6f19685706c`). If the user says yes, append the confirmed new knowledge to that page via the Notion tools — each item written as a clear, self-contained entry (what was decided and the rationale), tagged by lens where relevant. Only write the items the user approved.

## When to use this vs. plain grilling

Reach for this lensed variant when the thing being designed spans product surface, data/logic, and visual design at once — i.e. a real feature. For plans that are purely architectural or purely visual, a single-lens interview is less noisy.
