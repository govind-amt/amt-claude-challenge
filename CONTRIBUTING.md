# Contributing — how to submit and how PRs get merged

This is the step-by-step flow for the challenge. Participants follow "Submitting". Reviewers follow "Reviewing & merging".

---

## Submitting (participants)

### 1. Create your branch

```bash
git checkout main
git pull
git checkout -b submission/<your-name>
```

### 2. Add your work

**Track A — Claude Code**
- Put your artifact in the right folder:
  - a skill → `skills/<your-name>-<skill>/` with a `SKILL.md` and a short `README.md`
  - a subagent → `subagents/<your-name>-<agent>.md`
  - an MCP integration → `mcp/<your-name>-<service>.md`
- Copy `submissions/_template/` to `submissions/<your-name>/` and fill in the README (track, course, badge, LinkedIn link, and a link to the artifact you added above).

**Track B — Web**
- Copy `submissions/_template/` to `submissions/<your-name>/` and fill in the before/after writeup plus your badge and LinkedIn link.

### 3. Drop in your badge

Save your course completion badge screenshot into `submissions/<your-name>/` and reference it in your README.

### 4. Open the PR

```bash
git add -A
git commit -m "Submission: <your-name>"
git push -u origin submission/<your-name>
gh pr create --fill
```

In the PR description include:
- [ ] Which track (A or B)
- [ ] Course(s) completed
- [ ] Link to your LinkedIn post (tagging AMT)
- [ ] What your artifact does (Track A) / link to your writeup (Track B)

---

## The bar for a merge

A PR gets merged when it has all three:

1. **Course done** — badge present in your submission folder.
2. **LinkedIn post** — linked in the PR, tagging AMT.
3. **Artifact** — Track A: a working, reusable skill/subagent/MCP with a short README. Track B: a concrete before/after writeup of real work.

"Reusable" means someone else could pick it up and use it. A hello-world skill doesn't clear the bar; a "generate release notes" skill does.

---

## Reviewing & merging (reviewers)

1. **Check the three requirements** above are all present.
2. **Sanity-check the artifact** — for Track A, does the skill/subagent/MCP actually make sense and work? For Track B, is the before/after real and specific?
3. **Request changes** if something's missing — point to which of the three is incomplete. Keep it quick; this is upskilling, not gatekeeping.
4. **Merge** into `main` once it clears.
5. **Update the leaderboard** (below) in the same sitting so standings stay current.

### Updating the leaderboard on merge

Edit `leaderboard.json`. Find the participant (add them if they're new) and set the milestones they've now met:

```json
{
  "name": "govind",
  "track": "A",
  "course": true,
  "linkedin": true,
  "artifact": true,
  "completedDate": "2026-09-15"
}
```

- Flip `course` / `linkedin` / `artifact` to `true` as each is confirmed.
- Set `completedDate` (YYYY-MM-DD) only once **all three** are true.
- Commit directly to `main`:
  ```bash
  git add leaderboard.json
  git commit -m "Leaderboard: <name> completed"
  git push
  ```

The published page (GitHub Pages) picks up the change on next load. Everyone who reaches 100 shares rank #1 — no single winner unless only one person finishes.

---

## Questions

Ask in the challenge channel. Helping a teammate get unstuck (Claude Code install, first CLAUDE.md, MCP auth) is encouraged — that's the point.
