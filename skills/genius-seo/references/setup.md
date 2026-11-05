# Connecting Free Data Sources

Every key stays on your machine in `~/.config/claude-seo/` (Windows: `C:\Users\<you>\.config\claude-seo\`). Never commit keys.
These configs are read by the `claude-seo` plugin (`seo-google`, `seo-backlinks`, `seo-bing`).

| Priority | Source | Gives | Own site only? |
|---|---|---|---|
| 1 | Google Search Console API | Real queries, clicks, positions, indexing | Yes |
| 2 | Bing Webmaster Tools API + IndexNow | Backlinks, Bing keywords, fast indexing (feeds ChatGPT search / Copilot) | Mostly |
| 3 | PageSpeed Insights + CrUX API | Core Web Vitals | No, any URL |
| 4 | GA4 Data API | Which posts lead to conversions | Yes |
| 5 | Moz API (free tier) | Domain authority and links for any domain | No |
| 6 | Common Crawl | Rough backlinks for any domain, no key | No |
| 7 | Firecrawl | Live SERPs and any page's content | No |
| Paid | DataForSEO | Search volume, traffic potential, competitor top pages, content gap | No |

## 1. Google (Search Console, GA4, PageSpeed, CrUX)
1. console.cloud.google.com: create a new project.
2. APIs & Services → Library: enable Search Console API, PageSpeed Insights API, Chrome UX Report API and Google Analytics Data API.
3. Credentials → Create API key. Restrict it to PageSpeed and CrUX.
4. IAM & Admin → Service Accounts → Create `claude-seo` → Keys → Add JSON key. Save it as `~/.config/claude-seo/service_account.json`.
5. Copy the `client_email` from that JSON:
   - Search Console → Settings → Users and permissions → Add user → **Full**.
   - GA4 → Admin → Property Access Management → Add user → **Viewer**. Note the property ID.
6. Create `~/.config/claude-seo/google-api.json`:
   ```json
   {
     "service_account_path": "~/.config/claude-seo/service_account.json",
     "api_key": "YOUR_GOOGLE_API_KEY",
     "default_property": "sc-domain:yourdomain.com",
     "ga4_property_id": "properties/YOUR_GA4_ID"
   }
   ```

## 2. Bing Webmaster Tools + IndexNow
1. bing.com/webmasters → Import from Google Search Console.
2. Settings → API access → generate a key.
3. IndexNow: run the claude-seo Bing extension installer. It needs a key file served at your site root (a site change, so deploy it deliberately).

## 3. Moz
Free API key at moz.com. Check the current free query limit.

## 4. Backlinks config
`~/.config/claude-seo/backlinks-api.json`:
```json
{ "moz_api_key": "YOUR_MOZ_KEY", "bing_api_key": "YOUR_BING_KEY" }
```

## 5. Firecrawl
Either the claude.ai Firecrawl connector, or set `FIRECRAWL_API_KEY` (from firecrawl.dev) as an environment variable. This plugin's `.mcp.json` starts `firecrawl-mcp`.

## 6. Verify
Ask Claude to "check SEO connections". It runs claude-seo's `google_auth.py --check` and `backlinks_auth.py --check`.

## Manual free tools (no API)
- Google Keyword Planner: search volume (free with a Google Ads account, no spend needed).
- Ahrefs Webmaster Tools, Website Traffic Checker, Backlink Checker: paste results into the chat.
- Google Rich Results Test: validate FAQ and Article schema.
