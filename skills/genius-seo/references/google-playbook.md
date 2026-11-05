# How Google Ranks: The Official Playbook

Everything here is from Google Search Central, web.dev or primary studies, read 2026-11-05, unless marked. Re-check before quoting.

## 1. The ranking systems Google names
Source: [A guide to Google Search ranking systems](https://developers.google.com/search/docs/appearance/ranking-systems-guide)

| System | What it does | What to do about it |
|---|---|---|
| **BERT, neural matching, RankBrain** | Understand meaning, intent and concepts, not just exact words | Write naturally for the reader's real question. No keyword stuffing |
| **Passage ranking** | Identifies "individual sections or passages of a web page" to judge relevance | Clear, descriptive headings; each section answers one thing well |
| **Helpful content** (part of core since Mar 2024) | Rewards "original, helpful content written by people, for people" | The self-assessment in §2 |
| **Reviews system** | Rewards "insightful analysis and original research… by experts or enthusiasts" | First-hand testing, evidence, real experience |
| **Original content systems** | Shows original reporting "ahead of those who merely cite it" | Be the source: original data, scripts, case studies |
| **Freshness ("query deserves freshness")** | Fresher results where freshness is expected | Update time-sensitive pages substantively. Don't just change the date |
| **Link analysis / PageRank** | Links are still a core signal | Earn real links (§5) |
| **Site diversity** | "Generally won't show more than two web page listings from the same site in our top results" | One strong page per intent; don't split one topic across many pages |
| **Deduplication** | Hides near-duplicate results | Avoid duplicate and boilerplate pages |
| **Exact match domain** | Doesn't over-reward keyword domains | Brand > keyword domain |
| **Reliable information** | Prioritizes reliable sources, especially for sensitive topics | Cite primary sources, especially for YMYL |
| **Spam detection (SpamBrain)** | Enforces the spam policies (§4) | Never game it |
| **Removal-based demotion** | Many valid copyright or personal-information removals demote the whole site | Don't copy |

Retired or merged into core: Panda (quality), Penguin (link spam, core since 2016), Hummingbird (2013).

## 2. Google's people-first self-assessment
Source: [Creating helpful, reliable, people-first content](https://developers.google.com/search/docs/fundamentals/creating-helpful-content)

**Ask before publishing:**
- Does it provide **original information, reporting, research or analysis**?
- Is it **"beyond the obvious"**? Does it add "substantial additional value" if it draws on other sources?
- Is the **title a descriptive, helpful summary**, not exaggerated or shocking?
- Would you **bookmark it, share it** or expect it in a book?
- Does it provide **substantial value compared with other pages in the results**?
- Is it **produced well**, with no spelling or style issues and nothing sloppy?
- Does it build trust: **clear sourcing, the author's expertise, an About page**?
- Is it **written or reviewed by an expert or enthusiast**? Any **easily verified factual errors**?
- Will the reader **leave having learned enough to reach their goal**, and feel **satisfied**?

**Warning signs of search-first content (avoid):**
- Lots of content on many topics hoping some ranks; **extensive automation**
- Mainly summarizing others; chasing trends you wouldn't otherwise cover
- Readers needing to **search again** for better information
- Writing to a word count ("**No, we don't**" have a preferred word count)
- Entering a niche "without any real expertise"
- **Changing dates to seem fresh** without substantial change; mass-adding or deleting content "to seem fresh" ("**No, it won't**" help)

**Who, How, Why (E-E-A-T):**
- **Who:** show bylines that lead to author background. **Never fake authors**: "AI-generated headshots, made-up names, or false credentials" are deception and a low-quality signal.
- **How:** explain how the content was made (testing, sources). Disclose substantial AI or automation use where readers would expect it.
- **Why:** "primarily to help people". If it's primarily to attract search visits, that isn't what core systems reward, and scaled automation for rankings is spam.

**Quality Rater Guidelines (secondary summary, Sept 2025 version; verify in [Google's PDF](https://static.googleusercontent.com/media/guidelines.raterhub.com/en//searchqualityevaluatorguidelines.pdf)):** AI content that is mass-produced without human review, or only rephrases existing sources, can be rated **Lowest**. YMYL now explicitly includes **government, civics and society**. Raters also now evaluate AI Overviews for direct, correct answers. Raters don't rank sites; their ratings help Google evaluate its systems.

## 3. Core updates: what to do when rankings move
Source: [Google Search's core updates](https://developers.google.com/search/docs/appearance/core-updates)

1. Wait until the update **finishes** (Search Status Dashboard), then **at least a week**.
2. Compare a week after with a week before, by page, query and search type (Web, Images, Video, News).
3. **Small drop** (e.g. #2 → #4): "no need to take drastic action". **Large drop** (e.g. #4 → #29): assess the site as a whole with the §2 questions, ideally with an unbiased outside reviewer.
4. **No quick fixes** (like removing an element "because you heard it was bad for SEO"). Improve in meaningful ways for users.
5. **Deleting content is a last resort.** Whole sections you want to delete are likely search-first.
6. **Recovery can take months**, sometimes until the next core update. Smaller unannounced updates also re-evaluate.

## 4. The full spam policy list (never do these)
Source: [Spam policies](https://developers.google.com/search/docs/essentials/spam-policies)

Cloaking · **Doorway abuse** ("pages… created to rank for specific, similar search queries") · **Expired domain abuse** · Hacked content · Hidden text and links · **Keyword stuffing** · **Link spam** ("links… primarily for the purpose of manipulating search rankings") · Machine-generated traffic · Malicious practices · Malware · Misleading functionality · **Scaled content abuse** · Scraping · **Site reputation abuse** (third-party content placed on a host mainly to use its ranking signals) · Sneaky redirects · Thin affiliation · User-generated spam · Legal-removal and personal-information-removal demotions · Policy circumvention · Scam and fraud.

**Highest risk for content-led businesses:** doorway pages (city or variation pages), scaled content, link schemes (paid links without `rel="sponsored"`) and site reputation abuse (paid "guest posts" on big sites).

## 5. Links
Source: [SEO link best practices](https://developers.google.com/search/docs/crawling-indexing/links-crawlable)
- Google crawls `<a href>` links. Use real HTML links, not JavaScript click handlers.
- **Anchor text:** descriptive and concise ("how the cheese is made", not "click here"). "If it feels like you're forcing keywords into the anchor text, then it's probably too much."
- **"Every page you care about should have a link from at least one other page on your site."** No orphan pages.
- Don't chain many links next to each other.
- `nofollow` only for sources you don't trust; **`sponsored` for paid links**; **`ugc`** for user-added links.

**Why links matter:** [Ahrefs (Dec 2023)](https://ahrefs.com/blog/search-traffic-study/) found 96.55% of pages get zero Google traffic. The three common reasons are **no search demand, no backlinks, and a mismatch with search intent**. Their conclusion: target uncompetitive topics you can rank for with few links, or build links for competitive ones.

## 6. Titles and snippets
Sources: [Title links](https://developers.google.com/search/docs/appearance/title-link) · [Snippets](https://developers.google.com/search/docs/appearance/snippet)
- **Every page needs a unique, descriptive, concise `<title>`.** "There's no limit on how long a `<title>` element can be", but it's truncated to fit the device. Keeping the key words in the first ~60 characters is a **practical** guideline, not a Google rule.
- No keyword stuffing; no repeated or boilerplate titles. Brand concisely (site name at the start or end with a delimiter).
- **Make the main title the most prominent text** (first visible `<h1>`). Google builds title links from the `<title>`, the main visual title, headings, `og:title`, prominent text, anchor text and WebSite structured data.
- **Snippets come mainly from page content.** Google uses the meta description when it describes the page better. "There's no limit on how long a meta description can be"; write a short, relevant pitch.

## 7. Page experience and Core Web Vitals
Sources: [Page experience](https://developers.google.com/search/docs/appearance/page-experience) · [web.dev Web Vitals](https://web.dev/articles/vitals)
- "There is no single signal." **Core Web Vitals are used by ranking systems**, but good scores don't guarantee top rankings. Chasing perfect scores "just for SEO reasons may not be the best use of your time."
- **Good thresholds (75th percentile, mobile and desktop):** LCP ≤ **2.5 s** · INP ≤ **200 ms** · CLS ≤ **0.1**.
- Other page-experience aspects "don't directly help your website rank higher", but they help users and conversions.

## 8. The expert's priority order
1. **Match intent** (the type, format and angle that already rank). This is the #1 reason pages fail.
2. **Pick winnable topics:** demand × business value × "can we compete?"
3. **Write non-commodity, people-first content** with E-E-A-T (real author, first-hand experience, sources).
4. **Earn real links and mentions**, and link internally so there are no orphans.
5. **Make it technically clean:** crawlable, indexable, fast enough (CWV "good"), unique titles.
6. **Keep it fresh** with substantive updates, not date changes.
7. **Measure** in Search Console (including the Generative AI report). For core-update drops, follow §3 instead of panicking.
