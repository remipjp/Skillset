---
name: context-briefing-r
description: Produce a plain-language, jargon-free briefing that gets a teammate with zero prior context up to speed on a feature or initiative, scoped to a chosen slice and audience. Use when the user wants to onboard a designer, engineer, PM, or stakeholder onto work already scoped in this session, or says things like "explain this to my designer", "brief my team", "write context for someone new", "get us on the same page".
---

Write a briefing that a smart teammate with **zero prior context** on this project can read once and understand what we're building and why. Assume the reader knows nothing about the product, the domain, the codebase, or the decisions made so far — but is intelligent and just needs the picture drawn for them.

This skill assumes the feature/initiative has **already been researched and scoped** earlier in the session (e.g. via `/grilling`, `/grill-to-brief-r`, `/research`, or Linear/codebase exploration). Its job is to distill that shared understanding into something shareable — not to do new discovery. If little context exists yet, gather it first (or tell the user), then brief.

## Before writing — settle three things

1. **Scope the slice.** A briefing that covers everything covers nothing. Confirm exactly which slice to explain (e.g. "truck only, not rail/barge"; "Phase 1"; "the data model, not the UI"). Everything outside the slice is named as out-of-scope, not explained.
2. **Know the audience.** A designer needs flows, states, and what the user sees. An engineer needs the data model, constraints, and edge cases. A PM/stakeholder needs goals, scope boundaries, and trade-offs. Ask if unclear, and lean the emphasis accordingly — but keep it plain-language regardless of audience.
3. **Strip the jargon.** No code identifiers, table names, class names, ticket IDs, or internal shorthand unless you immediately define them in ordinary words. If a domain term is unavoidable (e.g. "scale ticket", "Bill of Lading"), explain it in plain English the first time it appears.

## Structure to follow

Adapt the headings to the topic, but this shape is what works — it walks the reader from "what is this even" down to the specific work, then bounds it:

1. **What the product is** — a 30-second orientation for someone who's never seen it. Skip if the reader clearly knows the product.
2. **The world today** — how things currently work in the area being changed. Ground it in the real user and their real workflow, not the system's internals.
3. **The problem** — what's broken or missing, and *why it matters* (the business/user pain, the cost of the status quo). This is the "why now".
4. **What the real-world thing actually is** — for domain-heavy work, narrate the physical/real-world process the feature models (e.g. "picture a scrapyard that's sold a load of copper… the truck arrives, gets loaded, weighed…"). This is often the highest-value section for a newcomer and the easiest to skip by mistake.
5. **What we're building** — the concrete change, described as capabilities and captured data, not implementation.
6. **The key flows** — the handful of distinct paths a user can take, and why each exists. Call out the important forks explicitly.
7. **What we are NOT doing** — the out-of-scope list. This prevents the reader from over-scoping and is as important as the "what we're building" section.
8. **The one-sentence goal** — a single bolded sentence the whole team can repeat.
9. **A note on constraints/consistency** — anything that shapes the solution space (e.g. "reuse the existing patterns, don't reinvent"; a hard deadline; a platform limitation).

## Voice

- Concrete over abstract. "A truck arrives and gets weighed on a scale" beats "the system captures weight events."
- Short paragraphs, plain sentences. Favour a real scenario over a bulleted feature list where it aids understanding.
- Honest about scope and unknowns — flag what's still open, don't paper over it.
- Output as plain text/Markdown in the chat by default. Offer to save it to a repo doc or tailor it to another audience (design/eng/PM) or a shorter one-pager afterward.

## Anti-patterns

- Don't dump the decision log or the ticket list — that's a record, not a briefing.
- Don't lead with the data model or architecture; lead with the user and the problem.
- Don't explain the whole initiative when asked for one slice.
- Don't assume the reader will infer the "why" from the "what" — state it.
