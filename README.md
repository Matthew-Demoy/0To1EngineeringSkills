# One Shot Your MVPs
Agent skills I use to build full-stack applications that deliver value from day 1 when time constraints are tight and requirements are ambiguous.

Writing code is trivial. Shipping a full-stack MVP *correctly* when you have one day is unforgiving. You don't have cycles to iterate on features that miss the mark. These skills front-load the product and domain work so you can smoothly hand off your plan to agents and build the right thing on the first pass with product taste, technical execution, and time management all in sync.

One shotting an MVP isn't just about the day 1 milestone. It sets up for product-market-fit cleanly. Your codebase stays free of dead schemas and outdated context that accumulate through iteration. When you move to the next phase, you're building on a solid foundation instead of refactoring a prototype.

## Skills

**[brief-to-product-context](/skills/brief-to-product-context/SKILL.md)** — Read intake documentation and extract only the product/domain signal—who the user is, their workflow, their pain, the job-to-be-done. Strips out solutioning so you solve the problem as a true product person.

**[business-perspective](/skills/business-perspective/SKILL.md)** — Trace a top-down chain from how a company makes money down to whatever is being built. Every feature you ship is an investment in critical time; this skill ensures the feature meets the needed business purpose directly.

**[domain-knowledge-triage](/skills/domain-knowledge-triage/SKILL.md)** — Given an unfamiliar domain, surface and sort its concepts, terms, and metrics into tiers so you know where to spend limited prep time. Skips hours of research that's needed to ensure the MVP accurately addresses the domain.

**[signal-to-prd](/skills/signal-to-prd/SKILL.md)** — Synthesize the session's research, notes, and interviews into a PRD plus a companion ADR—before any design or code. Condenses everything gathered so your agent can build cleanly from day 1.

**[to-issues](/skills/to-issues/SKILL.md)** † — Break a plan, spec, or PRD into independently-grabbable issues using tracer-bullet vertical slices. Enables functional test-driven development so agents build the application autonomously (Kudos to Matt Pocock for this ingenious approach).

**[tdd](/skills/tdd/SKILL.md)** † — Test-driven development with red-green-refactor loops and integration-style tests. Good middle ground between direct building and plan mode.

**[to-readme](/skills/to-readme/SKILL.md)** — Draft a reviewer-ready README from the design-product-notes, codebase, and deploy URLs. Last step to package the MVP for developers and users.

† Bundled from [Matt Pocock's skills](https://github.com/mattpocock/skills) under the MIT License — see [NOTICE](./NOTICE).

## Install

### Option A — skills.sh (recommended, works with Claude Code, Cursor, Codex)

```bash
npx skills@latest add Matthew-Demoy/0To1EngineeringSkills
```

Pick the skills you want and which agents to install them on.

### Option B — Manual (copy the folders)

```bash
git clone https://github.com/Matthew-Demoy/0To1EngineeringSkills.git
cp -R 0To1EngineeringSkills/skills/* ~/.claude/skills/
```

Then restart your agent so it picks up the new skills.

## A note on `to-issues`

`to-issues` expects a project issue tracker and a triage-label vocabulary to be
set up. Without them it can't publish. See the upstream
[mattpocock/skills](https://github.com/mattpocock/skills) repo for the companion
setup skill.

## License

MIT — see [LICENSE](./LICENSE).
