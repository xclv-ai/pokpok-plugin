---
name: pokpok-setup
description: Connect the POKPOK brand-perception server after installing the POKPOK plugin. Use when the plugin was just installed, when the POKPOK server shows "needs authentication" or a tool answers that the connection is not signed in, or when the user asks how to connect POKPOK.
---

# Connecting POKPOK

The plugin registers one remote MCP server, `pokpok`, at
`https://auth.pokpok.ai/functions/v1/pokpok-mcp-v6/private`. It is POKPOK's signed-in address: every
tool is refused until the person has signed in once. It uses OAuth with dynamic client registration;
nothing has to be pasted.

**In Claude Code** (terminal, desktop app, IDE): the server shows "needs authentication" until the
person runs `/mcp`, picks `pokpok` and chooses **Authenticate**. A browser opens on `pokpok.ai/signin`.

**In claude.ai**: the first call to a POKPOK tool makes Claude show a **Connect** card. Ask the user to
press it. The same sign-in page opens.

Then, on both:
1. Sign in with the POKPOK **email and password**. Do not use the Google button from this window: it
   ends on the pokpok.ai home page instead of coming back. If that happens, close the tab and start the
   sign-in again; the session already exists.
2. The POKPOK permission page shows **Allow**. After it the tools work; no restart is needed.

What the sign-in gives: every public report, the person's own brand report ("How is our brand doing?"
needs no brand name), the reports their account ordered, and `pokpok_page` (a shareable page). Reports
the person has not bought stay closed, and the tools say so instead of estimating; never fill the gap
with a guess.

If POKPOK stops working after someone signed out on pokpok.ai: that sign-out also disconnected Claude.
Sign in again the same way.
