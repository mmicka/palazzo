# Measuring and Tracking Visibility in ChatGPT (and Other AI Assistants): Tools, Methods, Benchmarks — as of October 2026

_Research note on sourcing: the sandbox's egress proxy blocked direct page fetches (WebFetch failed on nearly every domain), so every figure below comes from web-search result extracts of the cited pages. I could not read the full pages to confirm context. Treat exact numbers, and pricing especially, as "reported by the cited page" and re-check them on the live page before publishing. Pricing is in USD unless noted. Most sources are vendor or agency blogs with a commercial interest; I flag conflicts of interest throughout._

---

## 1. AI visibility tracking tools in 2026: price for small businesses, what they measure, how they collect data

### Takeaway
A small agency can start tracking for about $29–$100/month: Otterly Lite at $29, Semrush AI Visibility Toolkit at $99 per domain, Peec Starter at about $95, and SE Ranking's AI add-on at about $89. HubSpot's AI Search Grader gives a free one-off snapshot. Profound, Scrunch and Ahrefs Brand Radar (all-platform tier) cost $199–$699+/month or are enterprise-only. Prices changed often in 2026 and sources conflict, so every price below needs checking on the vendor page. Data collection splits into UI/front-end scraping (Peec, Profound), API calls (Gumshoe advocates this), and modeled prompt databases (Ahrefs, Semrush). These methods give materially different answers.

### Cited Findings

