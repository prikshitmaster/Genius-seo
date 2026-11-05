# SEO + AEO Checklist

Run this before writing any blog post. Based on Ahrefs' SEO fundamentals (2-hour course summary), adapted for Splendid Tech.

Target keywords to work in where they fit: staffing, consultancy, consulting, coaching, STEM OPT, OPT, OPT EAD, job search.

> Numbers below marked *(Ahrefs)* come from Ahrefs' own studies. Use them for planning only. Don't quote them in blog posts without a checkable source.

---

## How ranking works (the 3 signals that matter)

1. **Backlinks:** links from other sites act as votes of trust.
2. **Search intent:** the page type has to match what searchers want.
3. **User satisfaction:** answer the query fully and fast. Length doesn't matter.

AI answers (ChatGPT, Google AI Overviews) split one prompt into many searches and pull from the same search indexes. Ranking in Google is the foundation of getting cited by AI. *(Ahrefs: 76% of AI Overview citations come from pages already in the top 10.)*

---

## Step 1: Is the keyword worth targeting? (5 checks + AI filter)

### 1. Search demand
- [ ] Check search volume (Ahrefs, Semrush, Google Keyword Planner).
- [ ] Don't trust volume alone. Some queries get zero clicks because Google answers them on the results page.

### 2. Traffic potential
- [ ] Look at how much traffic the current #1 page gets overall, not just the keyword's volume. A top page ranks for many related keywords.

### 3. Business potential (score 0–3)
| Score | Meaning | Example |
|---|---|---|
| 3 | Our service is the natural solution | "OPT job search help", "resume review for international students" |
| 2 | Easy to recommend a service | "how to get a job on OPT", "STEM OPT resume tips" |
| 1 | Relevant audience, hard to pitch | "what is OPT EAD" |
| 0 | No link to our services | general visa news unrelated to jobs |

- [ ] Prefer 2–3. Write 1s only to build topical authority.
- [ ] Note which service page this maps to: `career-strategy`, `resume`, `linkedin`, `networking`, `job-applications`, `interview-prep`.

### 4. Search intent (read the current results)
- [ ] **Content type:** blog posts, videos, service pages, government pages?
- [ ] **Format:** how-to, listicle, guide, comparison, checklist?
- [ ] **Angle:** beginner, "2026 update", step-by-step, for a specific role?
- [ ] If the results are all USCIS/government pages or job boards and we'd write a blog post, intent doesn't match. Move on.

### 5. Ranking difficulty: Can we compete?
- [ ] More quality backlinks than them?
- [ ] Website authority in the same ballpark?
- [ ] Equal or more topical authority?
- [ ] Something better to offer?

| "Yes" answers | Action |
|---|---|
| 3–4 | Go for it. |
| 2 | Only if "something better" is a strong yes; build supporting posts first. |
| 0–1 | Pick a longer-tail keyword and re-check. |

### AI filter
- [ ] Google the keyword. Can an AI Overview fully answer it without a click? If yes, the click is gone. Either skip it or target it so that **Splendid Tech gets named inside the AI answer**.
- [ ] Question keywords trigger AI Overviews most often *(Ahrefs: ~58% vs ~21% overall)*. "How do I..." posts need extra depth that AI can't summarize away: timelines, examples, real scenarios.

---

## Step 2: Find keyword ideas
- [ ] Start with seed keywords: OPT, STEM OPT, OPT EAD, H-1B job search, international student resume, tech interview prep, LinkedIn for job seekers.
- [ ] Filter by modifier:
  - Informational: how, what, why, guide, timeline, checklist
  - Commercial: best, top, vs, review, coaching, consultant, services
- [ ] Check competitor sites' top pages (Ahrefs Site Explorer → Top Pages). If it brings them traffic, add it to the list.

---

## Step 3: Write the post

### Match the winners
- [ ] Open the top 3 relevant results (skip outliers that don't match intent).
- [ ] List the subtopics they all cover, how their headings are structured, and who they're written for.
- [ ] Content gap: find keywords those pages rank for in common. Those are subtopics readers expect.
- [ ] Then beat them: fresher facts, clearer steps, first-hand examples.

### On-page basics
- [ ] Keyword in the title (under ~60 chars) where it fits naturally, in the H1 and in the first 100 words.
- [ ] Short, descriptive URL slug.
- [ ] Meta description ~150–160 chars saying what the reader gets.
- [ ] One H1, clear H2/H3s, short sentences, short paragraphs.
- [ ] Internal links from other relevant posts to this one, and from this one to the matching service page.
- [ ] No keyword stuffing, no word-count target.

### Write for AI (AEO)
- [ ] **Bottom line up front:** each section opens with the answer, then the detail.
- [ ] **Atomic sections:** every section makes sense on its own, because AI reads in chunks.
- [ ] **Entity-rich:** use names, numbers and specifics ("USCIS Form I-765", "90 days of unemployment on post-completion OPT"), not "the form" or "a limit".
- [ ] FAQ section with real questions (People Also Ask, Reddit, student forums) and JSON-LD FAQPage.

### Accuracy and trust
- [ ] Immigration facts checked against USCIS, Study in the States or the Federal Register, with links.
- [ ] Every statistic has a real, checkable source. The 70% mentorship figure is labeled as Splendid Tech internal data.
- [ ] Plain, human voice. Splendid Tech mentioned once, in the CTA.
- [ ] Ends with one CTA: "Book a Free Strategy Call" linking to `/contact`.

### Freshness
- [ ] Content cited by AI tends to be fresher than what ranks in Google *(Ahrefs: ~25.7% fresher)*. Refresh posts when OPT/STEM OPT rules or dates change.
- [ ] Fastest wins are often updating posts that used to rank and slipped, not new posts.

---

## Step 4: Earn links and mentions
- [ ] **Skip** created links (directories, comments, profiles: little value) and bought links (against Google's spam policies).
- [ ] **Earn** links through relevance, relationships and a fair exchange of value:
  - Guest posts for international student blogs and career sites.
  - Expert quotes for journalists writing about OPT/H-1B job markets.
  - Outreach to university career centers and student orgs with a genuinely useful resource.
  - Find outdated stats on pages that rank. Email the sites linking to them and point to our updated, sourced version.
- [ ] The first outreach email starts a conversation; it doesn't ask for a link.
- [ ] **Brand mentions count even without a link.** *(Ahrefs: branded web mentions had the strongest correlation with AI Overview visibility.)* Get "Splendid Tech" named on Reddit, LinkedIn, podcasts and student forums.

---

## Step 5: Technical checks (after every deploy)
- [ ] No stray `noindex` on public pages. Currently only `app/admin/layout.tsx` is noindex, which is correct.
- [ ] `app/robots.ts` only disallows `/api/` and `/admin`. Don't block Googlebot or AI crawlers from `/blogs`.
- [ ] New posts are in the sitemap and live in the production database (not only `data/blogs.ts`).
- [ ] Every main page and a few `/blogs/<slug>` pages return 200.
- [ ] Run a scheduled site audit (Ahrefs Webmaster Tools is free; Google Search Console for indexing).
