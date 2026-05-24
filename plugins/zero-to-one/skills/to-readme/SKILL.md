---
name: to-readme
description: Draft a presentable project README from the design-product-notes, the codebase, and the deploy URLs — sized for a take-home reviewer. Use when finishing a take-home, preparing to submit, or asked to "write the readme", "polish the readme", "presentable readme", or "/to-readme".
---

# To README

Produce a reviewer-ready `README.md` for the project. This is the artifact a take-home reviewer opens first — it must communicate the user problem, the demo, and how to run it within the first screen.

## Output Location

Overwrites the project's `README.md` at the repo root. The template's scaffold README is explicitly meant to be replaced; do not preserve scaffold content unless the user has clearly customized it.

If `README.md` already contains content that does not look like the scaffold (project-specific tagline, custom sections, real screenshots), stop and ask before overwriting.

## Process

1. **Read the WHY** — read every file in `docs/design-product-notes/` (the design-product-notes folder per `CLAUDE.md`, or `docs/` as fallback). Pull the user problem from `brief-to-product-context.md`, the revenue/cost framing from `business-perspective.md`, and the scoped solution from `signal-to-prd.md`.

2. **Read the HOW** — read `package.json`, `pyproject.toml`, `Makefile`, and `.env.example` files to determine setup commands and required env vars. Read the project's `CLAUDE.md` stack section if present.

3. **Gather links** — ask the user (in one batched question) for:
   - Live demo URL (e.g. Vercel preview)
   - Repo URL (or detect from `git remote get-url origin`)
   - Loom/video URL (optional)

   If any are not yet available, leave a `TODO:` placeholder rather than inventing.

4. **Plan screenshots** — based on the PRD's user stories, pick 2–4 screens that demonstrate the golden path. Emit a **Capture Checklist** at the end of the skill output (not inside the README) telling the human exactly which screens to capture and where to save them.

5. **Write the README** — overwrite `README.md` using the template below.

## README Template

```markdown
# {{Project Name}}

{{One-sentence tagline derived from the job-to-be-done in brief-to-product-context.md}}

**Demo:** {{live URL or TODO}} · **Loom:** {{video URL or TODO}} · **Repo:** {{repo URL}}

---

## The problem

{{2–3 sentences from brief-to-product-context.md — who the user is, what hurts today, what they're trying to accomplish.}}

## What I built

{{3–5 bullets describing the shipped solution at user-visible level. Pulled from signal-to-prd.md's Solution + User Stories sections.}}

## Screenshots

![{{first screen description}}](docs/screenshots/01-{{slug}}.png)

![{{second screen description}}](docs/screenshots/02-{{slug}}.png)

{{Add more if the golden path needs them. Max 4.}}

## Run it locally

```sh
{{setup commands from Makefile / package.json — e.g. make install && make dev}}
```

Open {{local URL, e.g. http://localhost:3000}}.

Env vars: see `{{path/to/.env.example}}`.

## Stack

- **Web:** {{from package.json / CLAUDE.md}}
- **API:** {{from pyproject.toml / CLAUDE.md}}
- **DB:** {{from docker-compose.yml or CLAUDE.md}}
- **Deploy:** {{Vercel/Railway/etc.}}

## Design notes

{{3 bullets covering the most interesting product or technical decisions. Pulled from business-perspective.md (the business test) and signal-to-prd.md (Implementation Decisions). Each bullet names a tradeoff, not just a fact.}}

## What I'd do with more time

{{3 bullets — pulled from signal-to-prd.md's "Out of Scope" and "Further Notes" sections. Be concrete: "X would unlock Y," not "more polish."}}
```

## Capture Checklist (printed to the user, NOT in the README)

After writing the README, print to the user a checklist like:

```
Capture these screenshots:

  [ ] docs/screenshots/01-{{slug}}.png — {{describe what to capture, e.g. "Main dashboard with at least 3 entries seeded"}}
  [ ] docs/screenshots/02-{{slug}}.png — {{describe second view}}

Optional:
  [ ] Record a 2–3 minute Loom walking through the golden path
  [ ] Update README placeholders: {{list any TODOs left in the README}}
```

Use `mkdir -p docs/screenshots` if the directory doesn't exist.

## Rules

- **No invented content.** If a design-product-notes file is empty or missing, leave that section as a `TODO:` rather than guessing. Tell the user which files were empty.
- **No marketing voice.** Reviewer reads code, not copy. Tone is direct, factual, low-adjective.
- **Setup commands must match reality.** Read the Makefile and package.json — don't recite a generic `npm install && npm run dev` if the project uses `make dev`.
- **Demo URL goes first.** A reviewer with five minutes opens the demo before they read anything else. Put it above the fold.
- **Cap screenshots at 4.** More dilutes the golden path. If the product has many views, pick the ones that demonstrate the user story.
- **No domain-specific acronyms** if the consuming project's CLAUDE.md forbids them (check before drafting). Spell out PRD, ADR, etc.
