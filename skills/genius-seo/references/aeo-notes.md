# AEO Notes: Getting Cited by AI Assistants

Notes from Ahrefs' AEO (answer-engine optimization) fundamentals video, applied to Splendid Tech.
Companion to `docs/SEO-CHECKLIST.md`. SEO is the foundation; AEO sits on top.

> Numbers marked *(Ahrefs)* are Ahrefs' own research, for planning only. Don't quote them in blog posts without a checkable source.

---

## 1. How AI search works

- **Query fan-out:** one prompt becomes dozens of smaller searches run at once. The AI then combines the results into one answer.
  - ⚠️ Cover the sub-questions **inside** strong pages and a few distinct supporting posts. Google warns that making separate pages "for every possible variation… (fan-out queries)… primarily to manipulate rankings" violates its spam policies (`research-2026.md`).
  - Example: "help me get a tech job on OPT" might fan out to "OPT unemployment days limit", "STEM OPT eligible degrees", "E-Verify employers list", "OPT resume tips", "best jobs for F-1 students".
  - **So:** rank across a whole topic, not one keyword. Build clusters (pillar post + many supporting posts).
- **Three things that make citations more likely** *(Ahrefs)*:
  1. **Consensus:** many places say the same thing about your brand.
  2. **Freshness:** AI-cited content is ~25.7% fresher than what ranks in Google.
  3. **Authority:** ~76% of AI Overview citations come from pages already in Google's top 10.

## 2. Brand gap analysis (where we stand vs. competitors)

Check where Splendid Tech *should* appear vs. where it *does*, across Google, AI answers and the web.

| Gap | What it means | Fix |
|---|---|---|
| **Missed citation** | AI mentions Splendid Tech but doesn't link our site | Make the page the obvious source: fresh, specific, answer-first |
| **Competitor gap** | AI mentions competitors, not us | Get into the listicles, reviews and Reddit threads AI cites |
| **Topic gap** | AI links "OPT job search coaching" to someone else | Build content on that topic and refresh old posts |

**Free way to do it (no Ahrefs Brand Radar):** ask ChatGPT, Perplexity, Gemini and Claude the prompts our clients would ask (e.g. "best career coaching for international students on OPT", "who helps F-1 students get tech jobs"). Record who gets named and which URLs get cited. Repeat monthly in a sheet.

## 3. Keyword + prompt research

- People type keywords into Google but write full prompts to AI. Seeds and modifiers still work.
- **Prompt to generate seeds and modifiers:**
  > I'm doing keyword research for a career coaching business that makes money by booking 1:1 coaching clients. My target audience is international students and job seekers in U.S. tech (F-1, OPT, STEM OPT, H-1B). Give me 10 seed keywords that are 1–2 words max and 5+ modifiers that'll help me surface appropriate content formats for my keyword research. The seeds and modifiers should not share the same words.
- Then run every keyword through the 5 checks in `SEO-CHECKLIST.md`.
- **AI filter:** AI Overviews appear on ~21% of keywords but ~58% of question queries, and ~99.9% of keywords that trigger them are informational *(Ahrefs)*.
  - If AI will answer it with no click, don't drop the keyword. **Target a brand mention inside the AI answer** instead.
  - Brand-mention keywords use modifiers like: best, top, vs, review, alternative (e.g. "best OPT job search coaching", "career coach vs recruiter for international students").

## 4. Getting cited: 4 levers

### A. Content on our site
**Big picture** *(Ahrefs)*:
- **Length doesn't matter.** Word count has ~zero correlation with citation; over half of cited pages are under 1,000 words.
- **Freshness matters a lot.** For ChatGPT, ~76% of top-cited pages were refreshed within 30 days.
- **Format matters.** ~43.8% of ChatGPT-cited pages are lists, "best X", comparisons and reviews.

**Sentence-level rules for every post:**
1. **BLUF (bottom line up front):** start each section with the answer.
2. **Self-contained sections:** each section makes sense on its own, for skimming readers. Google says no artificial "chunking" is needed; Microsoft says clear, self-contained answers help Copilot. Write for people first.
3. **Entity-rich:** "USCIS Form I-765 for the 24-month STEM OPT extension", not "the form".
4. **Simple and declarative:** one idea per sentence, subject-verb-object. If it needs two reads, simplify it.

