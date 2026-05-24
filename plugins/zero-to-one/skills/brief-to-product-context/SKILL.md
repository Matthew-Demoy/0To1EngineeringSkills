---
name: brief-to-product-context
description: Read a take-home engineering brief and extract only the product and domain signal from it — who the user is, their workflow, their pain, and the job-to-be-done. Outputs a product researcher's summary, not a technical spec. Use when the user pastes a take-home brief and asks to extract product context, understand the user problem, or strip out technical requirements.
---

# Brief to Product Context

Given a take-home engineering brief, extract only the product and domain signal. Output a concise document a product researcher would write — not a technical spec.

## Output Location

1. Check the project's `CLAUDE.md` for a documented design-product-notes folder (e.g. a line like "design notes live in `<path>`").
2. If found, write to `<that-folder>/brief-to-product-context.md`.
3. If not, write to `docs/brief-to-product-context.md`. Create the directory if it doesn't exist.

No numeric prefix. Overwrite the file if it already exists.

## Output Structure

**User Profile** — who is the primary user? Role, context, level of sophistication.

**Daily Workflow** — what does their day look like today, before this tool exists? Be specific and concrete.

**Pain** — what friction, failure mode, or missing capability drives them to seek a solution?

**Job to Be Done** — complete this sentence: *"When [situation], I want to [motivation], so I can [outcome]."*

**Stated User Requirements** *(only if the brief contains explicit descriptions of what the user should see or do)* — preserve these verbatim, exactly as written. No paraphrasing.

## Rules

- Strip all of the following completely — do not summarize or reference them:
  - Technical stack, language, framework, or infra choices
  - Implementation constraints or architecture guidance
  - Evaluation criteria or grading rubrics
  - Submission instructions
- Do not editorialize. Do not add anything not implied by the brief.
- If the brief is thin on product signal, say so — don't invent a persona.
- Stated User Requirements must be verbatim lifts, not rewrites.

## Example trigger

User pastes a job brief or take-home prompt and says any of:
- "extract the product context from this"
- "what's the user problem here?"
- "strip out the tech stuff, just give me the product signal"
- or uses `/brief-to-product-context`
