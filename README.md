# 0 To 1 Engineering Skills

A small collection of [Claude Code](https://claude.com/claude-code) agent skills
for taking a product from **zero to one** — going from a raw brief to a shipped MVP when time is short and requirements are ambiguous.

## Skills

| Skill | What it does | Why this is important |
| --- | --- | --- |
| `brief-to-product-context` | Read an engineering brief and extract only the product/domain signal — who the user is, their workflow, their pain, the job-to-be-done. Outputs a product researcher's summary, not a tech spec. | As engineers (and our agents) our initial tendency is to immediatley solutioning. This leads to false start in design. By stripping out junk context about approach we can solve the problem as a true product person |
| `business-perspective` | Trace a top-down chain from how a company makes money down to whatever is being built, so every metric on the page can be justified in business terms. | When building an MVP, every feature has weight and is an investment in critical time. You don't have cycles if your turnaround is one day. By taking a business perspective we ensure that the feature we build meets the needed business purpose directly. This is where UX designs go from cool feature to actual value |
| `domain-knowledge-triage` | Given an unfamiliar domain, surface and sort its concepts, terms, and metrics into tiers so you know where to spend limited prep time. | I often find that most 0To1 oppurtunities are cross-functional, and are full of insititutional knowledge. This skills skips a few hours of personal research that is needed to ensure the MVP accuratley reflects the domain |
| `signal-to-prd` | Synthesize the session's research, notes, and interviews into a PRD plus a companion ADR — before any design or code. | This PRD will be what claude design and claude code work off of to build the product, it condenses every thing gather up to the point |
| `to-issues` † | Break a plan, spec, or PRD into independently-grabbable issues on the project issue tracker using tracer-bullet vertical slices. | The ingenious insight of Matt Pococks agentic workflow to build in vertical slices rather than in frontend, backend layers. This ensure functional test driven development is carried out by agents, increasing their capability to build the application automonomosuly. 
| `tdd` † | Test-driven development with a red-green-refactor loop and integration-style tests. | I find this is a good middle ground between telling an agent to build something directly and the plan mode loop which takes double the time in claude |
| `to-readme` | Draft a reviewer-ready README from the design-product-notes, codebase, and deploy URLs. Emits screenshot placeholders plus a capture checklist for the human. | Last step to package the MVP for developers and end users|

† Bundled from [Matt Pocock's skills](https://github.com/mattpocock/skills) under
the MIT License — see [NOTICE](./NOTICE).

## Install

### Option A — Plugin marketplace (recommended, supports updates)

In Claude Code:

```
/plugin marketplace add Matthew-Demoy/0To1EngineeringSkills
/plugin install zero-to-one@0to1-engineering-skills
```

Pull updates later with `/plugin marketplace update 0to1-engineering-skills`.

### Option B — Manual (copy the folders)

```bash
git clone https://github.com/Matthew-Demoy/0To1EngineeringSkills.git
cp -R 0To1EngineeringSkills/plugins/zero-to-one/skills/* ~/.claude/skills/
```

Then restart Claude Code so it picks up the new skills.

## A note on `to-issues`

`to-issues` expects a project issue tracker and a triage-label vocabulary to be
set up. Without them it can't publish. See the upstream
[mattpocock/skills](https://github.com/mattpocock/skills) repo for the companion
setup skill.

## License

MIT — see [LICENSE](./LICENSE).
