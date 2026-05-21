---
name: signal-to-prd
description: Synthesizes product signals, research, interviews, and notes gathered in the current session into a PRD plus a companion ADR document. Use when turning product discovery, user research, or raw signals into a structured PRD before UX design or technical design begins. Triggers on "signal to PRD", "research to PRD", "turn this research into a PRD", "product signals", or when the user has gathered discovery material and wants a PRD before any code or design work starts.
---

# Signal to PRD

Synthesize all context from this session — conversations, interviews, notes, documents — into a PRD and companion ADR. Do NOT interview the user. There is no codebase to explore. Drive the output autonomously from what you already know.

## Process

1. **Identify anchors** — extract key terms, domain concepts, and architectural decisions from the signals. These become ADR entries.

2. **Sketch modules** — identify the major system areas to build. Look for deep modules: significant functionality behind a simple, stable, testable interface.

3. **Write the PRD** — use the template below. Publish to the project issue tracker with the `ready-for-agent` triage label.

4. **Write the ADR** — publish as a separate document alongside the PRD. Cover domain vocabulary, naming conventions, and decisions that could be ambiguous between stakeholders.

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
