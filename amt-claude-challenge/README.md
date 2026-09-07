# AMT Claude Upskilling Challenge

A two-week challenge to level up how AMT developers use Claude. Complete a course, build something real, and add it to this shared library.

By the end, this repo becomes an AMT-wide collection of reusable Claude Code assets — skills, subagents, and MCP integrations — that anyone in the org can pull from.

---

## Two tracks

Pick the track that matches your current setup.

### Track A — Claude Code (Pro)
For developers already using Claude Code.

1. Complete **Claude Code in Action** on [Claude Academy](https://www.anthropic.com/learn).
2. Build one **advanced artifact** and open a PR adding it to this repo:
   - an **agent skill** (`skills/your-name-skill/`), or
   - a **subagent** (`subagents/`), or
   - an **MCP integration** (`mcp/`).
3. Include a short README with your artifact explaining what it does and how you built it.

### Track B — claude.ai web (free)
For developers currently using only the Claude web app. No subscription required.

1. Complete **Claude 101** and **AI Fluency: Framework & Foundations** on [Claude Academy](https://www.anthropic.com/learn). Both are free — sign up with your email.
2. Write a short **before/after** example of a real work task you now do better with Claude, and open a PR adding it to `submissions/your-name/`.

---

## How to submit

Every participant submits three things:

1. **Course completion badge** — screenshot or link, dropped in your submission folder.
2. **LinkedIn post** — post your completion, tag **AMT**, link it in your PR description.
3. **Your artifact** — the PR itself (Track A: skill/subagent/MCP; Track B: before/after writeup).

Open a pull request into `main`. A reviewer will check it and merge.

**Deadline:** _<set date — 2 weeks from launch>_

---

## Ground rule: make it reusable

Don't build a throwaway toy. Build something the next person can actually use.

- Good: a "generate release notes from merged PRs" subagent, a "lint our Node monorepo" skill.
- Not good: a skill that prints "hello world".

The whole point is that after the challenge, we have a real internal toolbox.

---

## Repo layout

```
amt-claude-challenge/
├── README.md                    ← you are here
├── skills/                      ← agent skills (one folder each)
│   └── example-release-notes/   ← worked example, copy this shape
├── subagents/                   ← subagent definitions
│   └── example-pr-reviewer.md   ← worked example
├── mcp/                         ← MCP integration examples
│   └── example-linear.md        ← worked example
└── submissions/
    └── _template/               ← copy this to submissions/your-name/
```

---

## Getting help

Stuck on setup or not sure what to build? Ask in the challenge channel. Setup help (installing Claude Code, first CLAUDE.md) counts as helping others — pitch in.
