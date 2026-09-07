---
name: release-notes
description: Generate clean release notes from merged pull requests between two git refs. Use when the user asks to draft release notes, a changelog entry, or a summary of what shipped between two tags/branches for a Node.js/React monorepo.
---

# Release Notes Generator

Turn a range of merged PRs into readable, grouped release notes.

## When to use this

The user wants release notes or a changelog for what shipped between two points in git history — e.g. "draft release notes from v1.4.0 to HEAD" or "what changed since last Friday's deploy".

## How to do it

1. **Get the merge commits in range.** Run:
   ```
   git log <from-ref>..<to-ref> --merges --pretty=format:"%s (%h)"
   ```
   If the user gives dates instead of refs, use `--since` / `--until`.

2. **Pull PR titles.** Each merge subject usually contains the PR title and number. Extract the human-readable title, drop the "Merge pull request #NNN from branch" boilerplate.

3. **Group by type.** Sort entries into these buckets based on conventional-commit prefixes or keywords in the title:
   - **Features** (`feat`, "add", "new")
   - **Fixes** (`fix`, "bug", "resolve")
   - **Performance** (`perf`)
   - **Chores / internal** (`chore`, `refactor`, `test`, `ci`, "bump", "deps")

4. **Write the notes.** Use this format:

   ```markdown
   ## <version or date>

   ### Features
   - <title> (#PR)

   ### Fixes
   - <title> (#PR)

   ### Internal
   - <title> (#PR)
   ```

5. **Keep it human.** Rewrite terse commit titles into plain language. "fix npe in auth mw" becomes "Fixed a crash in the auth middleware". Drop anything purely mechanical (version bumps) unless the user wants a full log.

## Notes

- If a range has no merges (squash-merge workflow), fall back to `git log <from>..<to> --pretty=format:"%s (%h)"` and filter out commits that look like internal noise.
- Ask the user for the version number if they didn't give one; don't invent it.