**General market picture**
- Roundups dated July–September 2026 agree broadly on tiers but conflict on Profound and Peec prices. Vendors changed pricing often in 2026. — [Elite Content Marketer](https://www.elitecontentmarketer.com/best-ai-visibility-tools/); [Stork.ai](https://www.stork.ai/blog/profound-vs-otterly-vs-peec); [Surmado](https://www.surmado.com/blog/best-ai-visibility-tools-2026); [ZipTie](https://ziptie.ai/blog/best-ai-visibility-tools-for-brands/); [Marqeable](https://www.marqeable.com/blog/best-ai-visibility-tools/)
- Many "comparison" articles are published by competing tools (e.g., Ryze, Trakkr, RankAI, Dageno, Airefs, AEO Labs, Peec's own comparison page), so their pricing claims carry a conflict of interest. — e.g., [Peec vs Profound (Peec-authored)](https://peec.ai/comparison/peec-vs-profound); [AEO Labs](https://www.aeolabs.ai/blog/profound-alternatives)

**Otterly.AI**
- Lite: $29/mo (about $25/mo annual) for 15 prompts and 1 workspace. Standard: $189/mo (about $160 annual) for 100 prompts, unlimited workspaces, and API/MCP access. Premium: $489/mo (about $422 annual) for 400 prompts. Enterprise is custom, reportedly "from $1,000/month." — [Rework](https://resources.rework.com/tools/aeo-ai-visibility/best-otterly-alternatives); [Capterra](https://www.capterra.com/p/10023384/Otterly-AI/pricing/); [UD Hong Kong, Aug 2026](https://www.ud.hk/en/insight/article/ai-visibility-tools-cost-hk-2026-08-17)
- Base engines are ChatGPT, Google AI Overviews, Perplexity and Microsoft Copilot. Gemini, Google AI Mode and Claude are paid add-ons: Gemini and AI Mode about $9/mo each on Lite; Claude about $29 on Lite, $109 on Standard and $439 on Premium. Team members are unlimited. — [Rework](https://resources.rework.com/tools/aeo-ai-visibility/best-otterly-alternatives); [Elite Content Marketer](https://www.elitecontentmarketer.com/best-ai-visibility-tools/)
- Data collection method: not stated in any source I found (gap).

**Peec AI**
- Current USD list: Starter $95/mo (50 prompts, choice of 3 models, 1 brand, about 4,500 checks); Pro $245/mo (150 prompts, 3 brands, about 13,500 checks); Advanced $495/mo (350 prompts); Enterprise custom (adds API and SSO). A 4th model costs $35/$85/$165 per month depending on tier. Annual billing is about 15% off. — [Capterra](https://capterra.com/p/10030058/Peec-AI/pricing); [Trakkr review](https://trakkr.ai/reviews/peec-ai-review/pricing); [LLM Pulse](https://llmpulse.ai/blog/best-peec-ai-alternatives/)
- Older euro listings conflict: Starter €89 and Pro €199 with up to 100 prompts. These appear to be outdated. — [Peec comparison page](https://peec.ai/comparison/peec-vs-profound); [Toolradar](https://toolradar.com/tools/peec-ai/pricing)
- Collection method: comparison blogs describe Peec as using UI scraping that "simulates how real users interact with ChatGPT, Perplexity, and AI Overviews," not API calls. I have not confirmed this against Peec's own documentation. — [Red Accel](https://www.redaccel.com/blog/ai-visibility-tools-compared/); [Content Monk](https://www.contentmonk.io/blog/profound-alternatives)

**Profound**
- The self-serve lineup reported through mid-2026 was: Starter $99/mo (ChatGPT only, 50 prompts, about 1,500 responses, 1 seat); Growth $399/mo (3 engines: ChatGPT, Perplexity and AI Overviews; 100 prompts; 3 seats; CSV/JSON export); Enterprise custom. Self-serve was billed annually. Claude and the full set of 9–11 engines required Enterprise. — [That Marketing Buddy](https://thatmarketingbuddy.com/pricing/profound); [Rankability](https://www.rankability.com/blog/profound-ai-review/); [WorkDuo](https://www.workduo.ai/blog/profound-ai-pricing)
- Third-party reviews put Enterprise deployments at about $2,000–$5,000+/month. — [WorkDuo](https://www.workduo.ai/blog/profound-ai-pricing); [AI Growth Agent](https://aigrowthagent.co/articles/profound-pricing/)
- **Possible change, September 2026:** the PricingSaaS tracker logged a week-39 2026 update in which Profound removed the paid self-serve tiers (Starter $99 and Growth $399), leaving a free Trial plan plus custom Enterprise. A September 2026 roundup also says the pricing page now shows only a free trial and custom Enterprise. Other mid-2026 sources still list $99/$399. Profound's help center mentions a 7-day trial for a "Lite" plan. — [PricingSaaS 2026W39](https://pricingsaas.com/companies/tryprofound/diffs/2026W39); [Elite Content Marketer](https://www.elitecontentmarketer.com/best-ai-visibility-tools/); [Profound help center](https://help.tryprofound.com/articles/2768996586-can-i-get-a-trial-plan-for-profound)
- Collection method: described as front-end capture ("daily browser-captured prompts") plus a "licensed opt-in consumer panel" that estimates real prompt behavior. — [Red Accel](https://www.redaccel.com/blog/ai-visibility-tools-compared/); [Content Monk](https://www.contentmonk.io/blog/profound-alternatives)

**Semrush AI Visibility Toolkit / Enterprise AIO**
- The AI Visibility Toolkit costs $99/mo per domain, billed annually, sold as a standalone product with a reported 7-day trial. Enterprise AIO is quote-only, sold at enterprise.semrush.com, and positioned for agencies running AI visibility "across dozens of clients." One guide claims an extra $99 per user, which I could not confirm. — [Semrush blog (vendor)](https://www.semrush.com/blog/ai-visibility-tracking-tools-for-agencies/); [Rework](https://resources.rework.com/tools/aeo-ai-visibility/best-semrush-ai-toolkit-alternatives); [eesel](https://www.eesel.ai/blog/semrush-seo-pricing)
- Data: reported as a "real-prompt clickstream (317M+ prompts)" combined with prompt tracking that Semrush runs itself. — [Activepieces](https://www.activepieces.com/blog/ai-visibility-tools-compared-by-plan-caps-2026); [APISerpent](https://apiserpent.com/blog/best-ai-visibility-tools)

**Ahrefs Brand Radar**
- Pricing conflicts. The most consistent reading is an add-on at $199/mo for one AI index, $398/mo for selected platforms and $699/mo for all platforms. One source says a limited version is included in Ahrefs base plans from $129/mo (Lite). Brand Radar began as a free beta, and that phase is over. — [Dageno review, Mar 2026 (competitor)](https://dageno.ai/blog/ahrefs-brand-radar-review); [RankAI (competitor)](https://rankai.ai/blog/ahrefs-brand-radar-alternatives); [HubSpot ES](https://blog.hubspot.es/marketing/mejores-alternativas-ahrefs-brand-radar?gad=1)
- Method: Brand Radar does not run your own prompts by default. It runs about 448–492 million prompts derived from Ahrefs' keyword database, Google People Also Ask and "fan-out" sub-questions across ChatGPT, Perplexity, Gemini, Copilot, AI Overviews and AI Mode. Prompt sets are refreshed monthly, and reports use a 90-day window. "Custom Prompts" can also be run as often as daily. — [Ahrefs methodology (vendor)](https://ahrefs.com/de/blog/brand-radar-methodology/); [Ahrefs Brand Radar page](https://ahrefs.com/brand-radar?currency=USD)
- Share of voice weights each prompt by "AI-adjusted volume," meaning Google search volume × a platform ratio (currently 0.115 for ChatGPT, so 20,000 Google searches becomes about 2,300 ChatGPT "impressions"). Ahrefs says these numbers show "potential visibility, not actual audience reach." The index favors high-demand questions, so niche or low-volume brands may get thin coverage. — [Ahrefs methodology](https://ahrefs.com/de/blog/brand-radar-methodology/); [Ahrefs AI share of voice](https://ahrefs.com/blog/ai-share-of-voice/)
- A competitor's critique (Profound) says the dataset leans heavily on AI Overviews and lacks Claude, Meta and Grok. — [Profound review of Brand Radar](https://tryprofound.com/blog/ahrefs-brand-radar-review)

**Scrunch AI**
- Most sources list Core at $250/mo, billed annually, covering about 4 engines, with a 7-day trial. The full set of about 9 engines requires custom Enterprise. QuickSEO lists a $99/mo, 50-prompt entry tier instead. Packaging changed several times in 2026, and on July 16 the pricing page served two different lineups to different visitors. Scrunch was reportedly acquired by Sitecore in June 2026. — [Capterra UK](https://www.capterra.co.uk/software/1077096/Scrunch-AI); [GeoToolbox review](https://geotoolbox.ai/blog/scrunch-ai-review.md); [eClincher](https://www.eclincher.com/articles/scrunch-ai-alternatives); [QuickSEO](https://quickseo.ai/compare/scrunch-ai)

**AthenaHQ**
- Sources conflict. Capterra lists a $95/mo flat self-serve plan with add-on credits. Others report a free "Essential" tier plus a $295/mo plan, or a $295–$499/mo range. — [Capterra](https://capterra.com/p/10030173/AthenaHQ/pricing); [Elite Content Marketer](https://www.elitecontentmarketer.com/best-ai-visibility-tools/); [SEO Counselors](https://seocounselors.com/resources/best-ai-visibility-platform)

**Gumshoe**
- Gumshoe builds buyer personas (user-defined or AI-generated) and runs simulated conversations those personas would have. It reports "persona visibility." Model count conflicts across sources (4 vs 11). — [Debutify, Jun 2026](https://debutify.com/blog/6-best-ai-visibility-tools-for-ecommerce-brands-to-track-llm-mentions); [Fritz.ai](https://fritz.ai/semrush-vs-gumshoe-ai/)
- Pricing is usage-based: about $0.10 per conversation in a 2025 roundup (possibly stale), and "per-audit pricing" in a June 2026 review. I found no official pricing page. — [Nebo Agency](https://www.neboagency.com/blog/entering-the-chat-comparing-the-top-ai-visibility-tools-for-your-brand/); [Debutify](https://debutify.com/blog/6-best-ai-visibility-tools-for-ecommerce-brands-to-track-llm-mentions)
- Gumshoe publicly argues for API-based collection. It says the UI-vs-API gaps found in competitor studies come mostly from default API settings. — [Gumshoe blog (vendor)](https://gumshoe.ai/blog/how-apis-unlock-better-insights-into-ai-search-visibility/)
- Conflict of interest: Gumshoe's co-founder co-authored the SparkToro consistency study (see Section 2).

**HubSpot AI Search Grader (free)**
- Free, needs no account, and works for any brand, including competitors. It gives a one-time check of how ChatGPT, Perplexity and Gemini describe a brand based on their training data. The score out of 100 combines sentiment, presence quality (20), brand recognition (20), share of voice (10) and market competition/position (10). HubSpot sells a separate AEO product for continuous tracking. — [HubSpot AI Search Grader](https://www.hubspot.com/ai-search-grader); [HubSpot AEO Grader](https://www.hubspot.com/aeo-grader)

**SE Ranking / SE Visible**
- SE Ranking's AI Search add-on starts at $89/mo ($71.20/mo annual) and tracks AI Overviews, AI Mode, Perplexity and ChatGPT. It is an add-on to an SE Ranking plan, not standalone. The separate SE Visible product starts at about $79/mo billed annually and covers ChatGPT, Perplexity, AI Mode and Gemini. — [Gracker (competitor)](https://gracker.ai/blog/best-se-ranking-alternatives); [Exploding Topics](https://explodingtopics.com/blog/se-visible-vs-semrush)

**Writesonic GEO**
- Writesonic's own docs list Lite $49/mo ($39 annual), Standard $99 ($79), Professional $249 ($199), Advanced $499 ($399) and Enterprise custom. GEO tracking (brand presence and tracking across ChatGPT, Perplexity and AI Overviews) starts at Professional. Third-party guides use different tier names (Starter $99, Basic $249, Growth $499), with extra users at $50/mo. — [Writesonic docs](https://docs.writesonic.com/docs/different-subscription-plans-of-writesonic); [eesel](https://eesel.ai/blog/writesonic-pricing); [eesel review](https://www.eesel.ai/blog/writesonic-review-2026)

**Data collection method matters (UI scraping vs API)**
- Surfer (sells scraped data) ran 1,000 prompts both ways. ChatGPT's interface cited 12.1 sources per answer versus 3.1 via the API, with only 4.8% domain overlap. A related finding is that the API named 13.8 brands per answer versus 7.9 in the UI. — [Surfer](https://surfer.ai/blog/llm-scraped-ai-answers-vs-api-results/)
- Promptwatch ran the same prompts through both routes on one day and found only 25.6% source overlap. 70% of the sources the UI surfaced never appeared via the API. — [Promptwatch](https://promptwatch.com/blog/ui-vs-api-for-ai-search-visibility)
- Paprik ran 35 prompts over 10 days. The ChatGPT UI surfaced 845 unique brands, the API without web search 135, and the API with web search 580. — [Paprik](https://paprik.ai/blog/accurate-api-based-ai-visibility-tracking-chatgpt-ui)
- Counterpoint from Gumshoe (an API advocate): the interface applies system prompts and settings, so these studies show that *default* API settings differ, "not that APIs cannot replicate interface behavior." Scraping has its own reliability problems: one benchmark excluded a scraping provider (Oxylabs) for falling below a 90% success rate. — [Gumshoe](https://gumshoe.ai/blog/how-apis-unlock-better-insights-into-ai-search-visibility/); [Superlines](https://www.superlines.io/articles/ai-search-visibility-tools-comparison)
- I found no neutral, independent replication of the UI-vs-API comparison. — (search across [Martin Kulawik](https://martinkulawik.de/en/blog/api-vs-scraping-ai-visibility/), [ZeroRank](https://zerorank.ai/blog/data-scraping-vs-api-calls-for-ai-search-visibility), [Growth Method](https://growthmethod.com/ai-visibility-tools/))

### Inferences
- **Summary table (pricing as reported; verify before use):**

| Tool | Cheapest relevant tier | ChatGPT included at entry? | Core metrics | Collection method |
|---|---|---|---|---|
| HubSpot AI Search Grader | Free (one-off) | Yes (+ Perplexity, Gemini) | Sentiment, recognition, SoV, market position | Training-data snapshot |
| Otterly.AI | $29/mo, 15 prompts | Yes | Mentions, citations/sources, SoV, sentiment | Not disclosed in sources |
| Peec AI | ~$95/mo, 50 prompts | Yes (3 models) | Visibility %, position, sentiment, sources | UI scraping (per third parties) |
| Semrush AI Visibility Toolkit | $99/mo per domain (annual) | Yes | Visibility, mentions, sources, prompt research | Clickstream prompt DB + tracked prompts |
| SE Ranking AI add-on / SE Visible | ~$89/mo add-on; ~$79/mo SE Visible | Yes | Mentions, links, AI results | Not disclosed |
| Ahrefs Brand Radar | ~$199/mo per AI index; ~$699 all | Yes (with ChatGPT index) | Mentions, citations, modeled SoV and impressions | Pre-built ~450–490M prompt index + custom prompts |
| Writesonic GEO | ~$199–249/mo (Professional) | Yes | Brand presence, tracking | Not disclosed |
| Scrunch | ~$250/mo (annual) | Yes | Visibility, citations, agent traffic | Not disclosed |
| AthenaHQ | $95 or $295/mo (conflicting) | Yes | Visibility, SoV, citations | Not disclosed |
| Profound | $99/$399 historically; possibly trial + Enterprise only since Sep 2026 | Yes | Visibility, SoV, citations, sentiment, prompt volumes | Front-end capture + consumer panel |
| Gumshoe | Usage-based (~$0.10/conversation, 2025) | Yes | Persona-level visibility | API (vendor-stated preference) |

- For a small agency tracking its own brand plus 2–3 clients, the realistic entry points are Otterly Lite ($29), Peec Starter (~$95) or Semrush's toolkit ($99 per domain, which gets expensive across many client domains). Ahrefs Brand Radar's pre-built index is likely to under-represent a small local agency, because it is seeded from search volume. Its custom-prompt feature is the relevant part for niche brands.
- Results from tools using different collection methods should not be compared directly. If an agency changes tools, the baseline resets.
- Prompt caps (15–150 on entry tiers) are the real constraint. Combined with the variance findings in Section 2, a 15-prompt plan run once a day per engine gives only a coarse signal for any single prompt.

### Gaps
- Could not open any vendor pricing page directly. All prices come from third-party extracts dated roughly March–October 2026, and Profound's current (October 2026) lineup is unresolved.
- Collection methods for Otterly, SE Ranking, Writesonic, Scrunch and AthenaHQ were not stated in the sources I found.
- No independent, peer-reviewed accuracy test of these tools was found. All accuracy comparisons are vendor-produced.
- No CAD pricing was found. Canadian buyers would need to convert USD, and several vendors bill in EUR.

---

## 2. Methodological limits: prompt volume, run-to-run variance, personalization/memory, location — and how many runs are needed

### Takeaway
ChatGPT answers are probabilistic. In the SparkToro/Gumshoe study (Nov–Dec 2025), identical brand lists repeated less than 1 time in 100. Ranking position is therefore meaningless, but "mention rate" (the share of runs in which a brand appears) is reasonably stable when aggregated. No official prompt-volume data exists; every "volume" figure is modeled from Google keywords, clickstream or panels. Simple binomial statistics imply that dozens to 100+ observations per prompt or topic are needed to detect changes smaller than ±10 percentage points. No controlled public study isolates the effects of memory or location.

### Cited Findings
- **SparkToro/Gumshoe study design:** Rand Fishkin (SparkToro) and Patrick O'Donnell (Gumshoe.ai) had about 600 volunteers run 12 prompts a combined 2,961 times (60–100 runs per prompt per platform) through ChatGPT, Claude and Google AI Overviews/AI Mode in November–December 2025. The write-up was published about January 27, 2026. — [Search Engine Journal](https://www.searchenginejournal.com/ai-recommendations-change-with-nearly-every-query-sparktoro/566242/); [Search Engine Land](https://searchengineland.com/ai-recommendation-lists-rarely-repeat-study-468076)
- **Results:** the chance of getting the same brand list twice was under 1 in 100 for ChatGPT and Google AI, and roughly 1 in 1,000 for getting the same list in the same order. Claude was only slightly more consistent. — [Search Engine Journal](https://www.searchenginejournal.com/ai-recommendations-change-with-nearly-every-query-sparktoro/566242/); [PPC Land](https://ppc.land/ai-visibility/)
- **Visibility is steadier than rank:** the 3 most-mentioned brands appeared in an average of 64% of ChatGPT responses, 73% of Claude responses and 68% of Google AI responses. In a headphones test (142 prompts, 994 responses), Bose, Sony, Sennheiser and Apple each appeared in 55–77% of responses. Smaller or tighter categories gave more stable results. — [Communicate Online](https://communicateonline.me/news/ai-brand-recommendations-vary-marketers-warned-on-tracking-tools/); [ASCII](https://ascii.co.uk/news/article/news-20260205-160320ab/study-ai-tools-give-wildly-inconsistent-brand-recommendation)
- Fishkin called tools that report an AI "ranking position" "full of baloney," but accepts visibility percentage aggregated across many prompts and runs. One commentator says he later described broad prompt tracking as a reasonable metric. — [Search Engine Journal](https://www.searchenginejournal.com/ai-recommendations-change-with-nearly-every-query-sparktoro/566242/); [PPC Land](https://ppc.land/ai-visibility/)
- **Caveats:** the study is not peer reviewed, and the authors said neither is a data scientist (per WARC). It used only 12 prompts. Gumshoe sells AI visibility tracking, so it has a commercial interest. — [Communicate Online](https://communicateonline.me/news/ai-brand-recommendations-vary-marketers-warned-on-tracking-tools/)
- **How many runs:** an analysis of the study's figures estimates that one prompt run about 30 times gives roughly an 11-point margin of error, and 100 runs still about 6 points. It argues that spreading a budget across more distinct prompts estimates the whole topic better than repeating one phrasing. — [Befranc newsletter](https://newsletter.befranc.co.uk/p/the-maths-behind-ai-visibility-tracking-and-why-most-of-it-gets-misquoted)
- **Prompt volume is unknown and modeled:** Ahrefs estimates ChatGPT demand as Google volume × 0.115 and says this shows "potential visibility, not actual audience reach." Semrush uses a 317M+ prompt clickstream dataset, and Profound uses an opt-in consumer panel. OpenAI publishes no prompt-volume data (none found). — [Ahrefs methodology](https://ahrefs.com/de/blog/brand-radar-methodology/); [Activepieces](https://www.activepieces.com/blog/ai-visibility-tools-compared-by-plan-caps-2026); [Red Accel](https://www.redaccel.com/blog/ai-visibility-tools-compared/)
- One newsletter argues a visibility score is "only as honest as your prompt index." Others call visibility scores vanity metrics unless tied to traffic or pipeline. — [Stacked GTM](https://newsletter.stackedgtm.ai/p/your-ai-visibility-score-is-only); [Clickport](https://clickport.io/blog/ai-visibility-scores-vanity-metrics)
- **Personalization and memory:** I found no controlled study comparing logged-in and logged-out sessions or isolating location. A vendor (Pepper) recommends auditing in a fresh, logged-out session with one prompt per new chat, because logged-in results reflect the user's memory. It also claims a May 2026 OpenAI memory update widened the personal context ChatGPT draws on (unverified). — [Pepper](https://www.pepper.inc/blog/chatgpt-brand-visibility-audit/)
- Budget, location, team size and stated criteria change what ChatGPT calls "best." Natural run-to-run variance means different answers alone don't prove personalization; testing needs a neutral control. — [MaxAEO](https://maxaeo.ai/blog/chatgpt-personalize-recommendations/); [geoSurge](https://www.geosurge.ai/corpus/gen-3019/chatgpt/chatgpt-memory-and-personalized-brand-recommendations.html)
- **Platform changes shift baselines:** after a May 2026 ChatGPT change that made brand links more prominent, Similarweb reportedly saw the homepage share of ChatGPT referrals rise from about 26–29% to about 62–63%, and total ChatGPT referrals rise 157.7% week over week. — [Cognizo (citing Similarweb)](https://www.cognizo.ai/blog/chatgpt-ai-visibility-statistic)

### Inferences
- My own binomial math (95% CI ≈ ±1.96·√(p(1−p)/n)) shows how the margin depends on the true mention rate. For a brand mentioned about 10% of the time: about ±11 points at 30 runs and about ±6 at 100 runs, matching the newsletter. For a brand mentioned about 50% of the time: about ±18 points at 30 runs and about ±10 at 100. A small agency should therefore treat month-over-month changes of under about 10–15 points as noise unless it has 100+ observations per measured topic.
- Repeated runs of the same prompt in the same session are not independent. Fresh chats (or Temporary Chat / logged-out sessions) are needed for each observation.
- For local or service businesses, location strongly shapes answers ("best web agency in Montreal"). Prompts should state the location explicitly rather than rely on IP-based location, so runs are reproducible.

### Gaps
- No peer-reviewed study on run-to-run variance in AI recommendations was found. The SparkToro study remains the main reference and has the caveats above.
- No published controlled test of how memory, account history or IP location affect ChatGPT vendor recommendations.
- No official ChatGPT prompt-volume data. All volume figures are modeled.

---

## 3. Does OpenAI provide any official analytics for publishers or businesses?

### Takeaway
No. As of October 2026 I found no OpenAI analytics dashboard for publishers or businesses showing organic mentions, impressions or referrals. The only official mechanisms are the automatic `utm_source=chatgpt.com` tag on outbound links (documented in OpenAI's Publishers & Developers FAQ) and, for paid placements, ChatGPT Ads Manager reporting (2026). OpenAI does not share organic mention data. Tracking also broke for about a week in October 2026 after the GPT-6 rollout.

### Cited Findings
- OpenAI's Publishers and Developers FAQ says ChatGPT automatically adds `utm_source=chatgpt.com` to referral URLs, so publishers who allow OAI-SearchBot can track ChatGPT referrals in tools such as Google Analytics. — [OpenAI Help Center](https://help-lb.openai.com/en/articles/12627856-publishers-and-developers-faq)
- ChatGPT adds no `utm_medium`, so tagged visits can land as "Unassigned" rather than "Referral" in GA4's default grouping. In June 2025 the tag was extended from citation links to links in the "More"/Sources panel. — [Clickport](https://clickport.io/blog/chatgpt-direct-traffic-ga4); [PPC Land](https://ppc.land/chatgpt-adds-utm-parameters-to-more-links-for-better-analytics-tracking/)
- **October 2026 tracking outage:** ChatGPT stopped appending `utm_source=chatgpt.com` from about October 8 (around 2pm PT) until a fix began rolling out about 2am PT on October 15, 2026. The timing coincided with the GPT-6 rollout. Inline answer links were hit hardest; Sources-panel and shopping links kept the tag. — [Relevant Audience](https://www.relevantaudience.com/analytics/chatgpt-utm-tag-bug-fixed-openai-confirmed-adobe/); [SE Roundtable](https://www.seroundtable.com/utm-parameters-missing-chatgpt-42299.html); [Search Engine Land, Oct 20 2026](https://searchengineland.com/chatgpt-appears-to-drop-utm-tracking-making-ai-referral-traffic-harder-to-measure-496552)
- Adobe's Cedric Huesler reported that on about 500 pages, ChatGPT visits fell about 31k/day while Direct rose about 26k/day. By 9am PT on October 15, tagged clicks were back to about 95–100% of the prior week. ChatGPT opens links with `noopener,noreferrer`, so the referrer is still missing on most clicks and the UTM is the signal to count. He advises annotating October 8–15 in GA4 rather than rebuilding attribution models. — [Relevant Audience](https://www.relevantaudience.com/analytics/chatgpt-utm-tag-bug-fixed-openai-confirmed-adobe/); [Scalevise](https://scalevise.com/resources/chatgpt-utm-bug-fix-ga4-attribution/); [TechWyse](https://www.techwyse.com/?p=79758)
- Sources conflict on whether OpenAI confirmed the bug. Some say OpenAI confirmed it on October 14 (secondhand); others say OpenAI made no public statement and its release notes don't mention it. — [Relevant Audience](https://www.relevantaudience.com/analytics/chatgpt-utm-tag-bug-fixed-openai-confirmed-adobe/); [Eva](https://eva.guru/answers/did-my-chatgpt-traffic-drop-or-lose-its-tracking/)
- **ChatGPT Ads (paid):** Ads Manager reports impressions, clicks, CTR, CPC, CPM and spend. A Conversions API and pixel reportedly shipped in May 2026 with configurable attribution windows. OpenAI does not share organic-mention impression share, prompts or demographics. — [Adventure PPC](https://www.adventureppc.com/blog/10-chatgpt-ads-reporting-metrics-every-advertiser-must-track-in-2026); [Thrad](https://www.thrad.ai/content/measuring-ai-assistant-ad-performance-honestly); [Top Growth Marketing](https://topgrowthmarketing.com/?p=40405)
- Early ChatGPT ads benchmarks (vendor-reported): pilot CTR about 0.91% vs about 6.4% for Google Search. Adthena counted 7,378 distinct ChatGPT advertisers across 3 markets in the week of July 13–20, 2026. Swydo added ChatGPT Ads to its reporting integrations in July 2026. — [Thrad](https://www.thrad.ai/content/chatgpt-ads-roi-what-the-early-data-actually-shows); [PPC Land](https://ppc.land/adthena-counts-7-378-chatgpt-advertisers-as-placements-grow-97x-in-a-quarter/); [Swydo changelog](https://changelog.swydo.com/152655-make-chatgpt-ads-part-of-your-marketing-reports)
- **Commerce:** Instant Checkout launched September 29, 2025 with Stripe on the Agentic Commerce Protocol. Reportedly, by March 2026 OpenAI had moved merchants back to their own checkout, with ChatGPT focused on discovery. I found no merchant analytics dashboard. — [PPC Land](https://ppc.land/openai-launches-instant-checkout-for-chatgpt-with-stripe-partnership/); [Naturaily](https://naturaily.com/blog/agentic-commerce-shopify-guide)
- One roundup cites Cloudflare Radar putting OpenAI's crawl-to-referral ratio at about 425:1, a reminder that bot crawls in server logs far outnumber human referrals. — [Mean CEO blog (secondary)](https://blog.mean.ceo/chatgpt-referral-traffic-statistics/)

### Inferences
- For a small agency's own brand, "official" ChatGPT data means the UTM-tagged sessions in its own analytics and nothing more. Every visibility or mention metric comes from third-party sampling.
- Tracking dependent on a single UTM parameter is fragile. Any October 2026 month-over-month report needs an annotation for October 8–15.

### Gaps
- Could not read OpenAI's help-center page in full to check for newer analytics announcements. No official OpenAI source in the results described a publisher or business analytics product in 2025–2026.
- No information found on whether ChatGPT's Ads Manager is open to small Canadian advertisers or what its minimum spend is.

---

## 4. Tracking ChatGPT referral traffic and leads in GA4, other analytics, and CRM

### Takeaway
GA4 added a native "AI Assistant" channel on May 13, 2026 (medium `ai-assistant`). It is not retroactive and its referrer list is unpublished. Agencies should still build a custom channel group with a domain-anchored regex for history and for completeness, and segment on `utm_source=chatgpt.com`. A meaningful share of AI-influenced visits arrives as Direct or branded search ("dark" AI traffic). A required "How did you hear about us?" field with a "ChatGPT / AI assistant" option plus free text is the main way to capture that influence in the CRM.

### Cited Findings
- **Native GA4 channel:** Google added "AI Assistant" to the Default Channel Group on May 13, 2026. It needs no setup. Recognized assistant referrals get medium `ai-assistant` and campaign `(ai-assistant)`. Google names ChatGPT, Gemini and Claude as examples but hasn't published the full list. The channel is not retroactive, and many properties only saw it populate around mid-June 2026. — [Semrush News](https://www.semrush.com/blog/ga4-adds-ai-assistant-channel/); [TechWyse](https://www.techwyse.com/news/platform-updates/google-analytics-ai-assistant-channel-ga4-default-channel-group); [GA Optimizer](https://www.gaoptimizer.com/blog/ga4-ai-assistant-channel/); [Zeevron](https://www.zeevron.com/insights/ga4-ai-assistant-channel)
- Known gaps in the native channel: referrer-less traffic (many mobile apps, copied links) still lands in Direct, and Google AI Overviews and AI Mode are classified as Organic Search. — [Zeevron](https://www.zeevron.com/insights/ga4-ai-assistant-channel); [TryAivo](https://www.tryaivo.com/blog/ga4-ai-assistant-channel)
- **Custom channel group:** create an "AI" channel using a regex on session source, placed above "Referral" because GA4 assigns sessions to the first matching rule. A domain-anchored example is `chatgpt\.com|chat\.openai\.com|openai\.com|perplexity\.ai|claude\.ai|gemini\.google\.com|copilot\.microsoft\.com|edgeservices\.bing\.com`. Loose patterns such as `.*claude.*` can catch unrelated sites. — [Loves Data](https://www.lovesdata.com/blog/how-to-track-ai-traffic-ga4/); [Terminus](https://www.terminusapp.com/blog/ai-traffic-channel-in-ga4/); [Passionfruit](https://www.getpassionfruit.com/blog/how-to-track-ai-search-referrals-in-ga4-regex-channel-groups-bigquery-and-looker-studio)
- Sources conflict on whether custom channel groups apply retroactively to historical data. Some guides say yes, others say no but suggest Explorations. — [Savvy](https://savvy.co.il/en/blog/wordpress-seo/track-ai-traffic-google-analytics-4/); [MeasureU](https://measureu.com/resources/ai-channel-grouping/)
- Practitioners report the referrer is stripped from inline links for free ChatGPT users. Mobile app taps and copy-paste arrive as Direct, so ChatGPT is undercounted. OpenAI has not documented this. — [Clickport](https://clickport.io/blog/chatgpt-direct-traffic-ga4); [SearchPilot](https://www.searchpilot.com/resources/blog/how-does-ai-traffic-show-up-in-analytics)
- Ahrefs warns that "not all traffic from AI assistants is being recorded properly," and that AI Overviews/AI Mode clicks count as Search, so AI's share is understated. — [Ahrefs AI vs search benchmark](https://ahrefs.com/benchmarks/ai-vs-search)
- One measurement guide recommends keeping three separate measures: human referrals in analytics, likely no-click "dark" influence, and crawler requests in server logs. — [Trakkr](https://trakkr.ai/ai-search-traffic)
- **Self-reported attribution:** ask leads directly with a "How did you hear about us?" field and store the answer as lead source. Recommended practice is a required picklist (including "AI search/chat") paired with a free-text question such as "What made you decide to reach out now?" — [LeadJourney glossary](https://leadjourney.io/glossary/self-reported-attribution); [Prose Media](https://www.prosemedia.com/blog/marketing-attribution-2026-ga4-crm); [Growthspree playbook](https://www.growthspreeofficial.com/blogs/build-b2b-saas-self-reported-attribution-system-playbook-2026)
- One vendor blog (unverified, no primary source) claims AI search platforms now account for 12–22% of B2B self-reported attribution responses, up from 2–4% in 2024, and that 40–60% of buyers answer when the field is mandatory. It cites 6sense without a link. — [Growthspree](https://www.growthspreeofficial.com/blogs/dark-funnel-pipeline-impact-benchmarks-b2b-saas-b2b-2026-hidden-pipeline-acv-vertical-channel)
- AI recommendations "do not produce trackable click events" when a buyer reads the recommendation and later types the URL or searches the brand. — [Growthspree playbook](https://www.growthspreeofficial.com/blogs/build-b2b-saas-self-reported-attribution-system-playbook-2026)

### Inferences
- **Practical setup for a small agency (synthesis of the above):**
  1. Keep the native AI Assistant channel, and add a custom channel group "AI Assistants" with the anchored regex, placed above Referral, for gap coverage and history.
  2. Create a GA4 segment or exploration on `session source = chatgpt.com`, including source/medium `chatgpt.com / (not set)`, to catch UTM-tagged but Unassigned sessions.
  3. Mark form submits and booked calls as key events, and compare key-event rate by channel.
  4. Pass first-touch source and medium (from UTM or referrer) into hidden form fields so the CRM (e.g., HubSpot) stores them on the contact.
  5. Add a required "How did you hear about us?" dropdown with options such as "ChatGPT," "Other AI assistant (Gemini, Claude, Perplexity, Copilot)," "Google search," "Referral," "LinkedIn," "Other," plus an optional "Which question did you ask?" free-text field to learn the actual prompts.
  6. Track branded search impressions and clicks in Google Search Console and Direct traffic as proxy signals for "dark" AI influence. Annotate known outages (Oct 8–15, 2026) and platform changes (May 2026 link change).
- Self-reported "ChatGPT" answers will likely exceed tracked ChatGPT sessions, given referrer stripping and buyers who read a recommendation and then search the brand. The gap between the two is itself a useful metric.

### Gaps
- Couldn't confirm the full list of referrers GA4's native AI Assistant channel recognizes, or whether it reads `utm_source=chatgpt.com` when no referrer is present.
- No rigorous study quantifying "branded search lift" caused by AI mentions was found.
- No primary 6sense or TrustRadius data on self-reported AI attribution was found.

---

## 5. Benchmarks: share of traffic from ChatGPT/AI and conversion rates vs organic

### Takeaway
AI assistants still send a small share of total website traffic: about 0.4% across 115k sites in Ahrefs' live benchmark (to September 2026). ChatGPT dominates AI referrals, but its share is falling as Gemini and Claude grow. On conversion, the most credible multi-site estimate is Siege Media's 78-site median of about 1.26× organic (Jan–May 2026), not the 4–23× figures from single sites. Adobe's retail data shows AI visitors converting 42–54% better than non-AI traffic in 2026, while travel lagged until mid-2026. Volume is tiny: one 63-site dataset found AI delivered about 3.2 conversions for every 100 from organic.

### Cited Findings

**Traffic share**
- Ahrefs live benchmark (115,254 sites; window June 2025–September 2026; updated October 8, 2026): AI assistants delivered 5.3M visits, 0.43% of traffic, vs about 26.8% for search overall and about 24% for Google. — [Ahrefs AI vs Search benchmark](https://ahrefs.com/benchmarks/ai-vs-search)
- Earlier Ahrefs studies: about 35K sites showed AI at 0.1% of referral traffic. An 81,947-site update found AI traffic up about 10× year over year but still under 1%. Ahrefs' own site gets about 0.5% of its traffic from AI search. — [Ahrefs blog](https://ahrefs.com/blog/ai-traffic-research); [Ahrefs](https://ahrefs.com/blog/ai-traffic-increase/); [Ahrefs AI conversions](https://ahrefs.com/blog/ai-search-traffic-conversions-ahrefs/?app=1)
- Similarweb (via secondary sources): ChatGPT accounted for about 53% of worldwide generative-AI web traffic in 2026, down from about 76% a year earlier, with Gemini above a quarter. All AI referrals totaled about 1.13B in June 2025 vs about 191B for Google. — [Similarweb gen-AI stats](https://www.similarweb.com/blog/marketing/geo/gen-ai-stats/); [RankStudio PDF](https://rankstudio.net/articles/en/pdfs/chatgpt-referral-traffic-2026.pdf)
- Share of AI referrals conflicts by population. One roundup attributes a 95.1% ChatGPT share to BrightEdge. Goodie's B2B panel says ChatGPT's share of B2B AI referrals fell from 89% to 62.6%, with Claude at 18.5%. Goodie is an AI visibility vendor. — [Mean CEO (secondary)](https://blog.mean.ceo/chatgpt-referral-traffic-statistics/); [Goodie](https://higoodie.com/blog/ai-search-traffic-report-2026/)
- Adobe: retail AI-referred visit share up 393% YoY in Q1 2026 and travel up 233%. In July 2026, travel was +119% YoY, retail +62% and financial services +31%. Adobe's dataset covers over 1 trillion visits. — [Adobe Q2 2026 report (PDF)](https://business.adobe.com/resources/sdk/.2026-q2-ai-traffic-report/q2-2026-adi-ai-sourced-traffic-insights.pdf); [Adobe Aug 2026 report (PDF)](https://business.adobe.com/assets/pdfs/resources/sdk/ai-traffic-trends-report-august-2026/ai-traffic-trends-report-2026-08-19.pdf)

**Conversion**
- **Siege Media (78 GA4 sites, Jan–May 2026):** the median AI-to-organic conversion ratio was 1.26×, and AI matched or beat organic on 72% of sites. By vertical, the premium ran from 1.01× in ecommerce to 1.67× in finance. The study used GA4 session key-event rate and included only sites with ≥250 AI sessions and ≥1,000 organic sessions. Siege is an agency (self-published), and it disputes Similarweb's 7.1% AI conversion-rate claim. — [Siege Media](https://www.siegemedia.com/?p=45564); [SEO Works summary](https://www.seoworks.co.uk/downloads/ai-referral-traffic-benchmark/)
- **63-site dataset:** for every 100 conversions from organic search, AI referrals delivered 3.2. AI conversion rate was 0.67× paid search, 1.18× organic, 1.37× all sessions and 2.48× direct. The baseline choice changes the headline. — [SEO Works](https://www.seoworks.co.uk/downloads/ai-referral-traffic-benchmark/)
- A 96-million-session study reported AI-referred visits converting at 1.27% vs 1.09% for organic (+25%). Another large study found organic outperforming ChatGPT referrals by 13%. — [Relevant Audience](https://www.relevantaudience.com/seo/why-chatgpt-traffic-converts-worse-than-google-search/); [CiteProof](https://citeproof.co/blog/llm-traffic-conversion-rate)
- **Adobe (retail, vs all non-AI traffic, not organic specifically):** AI visitors converted 42% better in March 2026 and 54% better in May 2026, with 53% higher revenue per visit. Travel AI traffic converted 28% worse in May 2026, a gap that narrowed to about 1% by July 2026. AI visitors are more engaged and bounce less. — [Adobe Q2 2026 report](https://business.adobe.com/resources/sdk/.2026-q2-ai-traffic-report/q2-2026-adi-ai-sourced-traffic-insights.pdf); [Adobe Aug 2026 report](https://business.adobe.com/assets/pdfs/resources/sdk/ai-traffic-trends-report-august-2026/ai-traffic-trends-report-2026-08-19.pdf); [Digital Applied](https://www.digitalapplied.com/blog/ai-traffic-converts-42-percent-better-2026-channel-strategy)
- Shopify reportedly says AI-referred sessions convert at nearly 50% higher rates than organic on product detail pages (secondary). — [SEO Works](https://www.seoworks.co.uk/downloads/ai-referral-traffic-benchmark/)
- **Single-site outliers:** Ahrefs says AI visitors converted 23× better than organic on its own site, with AI at only 0.5% of traffic. Seer Interactive's client case study (late 2024 to spring 2025) found ChatGPT at about 15.9% conversion vs 1.76% for Google organic. — [Ahrefs](https://ahrefs.com/blog/ai-search-traffic-conversions-ahrefs/?app=1); [Seer Interactive](https://www.seerinteractive.com/insights/case-study-6-learnings-about-how-traffic-from-chatgpt-converts)
- Commonly repeated "4.4×" claims trace back to vendor content (e.g., Semrush's 2025 projection). Opollo reports about 5× for B2B. — [Emarketed](https://emarketed.com/aeo/ai-referral-traffic-conversion-value-2026/); [Marshal](https://www.runmarshal.com/field-notes/ai-search-traffic-is-4x-more-valuable-than-organic); [Siege Media](https://www.siegemedia.com/?p=45564)

### Inferences
- **Skeptical reading:** the higher conversion rate is consistent across sources, but most of the premium likely reflects self-selection. AI-referred visitors arrive after shortlisting, often on branded or high-intent pages, and the numbers are small. Single-site figures (23×, 9×) come from vendors with products to sell and should not be used as planning assumptions.
- For a small agency's business case, a defensible assumption is: AI referrals ≈ 0.2–1% of sessions, converting roughly 1–1.7× organic. Value is better captured by self-reported attribution in the CRM than by GA4 sessions alone.
- B2B services (like agencies) are closer to "finance/B2B" than ecommerce in Siege's vertical split, which suggests the premium could sit at the higher end. This is unproven for agencies specifically.

### Gaps
- Could not read Siege Media's full methodology (blocked). No agency- or professional-services-specific conversion benchmark was found.
- The original sources behind the "96-million-session" and "organic beats ChatGPT by 13%" studies were not identifiable from the extracts.
- Similarweb's own report giving AI referrals as a share of total web traffic was not accessed directly.

---

## 6. ChatGPT usage scale in 2026 and how often people use it to find vendors and service providers

### Takeaway
ChatGPT had 900M weekly active users as of OpenAI's February 2026 announcement. Reports in July 2026 said it was nearing 1B, but I found no official October 2026 figure. ChatGPT is still small next to Google in query share (Google about 74% of US desktop searches in Q4 2025), yet it has become a primary starting point for B2B vendor research. In G2's March 2026 survey, 51% of software buyers started in an AI chatbot more often than a search engine. BrightLocal's 2026 survey (via secondary sources) found 31% of US consumers used ChatGPT for a business recommendation in the past year.

### Cited Findings
- OpenAI announced 900M weekly active users and 50M paying subscribers on February 27, 2026, up from 800M in October 2025. — [TechCrunch](https://techcrunch.com/2026/02/27/chatgpt-reaches-900m-weekly-active-users); [9to5Mac](https://9to5mac.com/2026/02/27/chatgpt-approaching-1-billion-weekly-active-users/)
- The Information (late July 2026, citing internal data) reported ChatGPT was "on the precipice" of 1B WAU, seven months later than OpenAI had projected. There is no official confirmation. A Bloomberg Law item (July 31, 2026) headlined "more than 1 billion users, 2 million businesses" is ambiguous about the metric. — [The Information](https://feature.theinformation.com/articles/openais-chatgpt-nears-1-billion-weekly-active-users-seven-months-target); [Bloomberg Law](https://news.bloomberglaw.com/artificial-intelligence/openai-has-more-than-1-billion-users-2-million-businesses); [CityBiz](https://www.citybiz.co/article/880897/openai-nears-1-billion-weekly-chatgpt-users-as-ipo-plans-advance/)
- **Search share:** a SparkToro/Datos study (March 2, 2026; US desktop only, 41 domains, Q4 2025) found Google at 73.7% of desktop searches, with ChatGPT reaching 40.47% of US desktop devices. One summary says AI tools were about 3.2% of searches, which I could not verify. A Similarweb-based Graphite analysis claims AI is 56% of global and 34% of US "search volume," which conflicts sharply with Datos because the methods differ. The Datos study excludes mobile. — [PPC Land](https://ppc.land/google-holds-73-7-of-desktop-searches-chatgpt-is-smaller-than-you-think/); [AI Search Decoded](https://aisearchdecoded.substack.com/p/how-big-is-ai-search-really); [QuickSEO](https://quickseo.ai/blog/chatgpt-vs-google-search-in-2026-market-share-user-data-what-it-means-for-seo)
- **G2 "The Answer Economy" 2026 AI Search Insight Report** (1,076 B2B software buyers, March 2026; press release April 15, 2026):
  - 51% now begin software research in an AI chatbot more often than a search engine, up from 29% in April 2025.
  - 69% chose a different vendor than they initially planned based on chatbot guidance, and about one-third bought from a vendor they had never heard of.
  - AI chatbots are the #1 source influencing shortlists, and review-site citations are the #1 signal that makes buyers trust a chatbot recommendation.
  - Sources: [G2 report](https://learn.g2.com/g2-2026-ai-search-insight-report); [PR Newswire via Morningstar](https://www.morningstar.com/news/pr-newswire/20260415cg34275/new-g2-research-half-of-b2b-software-buyers-now-start-their-research-with-ai-chatbots)
- A secondary summary attributes to G2 a figure that ChatGPT holds 62% of B2B software buyers' chatbot usage in 2026 (up from 47%), with Gemini at 14%. I could not confirm this in G2's text. G2 is a review platform with an interest in emphasizing review-site influence. — [QuickSEO](https://quickseo.ai/blog/b2b-buyers-ai-chatbot-research-2026-stats)
- **Forrester, State of Business Buying 2026** (survey of about 18,000 buyers): Forrester describes genAI search as a starting point for B2B buyers. A "94% of buyers use AI" figure appears only in secondary coverage, and Forrester's release uses 94% for a different stat. Forrester's 2026 predictions say 19% of buyers using AI apps feel less confident because of inaccurate information, and that in 2025, 30% viewed genAI as a meaningful interaction in the final commit stage. — [Forrester press release](https://www.forrester.com/press-newsroom/forrester-2026-the-state-of-business-buying/); [Digital Commerce 360](https://digitalcommerce360.com/2026/01/22/forrester-b2b-buying-ai-2026/); [Business Wire](https://www.businesswire.com/news/home/20251028458309/en/Forrester%E2%80%99s-2026-B2B-Marketing-Sales-And-Product-Predictions-B2B-Companies-Will-Lose-More-Than-10-Billion-Because-Of-Ungoverned-Use-Of-Generative-AI); [Let's Data Science (secondary)](https://letsdatascience.com/news/buyers-tighten-validation-of-ai-driven-insights-3c2f9f55)
- Gartner is cited secondarily as finding that 45% of buyers used AI during a recent purchase, and that 68% of buyers have a front-runner in mind at the start (attribution unclear). — [Revenue Experts](https://revenueexperts.beehiiv.com/p/ai-chatbots-changing-b2b-vendor-choice-69-pick-different-companies); [Reechee](https://reechee.io/blog/state-of-b2b-software-buying/)
- **BrightLocal 2026 Local Consumer Review Survey** (US, n=1,002; via secondary summaries): use of AI tools to find local services rose from 6% to 45% in about a year. 31% used ChatGPT for a business recommendation in the past 12 months, and 23% used Google AI Mode. 42% trust AI recommendations about as much as reviews, and 97% of AI users at least sometimes verify against reviews. — [IPS News](https://ipsnews.net/business/2026/04/23/why-ai-search-is-replacing-google-for-local-business-discovery/); [Cloutly](https://cloutly.com/blog/ai-search-statistics/); [BrightLocal](https://www.brightlocal.com/?p=132601)

### Inferences
- The audience is large and buyer behavior has shifted in shortlisting, even though click volume to websites stays small (Section 5). For an agency, the value of ChatGPT visibility is mostly "being on the shortlist" (influence), with a minority showing up as tracked clicks. This supports self-reported attribution as the primary business metric.
- G2's sample is software buyers, not buyers of agency services. Applying it to agency selection is an extrapolation.
- Review-site citations (G2 finding) and reviews being checked (BrightLocal) suggest an agency should monitor which third-party sources (Clutch, Google reviews, directories) ChatGPT cites, which tools with citation-source reports can show.

### Gaps
- No official OpenAI weekly-active-user figure later than February 2026 was found.
- No 6sense or TrustRadius 2026 data surfaced in searches. Forrester's adoption percentage could not be confirmed from the primary source.
- No survey specific to how businesses find marketing or digital agencies via ChatGPT was found.
- BrightLocal figures come from secondary summaries; the primary report was not accessed.

---

## 7. A do-it-yourself tracking method for a small agency without paid tools

### Takeaway
A credible DIY setup has four parts:
- **Prompt panel:** a fixed panel of about 20–30 buyer-intent prompts, run in fresh logged-out or temporary sessions with the location stated in the prompt, about 3–5 runs per prompt each month. Log results in a spreadsheet and report the mention rate (% of runs where the agency appears), not rank.
- **Analytics:** GA4's AI Assistant channel plus a custom regex channel group.
- **CRM:** a required "How did you hear about us?" field with a ChatGPT option.
- **Baselines:** the free HubSpot AI Search Grader for an occasional snapshot, and Otterly Lite ($29/mo) if automation becomes worthwhile.

### Cited Findings
- Report mention rate across many runs, not position. Rank is unreliable, while visibility percentage aggregated over runs is defensible. — [Search Engine Journal (SparkToro study)](https://www.searchenginejournal.com/ai-recommendations-change-with-nearly-every-query-sparktoro/566242/); [PPC Land](https://ppc.land/ai-visibility/)
- Audit in a fresh, logged-out session with one prompt per new chat, scoring mention rate, recommendation rate and sentiment. — [Pepper](https://www.pepper.inc/blog/chatgpt-brand-visibility-audit/)
- Spread runs across more distinct prompts to estimate a topic rather than one phrasing. A single prompt needs about 30 runs for about an 11-point margin of error. — [Befranc newsletter](https://newsletter.befranc.co.uk/p/the-maths-behind-ai-visibility-tracking-and-why-most-of-it-gets-misquoted)
- Stating criteria such as location and budget in the prompt yields tailored answers even when logged out. Use a neutral control when testing personalization. — [MaxAEO](https://maxaeo.ai/blog/chatgpt-personalize-recommendations/)
- UI answers differ from API answers, so a DIY panel run in the ChatGPT interface reflects what prospects see better than a cheap API script does. — [Surfer](https://surfer.ai/blog/llm-scraped-ai-answers-vs-api-results/); [Paprik](https://paprik.ai/blog/accurate-api-based-ai-visibility-tracking-chatgpt-ui)
- Free and low-cost options: HubSpot AI Search Grader (free; ChatGPT, Perplexity and Gemini sentiment/SoV snapshot); Otterly Lite ($29/mo, 15 prompts, 4 engines). — [HubSpot](https://www.hubspot.com/ai-search-grader); [Rework](https://resources.rework.com/tools/aeo-ai-visibility/best-otterly-alternatives)
- GA4's native AI Assistant channel (since May 13, 2026) plus a custom regex group cover referral tracking at no cost. — [Semrush News](https://www.semrush.com/blog/ga4-adds-ai-assistant-channel/); [Loves Data](https://www.lovesdata.com/blog/how-to-track-ai-traffic-ga4/)
- Ahrefs publishes a 7-step guide to tracking ChatGPT visibility (vendor). — [Ahrefs](https://ahrefs.com/blog/chatgpt-visibility-tracking/)

### Inferences
- **Suggested DIY protocol (my synthesis; not from a single source):**
  1. **Build the panel (25 prompts).** Group prompts by intent:
     - about 10 category/local ("best digital marketing agency in [city]", "who builds Shopify stores in [city]")
     - about 6 service-specific ("agency for Google Ads for a dental clinic in [province]")
     - about 4 comparison ("[agency] vs [competitor]")
     - about 3 brand-knowledge ("what do you know about [agency]?")
     - about 2 problem-led ("my website gets no leads, who can help in [city]?")

     Write the location into the prompt. Freeze the wording, and record prompt version changes.
  2. **Run conditions.** Use a logged-out ChatGPT session or Temporary Chat (memory off), one prompt per new chat, and the default model. Optionally add one run with search explicitly triggered. Record the date, model shown and mode.
  3. **Frequency.** Run each prompt 4 times per month (e.g., weekly), giving 100 observations per month for the panel. Optionally repeat a 10-prompt subset in Gemini, Perplexity, Claude and Copilot monthly.
  4. **Spreadsheet columns:** date, engine and model, prompt ID, run #, agency mentioned (Y/N), recommended or just listed, position (informational only), sentiment (+/0/−), accuracy issues (wrong services or location), competitors named, URLs and sources cited (especially Clutch, Google Business Profile, directories, Reddit), and a screenshot link.
  5. **Monthly KPIs:**
     - mention rate overall and by prompt group
     - share of voice vs 3–5 named competitors (your mentions ÷ all tracked-brand mentions)
     - citation-source frequency
     - GA4 AI Assistant sessions and key events
     - CRM leads reporting "ChatGPT/AI"
     - branded search impressions (Search Console)
  6. **Interpretation rule.** With about 100 observations per month, treat changes under about ±10 points as noise (binomial margin, Section 2). Use quarter-over-quarter trends.
  7. **Time cost.** 100 runs at about 1–2 minutes each is roughly 2–3 hours per month per brand. If that is too much for several clients, Otterly Lite or Peec Starter automate it.
- Prospects' real prompts captured in the CRM free-text field ("What did you ask ChatGPT?") should feed back into the panel, which partly compensates for the lack of prompt-volume data.

### Gaps
- No published, validated DIY protocol (e.g., an academic or standards-body method) was found. The protocol above is a synthesis.
- No data on whether Temporary Chat or logged-out results differ systematically from logged-in results with memory, for vendor recommendations.
