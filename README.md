# Genius-seo

A Claude Code agent that vets a blog keyword before you write. It runs 5 keyword checks plus an AI filter against the live Google results and returns **GO / LONG-TAIL / SKIP** with a content plan.

## What's inside
- `agents/seo-keyword-scout.md`: the agent
- `docs/SEO-CHECKLIST.md`: the full SEO + AEO checklist the agent follows

## Install
Copy into your project:

```
your-project/.claude/agents/seo-keyword-scout.md
your-project/docs/SEO-CHECKLIST.md
```

Restart Claude Code, then ask: `use seo-keyword-scout on "your keyword"`.

## The checks
1. Search demand
2. Traffic potential
3. Business potential (0–3)
4. Search intent
5. Can you compete? Backlinks, authority, topical authority, something better to offer
6. AI filter: can an AI answer it without a click?

## Tools
- Works now with web search and Firecrawl.
- For real volume and backlink numbers, connect DataForSEO (`mcp__dataforseo__*`). Without it, the agent marks those checks "unknown" and doesn't guess.
