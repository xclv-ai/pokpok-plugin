---
name: pokpok
description: Read a brand's POKPOK brand-perception report and answer from its measured numbers. Use this whenever someone asks how their brand, site, or a named competitor is doing, how AI engines or ChatGPT describe or recommend a brand, why AI gets a brand wrong, who AI names instead of them, what to fix first, where a category is crowded or has open ground, or wants findings turned into a shareable POKPOK page — including "how are we doing", "our brand", "our site", "does AI understand us". POKPOK holds measurements, not opinions; every number comes from a stored report. Do not use it to write marketing copy or taglines, for share prices or financial data, or for anything outside a brand's web presence.
---

# POKPOK brand review

POKPOK measures how **people** read a brand's web presence and how **AI answer engines** read the same presence, and reports the gap between the two. Everything it returns is a stored measurement. Your job is to read the right part of the report and pass the numbers on faithfully; the value of the answer is that it is measured, not reasoned.

## Whose brand

When the person says "our brand", "us", "my site", "we", or gives no brand at all, call the brand tools with **no arguments**. They are signed in; POKPOK resolves their own report. Only pass a `brand` when they ask about a different one — a competitor, a client, a named company.

## Tools, and what each one is for

| Tool | Answers |
|---|---|
| `pokpok_search` | What reports exist for a brand, category or market. Start here when a brand is named. |
| `pokpok_fetch` | Any section of one report, by the id search returned. |
| `pokpok_diagnosis` | The verdict: people-side scores, engine-side scores, the gap, the weakest thing. |
| `pokpok_alignment` | The central measurement: on each of 17 brand-strategy markers, where the brand's own pages place it versus where an AI engine places it — and where they disagree. |
| `pokpok_truths` | The five uncomfortable truths — what customers read first. |
| `pokpok_fixes` | What to change, each with the measure it moves and by how much. |
| `pokpok_ai_recommendations` | Who AI names when a buyer asks about the category, who it names first, whether this brand appears at all. |
| `pokpok_position` | Where a brand ranks inside a category study. |
| `pokpok_white_space` | Where a category is crowded and which positions nobody holds. |
| `pokpok_corpus` | The market view across every category — start here for "what do you cover", "where is the market weakest". |
| `pokpok_schema` then `pokpok_query` | Anything the tools above do not answer: ranking, filtering, counting across reports. Always read the schema first. |
| `pokpok_render_report` | Findings already in the conversation, turned into a POKPOK-branded page with a shareable link. |

## The standard brand review

When someone wants to understand a brand's standing rather than one narrow fact, run it in this order. Each step builds on the one before, and the person usually wants the whole picture even if they asked one question.

1. `pokpok_search` — only if a brand is named. Confirm a report exists and get its id.
2. `pokpok_diagnosis` — the verdict. Lead with it.
3. `pokpok_alignment` — where the story people read and the story AI reads diverge. This is POKPOK's central finding; the disagreements are the useful part.
4. `pokpok_truths` — quote them as written.
5. `pokpok_fixes` — what to do, with the measured effect of each change.
6. `pokpok_ai_recommendations` — who wins the AI answer instead. Usually the most uncomfortable result; give it straight.
7. `pokpok_render_report` — only when asked for a page to share.

For a **category** question ("how do we compare", "where is the gap in the market"), search with `kind:category`, then `pokpok_position` for the brand's rank and `pokpok_white_space` for crowding and open ground.

## Rules, and why they exist

**Never invent or estimate a number.** If a tool does not return a report, the person is not signed in or has not bought it. Say exactly that. A plausible-sounding score that POKPOK did not measure is worse than no answer, because the person will act on it.

**Do not combine POKPOK's measurements into one number.** A brand gets a people-side score and an engine-side score, each 0–100, and the 17 markers carry their own percentages. They measure different things — the gap between them *is* the finding. Averaging them hides the very thing the report exists to show.

**Quote the five truths as POKPOK wrote them.** They are meant to be uncomfortable. Softening or paraphrasing them into something gentler removes their value.

**Do not state how many brands or categories POKPOK has measured.** That is POKPOK's business. Do not infer a corpus size from what comes back, and do not ask for it.

**Report the fixes with POKPOK's numbers.** The effect of each change is measured, not an estimate; do not round it into vaguer language.

**Building a page: write content, not HTML.** `pokpok_render_report` takes titled blocks — headings, paragraphs, lists, tables — and draws them in POKPOK's design. Never write markup or choose colours. When it returns, read its `advisories`: they name any figure on the page that POKPOK's data does not support. Tell the person about those before sharing the link.

**Large answers are cut on purpose.** If a result says it was truncated, ask for less — a section, fewer rows, fewer columns — rather than treating what you have as the whole answer.

## What this skill is not for

Writing taglines or marketing copy, financial or share-price questions, scheduling, or anything outside a brand's web presence. POKPOK reports what was measured; it does not create campaigns.
