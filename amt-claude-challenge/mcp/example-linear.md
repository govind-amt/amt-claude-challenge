# Example: Linear MCP integration

**Author:** _(example — this is the reference artifact)_
**Type:** MCP integration

## What it does

Connects Claude Code to Linear so you can read and update issues without leaving the terminal — "what's assigned to me this cycle", "move AMT-142 to In Review", "create an issue for this bug".

## Setup

Add the Linear MCP server to your Claude Code config. In your project's `.mcp.json`:

```json
{
  "mcpServers": {
    "linear": {
      "type": "http",
      "url": "https://mcp.linear.app/mcp"
    }
  }
}
```

Then authenticate when Claude Code prompts you on first use.

## Example prompts once connected

- "List my open Linear issues in the current cycle."
- "Create a Linear issue: 'Fix flaky auth test', assign to me, tag it bug."
- "What's the status of AMT-142?"

## Why this is useful for AMT

We already track work in Linear. Wiring it into Claude Code means issue triage, status updates, and creating tickets from things you spot mid-code all happen in one place — no context switch to the browser.

## Making it your own submission

An MCP submission should show a **real, working integration** with setup steps someone else can follow, plus 2–3 example prompts that prove it works. Pick a service AMT actually uses (Linear, GitHub, Sentry, a database) and document the wire-up.
