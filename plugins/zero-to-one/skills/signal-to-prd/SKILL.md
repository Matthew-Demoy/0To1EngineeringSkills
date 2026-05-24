---
name: signal-to-prd
description: Synthesizes product signals, research, interviews, and notes gathered in the current session into a PRD plus a companion ADR document. Use when turning product discovery, user research, or raw signals into a structured PRD before UX design or technical design begins. Triggers on "signal to PRD", "research to PRD", "turn this research into a PRD", "product signals", or when the user has gathered discovery material and wants a PRD before any code or design work starts.
---

# Signal to PRD

Synthesize all context from this session — conversations, interviews, notes, documents — into a PRD and companion ADR. Do NOT interview the user. There is no codebase to explore. Drive the output autonomously from what you already know.

Before drafting, read any upstream design-product-notes documents (brief, product context, business perspective, domain triage) — see **Output Location** for where they live — and incorporate their signal.

## Output Location

1. Check the project's `CLAUDE.md` for a documented design-product-notes folder (e.g. a line like "design notes live in `<path>`").
2. If found, write to `<that-folder>/signal-to-prd.md` (PRD) and `<that-folder>/adr.md` (ADR).
3. If not, write to `docs/signal-to-prd.md` and `docs/adr.md`. Create the directory if it doesn't exist.

No numeric prefixes. Overwrite the files if they already exist.

If the project has an issue tracker and a `ready-for-agent` triage label configured, also publish the PRD there. If no tracker is configured, the file is the source of truth.

## Process

1. **Identify anchors** — extract key terms, domain concepts, and architectural decisions from the signals. These become ADR entries.

2. **Sketch modules** — identify the major system areas to build. Look for deep modules: significant functionality behind a simple, stable, testable interface.

3. **Write the PRD** — use the template below. Write the file per **Output Location**; publish to the issue tracker if one is configured.

4. **Write the ADR** — write the file per **Output Location**. Cover domain vocabulary, naming conventions, and decisions that could be ambiguous between stakeholders.

## PRD Template

```
## Problem Statement
The problem the user is facing, from their perspective.

## Solution
The solution, from the user's perspective.

## User Stories
Numbered list. Format: As a <role>, I want <capability>, so that <benefit>.
Be exhaustive — cover edge cases, error states, and secondary actors.

## Implementation Decisions
- Modules to build and their interfaces
- Architectural decisions
- Schema changes
- API contracts
- Specific interactions

No file paths or code snippets unless a prototype produced a snippet that
encodes a decision better than prose (state machine, schema, type shape) —
inline it and note it came from a prototype.

## Testing Decisions
- What makes a good test for this system
- Which modules will be tested
- Prior art or patterns to follow

## Out of Scope
What is explicitly not being built in this PRD.

## Further Notes
Open questions, follow-on considerations.
```

## ADR Template

Produce as a separate document, published alongside the PRD.
Title: **Architecture Decision Record — Key Terms & Decisions**

For each significant term or decision:

```
## [Term or Decision Name]

**Status:** Accepted

**Context:**
Why this term or decision matters to the system.

**Decision:**
The precise definition or choice made.

**Consequences:**
What this means for how the system is built or understood.
```

Cover: domain vocabulary, naming conventions, major architectural choices, and any terms that could be ambiguous between stakeholders.
