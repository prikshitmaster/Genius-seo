# What the Leaders Say (2025–2026 research)

Primary sources only, read 2026-11-05. Planning numbers: don't publish them without the source link. Re-check before quoting; these pages get updated.

## 1. Google: official guidance on AI features
**Source:** [Optimizing your website for generative AI features on Google Search](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)

**Do:**
- **SEO is still the foundation.** "Continue prioritizing foundational SEO best practices, such as building a clear technical structure and creating unique, valuable content."
- **Write non-commodity content.** "Don't just recycle what others on the internet have already said, or could easily be produced by a generative AI model." Bring "in-depth experience".
- **Use supporting media:** "high-quality, relevant images and videos" where useful.
- **Keep it crawlable:** good page experience, less duplicate content, JavaScript SEO best practices.
- **Check eligibility:** a site must be included in the Search Console **Search generative AI control** ([help](https://support.google.com/webmasters/answer/16908024)). "Include" is the default, rolled out to all sites on 2026-08-31. Check that nobody switched it to "Exclude".
- **Measure:** the Search Console **Generative AI performance report**.

**Google says you can ignore** (its "mythbusting" list):
- **llms.txt and "special" AI markup:** "Google Search itself doesn't use them."
- **"Chunking" content:** "There's no requirement to break your content into tiny pieces… There's no ideal page length."
- **Rewriting just for AI:** AI understands synonyms, so you don't need every long-tail variation.
- **Inauthentic mentions:** "seeking inauthentic 'mentions' across the web isn't as helpful as it might seem."
- **Overfocusing on structured data:** not required for AI features, though still useful for rich results.

**Warning:** creating "separate content for every possible variation of how people might search (… fan-out queries)… primarily to manipulate rankings" **violates Google's spam policies**, and "a high quantity of pages doesn't make a website higher quality."

## 2. Microsoft Bing / Copilot
**Source:** [Optimizing Your Content for Inclusion in AI Search Answers](https://about.ads.microsoft.com/en/blog/post/october-2025/optimizing-your-content-for-inclusion-in-ai-search-answers) (Microsoft Advertising)

- Copilot parses pages into pieces. Help it with **clear descriptive headings, concise 1–2 sentence answers, lists, tables and Q&A blocks**, "self-contained phrasing", and specific facts instead of vague claims ("42 dB", not "quiet").
- **Avoid:** walls of text; **key answers hidden in tabs or expandable menus**; core information only in PDFs or images; decorative symbols (→ ★ !!!); overloaded sentences; unanchored hype ("next-gen").
- **Measure:** Bing Webmaster Tools **AI Performance** report (public preview, [Feb 2026](https://blogs.bing.com/webmaster/2026/2/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview/)) shows when your site is cited in Copilot answers.

**Reconciling Google and Microsoft:** clear structure, specific facts and direct answers help human readers *and* both engines. What Google warns against is **AI-only tricks** (llms.txt for Google, artificial chunking, page-per-variation). Write for people, structured clearly.

## 3. Ahrefs
- **AI Overviews cut clicks hard.** Dec 2025 data: an AI Overview correlates with **~58% lower CTR for position 1** (−50.8% at #2, −46.4% at #3). 300k keywords, Search Console data. ([Ahrefs, Feb 2026](https://ahrefs.com/blog/ai-overviews-reduce-clicks-update/))
- **What correlates with brand visibility in AI** (75k brands; ChatGPT, AI Mode, AI Overviews) ([Ahrefs, Dec 2025](https://ahrefs.com/blog/ai-brand-visibility-correlations/)):
  - YouTube mentions ~0.737, the strongest factor everywhere
  - Branded web mentions 0.709, branded anchors 0.628, branded search volume 0.466 (AI Mode)
  - Domain Rating is mid-tier, weaker than brand signals
  - The 3 assistants mostly mention the same brands (0.779 overlap)
  - ChatGPT relies least on classic authority, so it's **the most accessible entry point for small brands**
  - "Chasing low quality links and churning out content for content's sake" won't help
- **Time to rank:** only 1.74% of new pages reach the top 10 within a year; 40.82% of the pages that do get there in month 1. ([Ahrefs, May 2025](https://ahrefs.com/blog/how-long-does-it-take-to-rank-in-google-and-how-old-are-top-ranking-pages/))

## 4. Semrush
**Source:** [AI search SEO traffic study](https://www.semrush.com/blog/ai-search-seo-traffic-study/)
- The average AI search visitor (from a non-Google AI source such as ChatGPT) is **4.4× as valuable as an organic visitor, by conversion rate**: "even the smallest traffic gains from AI search can make a huge difference."
- **Traditional SEO factors drive much of LLM visibility.** Ranking still helps you get cited.
- ChatGPT search often cites pages beyond the top results; some LLMs favor positions 1–5.
- **Quora is the most-cited site in AI Overviews**; Reddit is also heavily cited.
- **~50% of ChatGPT links point to business/service websites.** Your own site can be cited.
- **Recommended:** quality and unique content, multimodal content, clear entities and headings, **comparison guides**, crawlable HTML (many AI crawlers don't run JavaScript), and consistent brand messaging across channels.

## 5. How people read (usability research)
**Source:** [Nielsen Norman Group: F-shaped pattern](https://www.nngroup.com/articles/f-shaped-pattern-reading-web-content/)
- People scan. Eyetracking shows patterns like the F-shape: they read the top, then skim down the left. **Put the key point in the first words of headings, paragraphs and bullets.**

## What changed in our playbook
| Old | New |
|---|---|
| "AI Overviews take ~35% of #1 clicks" | **~58%** (Ahrefs, Dec 2025 data) |
| "Chunk content into atomic sections for AI" | Keep sections clear and self-contained **for readers**. Google says no artificial chunking is needed |
| "Create content for every fan-out query" | **Cover the topic in one strong page** + distinct supporting posts. A page per variation is a spam risk |
| "Get mentions everywhere" | **Genuine** mentions only (Google) |
| llms.txt as an AEO step | Optional for non-Google tools; **Google ignores it** |
| Measure AI with GA4 referrals only | Add **Search Console Generative AI report** + **Bing AI Performance** |
