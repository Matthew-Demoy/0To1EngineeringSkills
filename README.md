# One Shot Your MVPs
Agent skills I use to build full-stack applications that deliver value from day 1 when time constraints are tight and requirements are ambiguous.

Writing code is trivial. Shipping a full-stack MVP *correctly* when you have one day is unforgiving. You don't have cycles to iterate on features that miss the mark. These skills front-load the product and domain work so you can smoothly hand off your plan to agents and build the right thing on the first pass with product taste, technical execution, and time management all in sync. 

## Skills

| Skill | What it does | Why this is important |
| --- | --- | --- |
| `brief-to-product-context` | Read an engineering brief and extract only the product/domain signal — who the user is, their workflow, their pain, the job-to-be-done. Outputs a product researcher's summary, not a tech spec. | As engineers (and our agents) our initial tendency is to immediately start solutioning. This leads to false starts in design. By stripping out junk context about approach we can solve the problem as a true product person |
| `business-perspective` | Trace a top-down chain from how a company makes money down to whatever is being built, so every metric on the page can be justified in business terms. | When building an MVP, every feature has weight and is an investment in critical time. You don't have cycles if your turnaround is one day. By taking a business perspective we ensure that the feature we build meets the needed business purpose directly. This is where UX designs go from cool feature to actual value |
| `domain-knowledge-triage` | Given an unfamiliar domain, surface and sort its concepts, terms, and metrics into tiers so you know where to spend limited prep time. | I often find that most 0To1 opportunities are cross-functional, and are full of institutional knowledge. This skill skips a few hours of personal research that is needed to ensure the MVP accurately reflects the domain |
| `signal-to-prd` | Synthesize the session's research, notes, and interviews into a PRD plus a companion ADR — before any design or code. | This PRD will be what Claude design and Claude code work off of to build the product, condensing everything gathered so far |
| `to-issues` † | Break a plan, spec, or PRD into independently-grabbable issues on the project issue tracker using tracer-bullet vertical slices. | The ingenious insight of Matt Pocock's agentic workflow to build in vertical slices rather than in frontend, backend layers. This ensures functional test driven development is carried out by agents, increasing their capability to build the application autonomously. 
| `tdd` † | Test-driven development with a red-green-refactor loop and integration-style tests. | I find this is a good middle ground between telling an agent to build something directly and the plan mode loop which takes double the time in claude |
| `to-readme` | Draft a reviewer-ready README from the design-product-notes, codebase, and deploy URLs. Emits screenshot placeholders plus a capture checklist for the human. | Last step to package the MVP for developers and end users|

† Bundled from [Matt Pocock's skills](https://github.com/mattpocock/skills) under
the MIT License — see [NOTICE](./NOTICE).

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
