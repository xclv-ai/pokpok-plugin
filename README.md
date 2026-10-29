# POKPOK for Claude

POKPOK measures how **people** and **AI answer engines** read a brand's web presence, and reports
where the two readings disagree. This plugin connects Claude to POKPOK's stored brand-perception
reports and adds **Dr HAOS**, POKPOK's Brand Perception Agent. In a chat that can draw it (claude.ai,
the Claude desktop app) the answer is drawn **inside the chat as a POKPOK page** (key numbers, cards,
infographics); in the Claude Code terminal you get the same numbers as tables, and a shareable page at
its own address on request.

## What you can ask

Sign in once (see `SETUP.md`), start a new chat and say "with POKPOK" so Claude uses it.

| Ask | What you get in the chat |
|---|---|
| Show Georganics with POKPOK. | A POKPOK page: key numbers, the brand card, who AI names instead, how people read the page, the five uncomfortable truths, what to fix first |
| Compare Georganics, banda and Dragon Rouge with POKPOK. | Leaderboard, the people score and the AI score of each brand, the five AI readings side by side, a scatter |
| Show the top AI-scored brands with POKPOK. | Leaderboard, both scores per brand, every score on one line with the average |
| How is our brand doing? | Your own brand's page or numbers (the signed-in account's own report) |
| Do AI engines describe our brand the way our own website does? | The 17-marker alignment: where the brand's own pages and the AI's reading disagree |
| Who does AI recommend instead of Georganics? | Who AI names, the brand in question in yellow |
| How visible are we in ChatGPT and Gemini this month, and which sites get cited? | For brands POKPOK tracks: how often AI answers name the brand, per engine and question, and the sources AI relies on |
| Dr HAOS, what is wrong with our site? | A diagnosis in Dr HAOS's form: DIAGNOSIS, KEY NUMBERS, EVIDENCE, CONSEQUENCE, PRESCRIPTION, I CAN |

Use any brand name or website instead of Georganics. Claude answers in words beside the page or the
table; ask follow-up questions as normal.

## What's inside

| Part | Purpose |
|---|---|
| `.mcp.json` | the POKPOK remote server, version 6, signed-in address (15 tools: 14 read-only, one that publishes a shareable page) |
| `skills/pokpok/` | when to use POKPOK, which tool reads what, where the in-chat page can be drawn, and the rules the answers follow |
| `skills/dr-haos/` | Dr HAOS's voice and answer form, word for word the text the live agent on pokpok.ai runs on |
| `SETUP.md` | how the sign-in works in Claude Code and in claude.ai |

The Dr HAOS skill is generated from POKPOK's own file, the same text the live agent runs on.

## Install

```
/plugin marketplace add xclv-ai/pokpok-plugin
/plugin install pokpok@pokpok-marketplace
```

Try it from a folder without installing: `claude --plugin-dir <path to this folder>`.

Without the plugin, add the server as a custom connector in Claude: **Settings → Connectors → Add
custom connector**, name `POKPOK`, address
`https://auth.pokpok.ai/functions/v1/pokpok-mcp-v6/private`.

## Accounts and data

The plugin uses POKPOK's signed-in address: sign in once with your POKPOK **email and password** before
the first question (Claude Code: `/mcp` → `pokpok` → Authenticate; claude.ai: the Connect card; see
`SETUP.md`). Public reports are then readable by any POKPOK account; a customer's own report ("our
brand") needs a purchase or subscription at [pokpok.ai](https://pokpok.ai). Every number the tools return
is a stored measurement with the date it was measured; the tools never estimate.

Do not press **Sign out** on pokpok.ai while you use POKPOK in Claude: signing out there also
disconnects Claude. Reconnect from the Connect card if that happens.

## Tools (server version 6)

`pokpok_show` (the POKPOK page inside the chat: one brand, a comparison, a top list, or a page form) ·
`pokpok_brand_report` · `pokpok_compare` · `pokpok_category_report` · `pokpok_listing_report` ·
`pokpok_visibility` · `pokpok_citations` · `pokpok_ai_answers` · `pokpok_define` · `pokpok_find` ·
`pokpok_my_reports` · `pokpok_catalog` · `pokpok_query` · `pokpok_fetch` (read-only) ·
`pokpok_page` (stores a shareable page and returns its address; needs sign-in).

Open `https://auth.pokpok.ai/functions/v1/pokpok-mcp-v6` in a browser to see the live server version
and when it was built.

## What changed in 6.0.0 (from 1.3.0)

- The server is version 6: in a chat that can draw it, the answer is drawn inside the chat as a POKPOK
  page (`pokpok_show`), laid out by POKPOK from the stored data, with seven graphics (leaderboard, brand
  card, lollipop, dumbbell, strip, heat grid, scatter).
- One brand's report is read in one call (`pokpok_brand_report` with the parts the question needs);
  comparisons, category studies, Amazon listings, AI-visibility tracking, cited sources and the AI
  answers word for word each have a tool of their own; `pokpok_define` explains every marker, metric
  and scale.
- Dr HAOS: his voice and answer form, as a skill.

Privacy policy: https://pokpok.ai/legal/privacy · Terms: https://pokpok.ai/legal/licensing ·
Support: https://pokpok.ai/support
