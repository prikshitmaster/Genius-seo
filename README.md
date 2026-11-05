# Genius SEO

A Claude Code plugin with a full SEO + AEO playbook for business blogs. It vets keywords, plans and writes posts that rank in Google **and** get cited by ChatGPT, Perplexity and Google AI Overviews. Then it builds links and mentions, checks the technical setup and measures what turns readers into customers.

## What's inside

| Part | What it does |
|---|---|
| `skills/genius-seo/SKILL.md` | The main skill. Knows the whole playbook and decides which tool handles each task |
| `agents/seo-keyword-scout.md` | Vets a keyword: 5 checks + AI filter → **GO / LONG-TAIL / SKIP** + content plan |
| `skills/genius-seo/references/seo-checklist.md` | Keyword checks, on-page rules, links, technical SEO |
| `skills/genius-seo/references/aeo-notes.md` | AI search: query fan-out, brand gaps, the 4 citation levers, YouTube, measurement |
| `skills/genius-seo/references/setup.md` | Connecting free data sources (Search Console, GA4, Bing, Moz, Firecrawl) |
| `.mcp.json` | Starts the Firecrawl MCP server |

The reference notes use a career-coaching business as the worked example. The skill adapts to your business from your project's `CLAUDE.md` or `.genius-seo/business.md`, and asks you if neither exists.

## Install

Inside Claude Code:

```
/plugin marketplace add prikshitmaster/Genius-seo
/plugin install genius-seo@genius-seo
```

Recommended companion plugins (by AgriciDaniel, MIT). Genius SEO hands work to them:

```
/plugin marketplace add AgriciDaniel/claude-blog
/plugin install claude-blog@agricidaniel-blog

/plugin marketplace add AgriciDaniel/claude-seo
/plugin install claude-seo@agricidaniel-claude-seo
```

Firecrawl (live Google results and page reading): use the claude.ai Firecrawl connector, or set a key from https://firecrawl.dev:

```
setx FIRECRAWL_API_KEY "fc-..."        # Windows
export FIRECRAWL_API_KEY="fc-..."      # macOS / Linux
```

Restart Claude Code.

## Use it

Just ask:

- `/genius-seo where do I start?`: technical check → measurement → brand gap → biggest gap first
- `can we rank for "your keyword"?`: runs the keyword scout
- `find keywords for my business`
- `plan a topic cluster on X`
- `write a post on X`: vet → brief → write → fact-check → score
- `which posts should I refresh?`
- `how do I get mentioned by ChatGPT?`
- `check if AI crawlers can reach my site`
- `connect Search Console`

## The keyword checks
1. Search demand
2. Traffic potential
3. Business potential (0–3)
4. Search intent
5. Can you compete? Backlinks, authority, topical authority, something better to offer
6. AI filter: can an AI answer it without a click?

## Rules it follows
- Never invents numbers; marks missing data "unknown" and names the tool that would answer it.
- Every published statistic needs a checkable source; regulated topics use official sources only.
- Never publishes, deploys, pushes or sends outreach without your OK.

## Data sources
Works out of the box with web search and Firecrawl. Free upgrades (Search Console, GA4, Bing Webmaster, PageSpeed/CrUX, Moz, Common Crawl) are in `references/setup.md`. DataForSEO (paid) adds search volume and competitor keyword data.

## License
MIT
