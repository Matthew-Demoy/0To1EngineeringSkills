---
name: domain-knowledge-triage
description: Given a domain or vertical, rapidly surfaces and sorts its concepts, terms, and metrics into four tiers so you know exactly where to spend limited prep time. Use when entering an unfamiliar domain for a take-home, interview, or new project — triggers on "triage this domain", "what do I need to know about X", "orient me on X", "domain knowledge for X", or when given a take-home brief in an unfamiliar vertical.
---

# Domain Knowledge Triage

Given a domain or vertical, synthesize a tiered glossary from training knowledge and session context. Do NOT ask the user to explain the domain.

## Process

1. Identify the domain (from session context, a job description, take-home brief, or a named product area).
2. Generate a comprehensive list of terms, metrics, standards, frameworks, and concepts — cast wide first.
3. Sort every item into exactly one of the four tiers using the triage rules below.
4. Produce the tiered glossary document.

## The Four Tiers

**Tier 1 — Baseline:** Any PM, engineer, or generalist entering this space is expected to know these. Blanking on one signals you didn't do basic homework. Appear in job descriptions, intro posts, and Wikipedia leads.

**Tier 2 — Adds Realism:** Signals you've worked in or near the vertical, not just read about it. Appear in practitioner conversations and product specs. Getting a few right meaningfully differentiates you.

**Tier 3 — Specialist Only:** Deep experts use these fluently; a generalist isn't expected to know them unprompted. Worth knowing they exist so you're not confused if they come up.

**Tier 4 — Rabbit Hole:** Highly specific, standards-body-level, or implementation-detail knowledge. Even specialists won't know all of these. Don't study these in a time-constrained context.

## Triage Rules

- Would a sharp generalist be embarrassed not to know this? → **Tier 1**
- Would knowing this make someone nod and say "ok, they've been around this space"? → **Tier 2**
- Is this something only someone who has done hands-on work would reach for? → **Tier 3**
- Is this a standards doc, academic sub-problem, or vendor-specific detail? → **Tier 4**

When in doubt between tiers, place in the higher (more accessible) tier.

## Output Format

```
# Domain Knowledge Triage: [Domain Name]

## Tier 1 — Know These Cold
**[Term]** — one sentence definition. Why it matters in ≤ 10 words.

## Tier 2 — Drop These In Conversation
**[Term]** — one sentence definition. What using this correctly signals.

## Tier 3 — Know They Exist
**[Term]** — one sentence definition. When/why a specialist would reach for this.

## Tier 4 — Rabbit Hole (Don't Study)
Brief list of names only — no definitions. One line noting the general category
(e.g. "IEEE standards," "EDA vendor tooling," "academic fault models").

## Prep Recommendation
2–3 sentences. Where to spend remaining prep time — name the tier boundary to
focus on and the single Tier 2 concept most likely to come up.
```

Scope: rapid orientation, not deep mastery. Confident fluency at Tier 1–2, informed awareness at Tier 3, Tier 4 exists only to mark the horizon.
