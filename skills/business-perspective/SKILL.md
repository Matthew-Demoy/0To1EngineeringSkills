---
name: business-perspective
description: Trace a "breadcrumb trail" from how a company makes money down to whatever is being built — a raw assignment, a product context, or a specific feature — so every signal that will land on the page can be tied back to a revenue or cost driver. Use when starting work and you need to confirm the thing being built actually serves the business, or when asked things like "how does this connect to revenue?", "why does the business care about this?", or "/business-perspective".
---

# Business Perspective

Given a company plus whatever is being built (assignment, product context, or feature), trace a top-down chain from revenue down to the eventual screen-level signals. The output forces every metric on the page — known today or proposed later — to justify itself in business terms.

## Inputs

- **Company** — name plus a 1–2 sentence description of what they do. For real companies, web-search for the revenue model. For fictional or take-home companies, reason from the description plus the closest real-world analogue (and name the analogue).
- **What's being built** — accept any of:
  - **Assignment** — raw brief or prompt. Nothing scoped yet.
  - **Product context** — user, workflow, pain, job-to-be-done. Solution space still open.
  - **Feature** — concrete thing being shipped, with proposed UI signals already in mind.

Look for upstream design-product-notes documents (assignment, product context, prior business perspective) using the resolution rules in **Output Location** below. If neither a session-context input nor an upstream document is present, ask once before drafting. Do not invent.

## Output Location

1. Check the project's `CLAUDE.md` for a documented design-product-notes folder (e.g. a line like "design notes live in `<path>`").
2. If found, write to `<that-folder>/business-perspective.md`.
3. If not, write to `docs/business-perspective.md`. Create the directory if it doesn't exist.

No numeric prefix. Overwrite the file if it already exists.

## Output Structure

Use the section order below.

### 1. Revenue model
The top 2–3 revenue streams with rough share if known. For a bank: interchange, account fees, FX spread, lending net interest margin, etc.

### 2. Unit economics
What does a profitable customer look like? Customer acquisition cost, lifetime value, gross margin per account, and which operational costs scale linearly with customers (the dangerous ones).

### 3. Cost and risk drivers that threaten revenue
The 3–5 things that, if they go wrong, eat the margin. Examples: linear-scaling support cost, fraud losses, churn from bad customer experience, regulatory fines, compute spend.

### 4. Why this exists (the bridge)
One paragraph wiring the thing being built directly to a driver in section 3. Be concrete with numbers: *"Support cost is $X per ticket × Y tickets per week and growing linearly with accounts. This work targets that driver by …"* Adjust scope to the input level:
- **Assignment-level:** name the driver the assignment is implicitly aimed at, even if the prompt doesn't say so.
- **Product-context-level:** name the driver the user pain maps to.
- **Feature-level:** name the driver this specific feature moves.

### 5. Breadcrumb trail to the page
The deliverable. For every signal, metric, or control that will appear on the page, trace it back to revenue:

> **Signal:** `auto_send_rate`
> → drives **operational metric:** reviewer hours saved per week
> → drives **cost driver:** support cost per ticket
> → drives **business outcome:** gross margin per account
>
> **Signal:** `false_auto_send_rate`
> → drives **risk driver:** customer trust, complaint volume, regulatory exposure
> → drives **business outcome:** churn, fines, brand cost

If the input is an assignment or product context with no UI yet, *propose* the signals that ought to be on the page and trace each. Mark them `(proposed)` so they can be challenged later. Every signal — proposed or already-decided — must appear in this list. Anything that can't be traced is a candidate to cut.

### 6. Falsifiable business test
One sentence: *"If we shipped this and `<metric>` moved by `<amount>`, the business would `<measurable outcome>`."* If you can't write this sentence, the work isn't business-shaped yet — flag it instead of faking it.

## Rules

- Money first, mechanics second. Don't describe how it works; describe what it earns or saves.
- Numbers beat adjectives. "Drops 3-minute reviewer cost to 0 on 40% of tickets" beats "improves efficiency."
- No metric on the page without a breadcrumb. If a signal can't be traced back to revenue or risk, name it and ask whether to cut it.
- Never invent revenue figures for real companies. Flag what's assumed vs. what's sourced.
- For fictional or take-home companies, name the closest real-world analogue you're reasoning from (e.g. "modeled on Mercury and Brex unit economics") so assumptions are inspectable.