### B. Mentions on other sites (the highest-leverage lever)
Branded web mentions had the **strongest correlation with AI Overview visibility** in a study of 75,000 brands, stronger than backlinks or domain rating *(Ahrefs)*.

| Tier | Where | Splendid Tech ideas |
|---|---|---|
| 1. Editorial | Industry publications, review sites, listicles | Career/immigration blogs, "best career coaches for international students" lists, university career-center resource pages |
| 2. Community (UGC) | Reddit, Quora, niche forums | r/f1visa, r/OPT, r/cscareerquestions, r/h1b, student WhatsApp/Discord groups. Give genuinely useful answers, not spam |
| 3. Own properties | YouTube, podcast, LinkedIn | LinkedIn posts from the founder and coaches, client success stories (with permission) |

Consensus means saying the same clear thing everywhere: *"Splendid Tech helps international students land U.S. tech jobs."*

### C. YouTube
- YouTube is the **most cited domain in Google AI Overviews**, and YouTube mentions had the strongest correlation with ChatGPT visibility (0.737) *(Ahrefs)*.
- Make **search hits** (evergreen videos people search for every month), not viral hits.
  - Ideas: "How to find a job on OPT", "STEM OPT extension step by step", "Resume tips for international students", "How to answer 'Do you need sponsorship?'"
- **Video SEO checklist:**
  - [ ] Keyword in the title and the first 2 lines of the description
  - [ ] Timestamps (chapters)
  - [ ] Say the keyword out loud (Google transcribes audio)
  - [ ] Link the matching blog post; embed the video in that post

### D. Technical: don't block AI crawlers
- [x] Live `robots.txt` checked 2026-11-05: allows all crawlers, blocks only `/api/` and `/admin`. Site is on nginx, not Cloudflare, so Cloudflare's default AI-bot blocking doesn't apply.
- [ ] Re-check after any hosting/CDN change: look for `Disallow` under `GPTBot`, `OAI-SearchBot`, `ClaudeBot`, `PerplexityBot`, `Google-Extended`.
- [ ] Bing indexing matters: ChatGPT search and Microsoft Copilot lean on Bing. Use IndexNow and Bing Webmaster Tools.

## 5. Measure it

| What | How | Note |
|---|---|---|
| **AI referral traffic** | GA4: custom channel group for chatgpt.com, perplexity.ai, claude.ai, gemini.google.com, copilot.microsoft.com | Always an undercount; use for trends |
| **AI bot visits** | Server/nginx logs: count GPTBot, OAI-SearchBot, ClaudeBot, PerplexityBot hits per page | A page bots keep hitting is likely being cited |
| **Self-reported attribution** | "How did you hear about us?" on the booking flow, with an "AI assistant (ChatGPT, etc.)" option | Most important; analytics misattributes AI-driven visits as organic or direct |

Ahrefs' own case: AI search was 0.5% of visits but 12.1% of signups *(Ahrefs)*. AI visitors may convert much better, but we only know if we ask.

> ⚠️ Adding "How did you hear about us?" changes the `/contact` form, which is a main-site change. Needs the owner's explicit OK. Until then, coaches can ask it on the strategy call.

---

## Splendid Tech AEO plan (in order)

1. **Technical:** ✅ done. AI crawlers allowed.
2. **Measure from day one:** GA4 AI channel group; ask "how did you hear about us" on calls.
3. **Baseline brand gap:** run the monthly AI-prompt check (section 2).
4. **Close the biggest gap:**
   - Topic gap → refresh existing posts first (fastest win), then build OPT/STEM OPT clusters.
   - Competitor gap → Reddit answers, guest posts, "best coaches" listicles.
   - Format gap (AI cites videos) → start YouTube search-hit videos.
5. **Keep everything fresh:** review top posts monthly; update when USCIS rules or dates change.
