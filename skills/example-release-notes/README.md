# Example: Release Notes skill

**Author:** _(example — this is the reference artifact)_
**Type:** Agent Skill

## What it does

Generates grouped, readable release notes from merged PRs between two git refs. Point it at a version range and it produces a clean changelog split into Features / Fixes / Internal.

## How I built it with Claude Code

- Started from a plain description of what I wanted ("turn merged PRs into release notes grouped by type").
- Had Claude draft the `SKILL.md`, then tested it on a real range in a repo.
- Iterated on the grouping rules until the output matched how we actually write release notes.

## How to use it

Drop the `release-notes/` folder into your project's skills directory (or a global skills location), then in Claude Code:

> "Draft release notes from v1.4.0 to HEAD"

## This is the bar

Your skill should be this concrete: a real task, a clear trigger, step-by-step instructions, and reusable by someone who didn't build it. Copy this folder's shape for your own submission.
