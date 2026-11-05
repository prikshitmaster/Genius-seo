# Genius-seo

A Claude Code agent that vets a blog keyword before you write. It runs 5 keyword checks plus an AI filter against the live Google results and returns **GO / LONG-TAIL / SKIP** with a content plan.

## What's inside
- `agents/seo-keyword-scout.md`: the agent
- `docs/SEO-CHECKLIST.md`: the full SEO + AEO checklist the agent follows
- `docs/AEO-NOTES.md`: how to get cited by AI assistants (query fan-out, brand gaps, mentions, YouTube, AI crawlers, measurement)

## Install

### 1. Agent + checklist
Copy into your project:

```
your-project/.claude/agents/seo-keyword-scout.md
your-project/docs/SEO-CHECKLIST.md
your-project/docs/AEO-NOTES.md
your-project/.mcp.json            (Firecrawl, see step 3)
```

### 2. Blog + SEO plugins (by AgriciDaniel, MIT)
Run inside Claude Code:

```
/plugin marketplace add AgriciDaniel/claude-blog
/plugin install claude-blog@agricidaniel-blog

/plugin marketplace add AgriciDaniel/claude-seo
/plugin install claude-seo@agricidaniel-claude-seo
```

- [claude-blog](https://github.com/AgriciDaniel/claude-blog): write, rewrite, fact-check, score and audit blog posts (`/blog write`, `/blog analyze`, `/blog factcheck`)
- [claude-seo](https://github.com/AgriciDaniel/claude-seo): technical SEO, schema, sitemap, backlinks, AI/GEO audits (`/seo audit`, `/seo page`)

### 3. Firecrawl (live Google results + page scraping)
Get an API key at https://firecrawl.dev and set it as an environment variable (never commit it):

```
# Windows (PowerShell)
setx FIRECRAWL_API_KEY "fc-..."
# macOS / Linux
export FIRECRAWL_API_KEY="fc-..."
```

The included `.mcp.json` starts the Firecrawl MCP server (`npx -y firecrawl-mcp`). On claude.ai you can use the Firecrawl connector instead; the agent supports both.

Restart Claude Code, then ask: `use seo-keyword-scout on "your keyword"`.

## Workflow
1. `seo-keyword-scout`: vet the keyword (GO / LONG-TAIL / SKIP)
2. `/blog write`: write the post from the agent's content plan
3. `/blog factcheck` + `/blog analyze`: verify sources, score the post
4. `/seo page <url>`: check the live page after publishing

## The checks
1. Search demand
2. Traffic potential
3. Business potential (0–3)
4. Search intent
5. Can you compete? Backlinks, authority, topical authority, something better to offer
6. AI filter: can an AI answer it without a click?

## Tools
- Works with web search and Firecrawl (see Install, step 3).
- For real volume and backlink numbers, connect DataForSEO (`mcp__dataforseo__*`). Without it, the agent marks those checks "unknown" and doesn't guess.
