---
name: pokpok-setup
description: Connect the POKPOK brand-perception server after installing the POKPOK plugin. Use when the plugin was just installed, when a POKPOK tool answers that the connection is not signed in, or when the user asks how to connect POKPOK.
---

# Connecting POKPOK

The plugin registers one remote MCP server, `pokpok`, at
`https://auth.pokpok.ai/functions/v1/pokpok-mcp-v2/private`. It uses OAuth with dynamic client
registration; nothing has to be pasted.

1. The first call to any POKPOK tool answers `401` and Claude shows a **Connect** card. Ask the
   user to press it.
2. A POKPOK sign-in page opens (`pokpok.ai`). Existing customers sign in with email + password or
   Google/Apple; the consent page then shows **Allow**.
3. After **Allow**, the same tool call runs again by itself. No restart is needed.

What the sign-in unlocks: the person's own brand report ("How is our brand doing?" needs no brand
name), plus every public report. Reports the person has not bought stay closed, and the tools say so
instead of estimating — never fill the gap with a guess.

If the Connect card never appears and a tool returns text that says the connection is not signed in,
the server URL in `.mcp.json` is wrong: it must end in `/private`. The address without `/private`
answers everyone anonymously and never asks Claude to sign in.
