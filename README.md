# AI Engagement Team

Five Claude skills that take a small firm from a first conversation to working AI tools that staff actually use.

Built by Colette Kenney, P.Eng., IMCK Corp. Portfolio: [imck.ca/portfolio](https://imck.ca/portfolio/)

---

## What this is

Most small firms ask for a feature: "Can AI write our client emails?" The feature is rarely the real problem. These skills run a full engagement in five stages. Each stage produces a written document that the next stage starts from.

| # | Skill | What it does | What it produces |
|---|---|---|---|
| 1 | [Discovery Lead](skills/discovery-lead/SKILL.md) | Runs the discovery call and finds the workflow problem behind the request | Discovery Brief, plus a follow-up email for any missing numbers |
| 2 | [Value Analyst](skills/value-analyst/SKILL.md) | Puts a yearly cost on each problem, checks the build is possible, chooses the smallest fix and prices it on value | One-page proposal with pass rates |
| 3 | [Prototype Builder](skills/prototype-builder/SKILL.md) | Builds the fix and tests it against pass rates written before testing | Build Record with the full test log |
| 4 | [Trainer](skills/trainer/SKILL.md) | Sets up the workspace, writes usage rules and plans short training on the team's own work | Training Plan, usage rules, cheat sheets |
| 5 | [Delivery Lead](skills/delivery-lead/SKILL.md) | Handover, monthly value reports, scope changes and the case study | Handover summary and value reports |

## How the skills work

- **Every number has a source.** Each figure is marked as stated by the client, estimated, or assumed.
- **Check existing software first.** If a tool the client already pays for solves the problem, set it up and skip the AI build.
- **Tests are written before testing.** Each pass rate is checked to make sure it can actually be met.
- **AI drafts. A qualified person decides.** Nothing goes to a client without a person reviewing it.
- **Plain language throughout.**

## Worked example

[examples/prairie-ledger-cpa](examples/prairie-ledger-cpa/) is a complete practice engagement for a made-up 14-person accounting firm. It includes the Discovery Brief, the proposal, three prototypes with their test logs (including the rounds that failed), the Build Record and the Training Plan.

**Prairie Ledger CPA is fictional. All names, records and numbers in the example are made up.**

Running this example end to end found gaps in the skills, which were then fixed:

- The Discovery Lead now asks which software features the client already uses, and collects cost and billing rates for every role.
- The Value Analyst now checks the build is ready before pricing, and checks that every pass rate can be met.
- The Prototype Builder now runs a readiness check before building anything.

## Using the skills

Each folder in `skills/` is one Claude skill, with its instructions in `SKILL.md`. To use them, add each folder to Claude as a custom skill, then start with the Discovery Lead. Each skill tells you what to paste into the next one.

## Ownership

Copyright 2026 IMCK Corp. See [LICENSE](LICENSE.md).
