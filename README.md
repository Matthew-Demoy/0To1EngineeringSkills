# 0To1EngineeringSkills

A small collection of [Claude Code](https://claude.com/claude-code) agent skills
for taking a product from **zero to one** — going from a raw brief to a shipped
feature. Built around a take-home / new-project workflow.

## Skills

| Skill | What it does |
| --- | --- |
| `brief-to-product-context` | Read an engineering brief and extract only the product/domain signal — who the user is, their workflow, their pain, the job-to-be-done. Outputs a product researcher's summary, not a tech spec. |
| `domain-knowledge-triage` | Given an unfamiliar domain, surface and sort its concepts, terms, and metrics into tiers so you know where to spend limited prep time. |
| `signal-to-prd` | Synthesize the session's research, notes, and interviews into a PRD plus a companion ADR — before any design or code. |
| `tdd` † | Test-driven development with a red-green-refactor loop and integration-style tests. |
| `to-prd` † | Turn the current conversation into a PRD and publish it to the project issue tracker. |

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

## A note on `to-prd`

`to-prd` expects a project issue tracker and a triage-label vocabulary to be set
up. Without them it will degrade to producing a standalone PRD. See the upstream
[mattpocock/skills](https://github.com/mattpocock/skills) repo for the companion
setup skill.

## License

MIT — see [LICENSE](./LICENSE).
