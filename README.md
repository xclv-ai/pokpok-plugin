# POKPOK for Claude

POKPOK measures how **people** and **AI answer engines** read a brand's web presence, and reports the
gap between the two. This plugin connects Claude to POKPOK's stored brand-perception reports and
teaches it the standard brand review.

## What you can ask

- "How is our brand doing?" — the verdict on your own brand (sign-in resolves which brand is yours)
- "Do AI engines describe our brand the way our own website does?" — the 17-marker alignment
- "What does POKPOK say about Georganics, and who does AI recommend instead?"
- "What should we fix first?" · "Where is our category crowded, and what does nobody claim?"
- "Put those findings into a POKPOK page I can send to my team."

## What's inside

| Part | Purpose |
|---|---|
| `.mcp.json` | the POKPOK remote MCP server (13 tools; 12 read-only, one that publishes a report page) |
| `skills/pokpok/` | when to use POKPOK, the review sequence, and the rules the answers follow |
| `SETUP.md` | how the OAuth connection works and what to do if the Connect card does not appear |

## Install

```
/plugin marketplace add xclv-ai/pokpok-plugin
/plugin install pokpok@pokpok-marketplace
```

Or add the server directly as a custom connector in Claude: **Customize → Connectors → Add custom
connector** with `https://auth.pokpok.ai/functions/v1/pokpok-mcp-v2/private`.

## Accounts and data

Public reports are readable by any signed-in POKPOK account. A customer's own report needs a
purchase or subscription at [pokpok.ai](https://pokpok.ai). Every number the tools return is a
stored measurement; the tools never estimate.

Privacy policy: https://pokpok.ai/legal/privacy · Terms: https://pokpok.ai/legal/licensing ·
Support: see the contact on pokpok.ai.

## Tools

`pokpok_search`, `pokpok_fetch`, `pokpok_diagnosis`, `pokpok_alignment`, `pokpok_truths`,
`pokpok_fixes`, `pokpok_ai_recommendations`, `pokpok_position`, `pokpok_white_space`,
`pokpok_corpus`, `pokpok_schema`, `pokpok_query` (read-only) · `pokpok_render_report` (writes a
shareable page).
