# How ChatGPT Finds, Selects, and Cites Sources and Businesses for Recommendation Queries (state as of October 2026)

> **Method note for the report writer.** In this session WebFetch failed with DNS errors on every domain I tried (platform.openai.com, developers.openai.com, help.openai.com, peec.ai, ahrefs.com). All findings below come from search-engine result summaries and snippets of the cited pages, not full-page reads. Exact numbers should be spot-checked against the original page before they appear in client-facing material. Evidence tiers used throughout: **[OFFICIAL]** = OpenAI or Microsoft first-party; **[LARGE-SAMPLE]** = study with a stated sample in the thousands or more (almost all vendor-funded); **[SMALL/ANECDOTAL]** = small-n test, case study or marketing blog; **[PREPRINT]** = arXiv, not peer reviewed. Almost nothing in this space is peer reviewed. Most "studies" come from companies that sell AI-visibility tracking or GEO services (Peec AI, Ahrefs Brand Radar, Semrush, Gumshoe, Otterly, Graphite, Loudface, Steady Demand, etc.), which have a commercial interest in showing that AI visibility is measurable and can be influenced.

## 1. When does ChatGPT answer from training data versus run a live web search?

### Takeaway
OpenAI says only that ChatGPT searches "automatically" when a question would benefit from current information, and that users can force a search. It publishes no trigger rules or rates. Practitioner tests agree that "best X" or discovery-style recommendation prompts trigger search far more often than informational prompts (roughly 50-75% versus 10-20%). The overall search rate swings widely by interface, model and login state, so a "best digital agency in Canada" prompt will often, but not always, be grounded in live search. When it isn't, the answer comes from the model's training-data priors.

### Cited Findings
- [OFFICIAL] OpenAI's help center says ChatGPT may search the web automatically when a question would benefit from current information, and users can also start a search manually. — [OpenAI Help: Searching the web with ChatGPT](https://help.openai.com/en/articles/9237897-chatgpt-search)
- [SMALL] In a 400-query test in the ChatGPT UI, AI+Automation found discovery prompts ("best X") triggered search 73% of the time versus 10% for informational prompts such as "What is a CRM?". Comparison prompts triggered search 100% of the time in an earlier 24-query API test but only 29% in the 400-query UI test, which shows the trigger depends on the surface. — [AI+Automation: How Often Does ChatGPT Trigger a Web Search? 400 Queries](https://aiplusautomation.com/blog/when-does-chatgpt-search)
- [LARGE-SAMPLE, vendor] Nectiv's October 2025 analysis (as relayed by others) reported a 53.5% search rate for commercial-intent prompts versus 18.7% for informational ones, and about 31% overall. — [Otterly: How often does ChatGPT trigger a Web Search? (2026 Data)](https://otterly.ai/blog/how-often-does-chatgpt-trigger-a-web-search/); [Graphite Five Percent: Do Not Force Search in Prompt Tracking](https://graphite.io/five-percent/research/do-not-force-search-prompt-tracking)
- [LARGE-SAMPLE, vendor] A Semrush analysis of about 80 million queries reportedly found that only about 46% trigger a live web search. This is secondhand; I did not see the Semrush original. — [Otterly summary](https://otterly.ai/blog/how-often-does-chatgpt-trigger-a-web-search/)
- [vendor] Graphite reported that logged-out ChatGPT showed evidence of using the web search tool in 58% of responses (early August 2026) when search was not forced. Its own tracking of one commercial prompt ("best texting service") found search in 31% of responses. Graphite warns that prompt-tracking tools which force search misstate what real users see. — [Graphite: Do Not Force Search in Prompt Tracking](https://graphite.io/five-percent/research/do-not-force-search-prompt-tracking)
- [PREPRINT] A September 2026 arXiv paper (Tannenbaum) models brand visibility as two paths. One is a live-retrieval path (real demand, then page fit, then search/fan-out, then evidence exposure, then final selection). The other is a "prior-compatible" path in which a brand is mentioned without any observed citation, meaning it comes from parametric memory. — [arXiv 2609.23162: From Prompt to Recommendation: A Fitted Stage Model of Brand Visibility in AI Search](https://arxiv.org/pdf/2609.23162)

### Inferences
- "Best digital agency in Canada" and "top web design agency in [city]" are textbook discovery/commercial prompts, which are the class most likely to trigger search. A meaningful share of runs (likely 25-50%, depending on surface and model) may still answer from parametric memory. Agencies therefore need both (a) presence in retrievable web sources and (b) enough historical web footprint to be in the model's priors.
- Rates measured by tools that force search, or that use the API instead of the consumer UI, overstate how often real users get search-grounded answers.

### Gaps
- OpenAI documents no trigger threshold or classifier. Reverse-engineered names for an internal "search probability" signal have circulated, but I found no verified 2026 source for them.
- No study isolates agency or professional-services prompts, or Canadian prompts, for search-trigger rate.
- Search rates by model (GPT-5.x auto/instant/thinking) as of October 2026 were not found.

## 2. Which search indexes does ChatGPT use (Bing, OpenAI's own index, Google)?

### Takeaway
OpenAI doesn't name its search providers publicly beyond "third-party search providers." The strongest 2026 evidence points to a multi-source setup. Microsoft says its Bing-based **Web IQ** grounding service supports ChatGPT. Vendor reverse-engineering shows OpenAI's own index ("Labrador") being A/B-tested against external SERP providers, including scraping vendors. The Information reported in 2025 that OpenAI used Google results scraped through SerpApi. The weighting between these sources is unknown.

### Cited Findings
- [OFFICIAL, Microsoft] Microsoft launched **Web IQ** on June 2, 2026, a set of grounding APIs "powered by Bing's index." Microsoft states it "already supports grounding capabilities in Microsoft Copilot and ChatGPT." Coverage notes that Web IQ is a rebuilt stack, not the same API that Copilot and ChatGPT first used. — [Microsoft Learn: Web IQ overview](https://learn.microsoft.com/en-us/web-iq/overview); [Microsoft Tech Community: Web IQ](https://techcommunity.microsoft.com/blog/azuredevcommunityblog/web-iq-web-search-and-grounding-apis-for-ai-agents/4565272); [Search Engine Land: Microsoft releases Web IQ](https://searchengineland.com/microsoft-releases-web-iq-powered-by-bing-but-designed-for-how-ai-agents-search-479194)
- [OFFICIAL] OpenAI's help center refers to sharing approximate location with "search providers," confirming that third-party providers are used without naming them. — [OpenAI Help: Searching the web with ChatGPT](https://help.openai.com/en/articles/9237897-chatgpt-search)
- [vendor reverse-engineering] Peec AI found that ChatGPT runs its own retrieval index, internally named **"Labrador."** It is a family of vertical indexes (web, news, PDFs, YouTube, shopping, etc.). A field in ChatGPT's server-sent events, active May 21 to July 21, 2026, carried only four values: **Labrador, Bright (Bright Data), Oxylabs, and SERP**. Three of those are external scraping/SERP providers. — [Peec AI: ChatGPT built its own search index](https://peec.ai/blog/chatgpt-built-its-own-search-index); [Search Engine Watch: ChatGPT is quietly building its own search engine](https://searchenginewatch.com/chatgpt-own-search-engine/)
- [vendor] Peec AI reported an A/B test named "prefer-index-over-serp-v3" affecting about 8% of chats. It also found that only 1.5% of Labrador URLs appeared in Bing's top 20 for the same queries, so Labrador is not simply Bing rebranded. — [Peec AI](https://peec.ai/blog/chatgpt-built-its-own-search-index)
- [court testimony, secondhand] Head of ChatGPT Nick Turley reportedly testified at the Google antitrust trial that OpenAI had hoped its own index would handle 80% of queries by year-end. The sources say this goal slipped. — [Search Engine Watch](https://searchenginewatch.com/chatgpt-own-search-engine/); [Peec AI](https://peec.ai/blog/chatgpt-built-its-own-search-index)
- [press report, 2025] The Information reported in August 2025, citing two people familiar with the matter, that OpenAI used Google search results scraped through **SerpApi** to help ChatGPT answer current-events queries (news, sports, markets). The arrangement reportedly followed Google declining OpenAI's request for direct index access, a detail tied to antitrust court documents. SerpApi had listed OpenAI as a customer and later removed the reference. — [Search Engine Land: OpenAI, ChatGPT, SerpApi, Google results](https://searchengineland.com/openai-chatgpt-serpapi-google-search-results-461226); [Slashdot/The Information](https://tech.slashdot.org/story/25/08/22/1442208/openai-is-challenging-google---while-using-its-search-data)
- [disputed] Other practitioners attributed Google parameters in ChatGPT links to Common Crawl, and an Ahrefs analysis pushed back on the direct-scraping explanation. — [Search Engine World: new chapter in OpenAI using Google SERPs](https://www.searchengineworld.com/we-have-a-new-chapter-in-the-saga-of-openai-using-google-serps)
- [historical, outdated] In 2023, ChatGPT browsing searched only via Bing. — [TechCrunch, June 2023](https://techcrunch.com/2023/06/27/openais-chatgpt-app-can-now-search-the-web-but-only-via-bing)
- [secondary] OpenAI does not publish how much of an answer comes from each source, and nobody outside OpenAI knows the split. — [Search Engine Watch](https://searchenginewatch.com/chatgpt-own-search-engine/); [agenzy.lt: Does ChatGPT Use Bing or Google in 2026?](https://www.agenzy.lt/blog/does-chatgpt-use-bing-or-google)

### Inferences
- "ChatGPT = Bing" was a reasonable 2023-2024 heuristic but is outdated as of 2026. Bing (via Web IQ) is confirmed as one input. OpenAI's own crawl/index (fed by OAI-SearchBot) and scraped SERPs, very plausibly including Google, are also in play.
- Practical implication for an agency: Bing indexation is still necessary hygiene (Bing Webmaster Tools, IndexNow), and Google rankings still matter indirectly. Being crawlable by OAI-SearchBot is required to get into Labrador.

### Gaps
- No OpenAI first-party statement naming Bing, Google, SerpApi, Bright Data or Oxylabs was found.
- The current (October 2026) status of the SerpApi/Google arrangement is unverified.
- Whether the public Bing Search API retirement (2025) affected OpenAI was not verified in this session.
- Peec AI is a vendor of AI-visibility tracking. Its SSE-field findings come from observed client traffic over a two-month window and may have changed since.

## 3. OpenAI crawlers and user agents: OAI-SearchBot, ChatGPT-User, GPTBot

### Takeaway
OpenAI's official bot documentation (now hosted at developers.openai.com) separates three controls. **OAI-SearchBot** decides whether a site can appear in ChatGPT search results. **GPTBot** decides whether content can be used for model training. **ChatGPT-User** is for user-initiated fetches; it is not used for automatic crawling, robots.txt "may not apply" to it, and it doesn't govern search inclusion. An agency can block training (GPTBot) while staying eligible for ChatGPT search (OAI-SearchBot), but blocking OAI-SearchBot removes it from search answers.

### Cited Findings
- [OFFICIAL] OpenAI's documentation describes the crawlers as independently controllable via robots.txt. A webmaster can allow OAI-SearchBot to appear in search results while disallowing GPTBot. — [OpenAI: Overview of OpenAI Crawlers](https://developers.openai.com/api/docs/bots); [OpenAI GPTBot doc](https://developers.openai.com/docs/gptbot) (the old platform.openai.com/docs/bots path appears to have moved to developers.openai.com)
- [OFFICIAL] **OAI-SearchBot** is the agent to manage in robots.txt for "Search opt outs and automatic crawl," i.e. inclusion in ChatGPT search results. — [OpenAI: Overview of OpenAI Crawlers](https://developers.openai.com/api/docs/bots)
- [OFFICIAL] **GPTBot** controls whether crawled content may be used to train OpenAI's foundation models. — [OpenAI: Overview of OpenAI Crawlers](https://developers.openai.com/api/docs/bots)
- [OFFICIAL] **ChatGPT-User** handles user-triggered fetches (e.g. when a user or a Custom GPT/agent action asks ChatGPT to open a page). It "is not used for crawling the web in an automatic fashion," and because requests are user-initiated, "robots.txt rules may not apply." It does not determine whether content appears in Search. Published IP ranges are at openai.com/chatgpt-user.json. — [OpenAI: Overview of OpenAI Crawlers](https://developers.openai.com/api/docs/bots)
- [OFFICIAL] It can take about 24 hours after a robots.txt update for OpenAI's systems to adjust. If a site allows both GPTBot and OAI-SearchBot, OpenAI may use one crawl for both purposes. — [OpenAI: Overview of OpenAI Crawlers](https://developers.openai.com/api/docs/bots)
- [third-party] OAI-SearchBot IP ranges are reportedly at openai.com/searchbot.json. User-agent version strings conflict between sources (OAI-SearchBot/1.0 in older pages, /1.3 in a 2026 third-party article). — [NexterWP: OAI-SearchBot (2026)](https://nexterwp.com/blog/oai-searchbot-wordpress/); [Search Engine World: OpenAI crawlers](https://searchengineworld.com/?p=40)

### Inferences
- The recommended agency configuration is to allow OAI-SearchBot (and verify that CDN/WAF rules such as Cloudflare's AI-bot blocking don't block it), with GPTBot as a business decision. Note that blocking GPTBot may reduce future parametric familiarity with the brand. This is an inference; OpenAI makes no such claim.
- Because OAI-SearchBot feeds OpenAI's own index (Labrador), a site that is well ranked in Bing but blocks OAI-SearchBot may still appear via third-party SERP results. OpenAI's own docs, however, frame OAI-SearchBot as the opt-out for search inclusion. This interaction is not documented.

### Gaps
- I could not read the docs page verbatim (fetch failure), so exact current wording and any newer agents (e.g. an ads- or agent-specific bot) are unverified.
- No official documentation was found on how frequently OAI-SearchBot recrawls, or on whether it renders JavaScript. Practitioner claims that it does not execute JS were not verified this session.

## 4. Query fan-out: how ChatGPT rewrites one prompt into sub-queries

### Takeaway
When ChatGPT searches, it rewrites the user prompt into one or more search queries. Large vendor datasets show it routinely adds modifiers such as "best," "reviews," and the current year, and sometimes uses `site:` queries aimed at brand domains. How often it fans out and how many sub-queries it generates varies widely between studies (14% to 47% of responses; median about 1-2 per response). The sub-queries are themselves unstable across runs. In mid-August 2026 ChatGPT changed its client traffic so that fan-out queries are no longer exposed in the same way, which makes post-August 2026 fan-out research harder to reproduce.

### Cited Findings
- [LARGE-SAMPLE, vendor] Peec AI analyzed about 5 million ChatGPT fan-out queries (April 2026) and found ChatGPT consistently rewrites queries before executing them, adding terms like "best," "reviews," and the current year. — [PPC Land: What ChatGPT actually searches for: 5 million fanout queries](https://ppc.land/what-chatgpt-actually-searches-for-5-million-fanout-queries-analyzed/); [Peec AI: Patterns we see in ChatGPT query fanouts](https://peec.ai/blog/patterns-we-see-in-chatgpt-query-fanouts)
- [LARGE-SAMPLE, vendor] Ahrefs studied about 15 million fan-out queries from 66.6 million ChatGPT responses (collection window stated as August-September; year not confirmed in snippet). Only 14.4% of responses contained fan-out queries, averaging about 1.6 per response. Of the most common `site:` searches, 75.9% targeted a brand's own site. — [Ahrefs: How ChatGPT Does Query Fan-Out (15 Million Queries Studied)](https://ahrefs.com/blog/query-fan-out-chatgpt/)
- [vendor, mid-size] Loudface (3,718 answers, July-August 2026) found ChatGPT fanned out on 47% of answers versus 2% for Perplexity, with a median of one sub-query per answer and a maximum of 15. — [Loudface: Query Fan-Out](https://www.loudface.co/blog/fan-out-queries)
- [SMALL, consultant] MJ Cachón (branded prompts, GPT-5.5) found a single run averages fewer than 3 sub-queries, but across 4 runs the number of distinct sub-queries rises to 10.3. — [MJ Cachón: Study of query fan-out in ChatGPT using brand searches](https://www.mjcachon.com/en/blog/study-query-fan-out-chatgpt-brand/)
- [vendor] Surfer found only about 27% of fan-out queries stay stable across repeated searches. — [Surfer: Query Fan-Out](https://surferseo.com/blog/query-fan-out/)
- [vendor claim] Several sources say ChatGPT merges results across sub-queries with Reciprocal Rank Fusion, so pages that match several sub-queries score higher. This is inferred, not OpenAI-confirmed. — [Peec AI: Patterns in ChatGPT fanouts](https://peec.ai/blog/patterns-we-see-in-chatgpt-query-fanouts)
- [practitioner reverse-engineering] Resoneo (February 2026) reportedly found that ChatGPT applies recency filters when executing fan-outs. — summarized in [Suganthan: How ChatGPT Picks Sources: A Live Tracker](https://suganthan.com/ai-seo-research/chatgpt/)
- [practitioner, 2026] A tracker verified August 21, 2026 says ChatGPT rebuilt its search call in mid-August 2026 and the `search_queries` field previously used to read fan-outs is gone. Another practitioner says ChatGPT "has hidden its fan-out queries." — [Suganthan tracker](https://suganthan.com/ai-seo-research/chatgpt/); [Little Green Agency: ChatGPT Has Hidden Its Fan-Out Queries](https://littlegreenagency.co.uk/blog/chatgpt-has-hidden-its-fan-out-queries-heres-how-to-get-them-back-with-n8n/)

### Inferences
- For "best digital agency in Canada," expect sub-queries like "best digital agencies Canada 2026," "top digital marketing agencies Canada reviews," and possibly city-specific variants. Pages that rank for several of these variants (dated "best of" roundups, directory category pages) have a structural advantage under RRF-style fusion.
- A `site:` query against a brand domain mostly happens after the brand is already a candidate (e.g. for verification or details), so on-site content helps describe a brand more than it helps get the brand discovered. This is a hypothesis drawn from the Ahrefs site: data.

### Gaps
- I did not find a 2026 source with quantified frequency of the "reddit" modifier specifically in ChatGPT fan-outs. The brief's example ("reddit") remains unverified for ChatGPT, though Reddit is heavily cited (see §5).
- The year of the Ahrefs collection window and its exact method (forced versus organic search) were not confirmed.
- Post-August 2026 fan-out behavior is poorly documented because of the client change.

## 5. How ChatGPT chooses which pages to cite and which brands to name; overlap with Google/Bing rankings

### Takeaway
No official ranking factors exist. Evidence suggests ChatGPT's cited URLs overlap only weakly with Google's top 10 (around 7-11% URL overlap in Ahrefs data) and more strongly with Bing (Seer-derived figures of 80-87%, contested by other studies at around 40%). For commercial "best X" prompts, the dominant cited page type is third-party "best X" listicles and directories. Brands that rank well on those lists are more likely to be named, which is the key mechanism for agency recommendations. Brand mentions can also come from parametric memory with no citation. Reverse-engineered details (a reranker named "ret-rr-skysight-v3," a freshness-scoring flag) date from 2025 and may be stale.

### Cited Findings
- [OFFICIAL] OpenAI provides no documented ranking or citation-selection factors. A practitioner tracker (August 2026) notes that no numeric quality, authority or trust score for a source appears in ChatGPT's traffic or client bundle, and concludes that anyone selling "ChatGPT ranking factors" is guessing. — [Suganthan: How ChatGPT Picks Sources](https://suganthan.com/ai-seo-research/chatgpt/)
- [LARGE-SAMPLE, vendor] Ahrefs found citation overlap between AI assistants and the Google and Bing top 10 averages about 11%. For ChatGPT, URL overlap with Google's top 10 was about 10% for short-tail queries. A separate figure says only 6.82% of ChatGPT citations appear in Google's top 10 for fan-out queries. Perplexity is far closer to Google (about 65%). — [Ahrefs: AI search overlap](https://ahrefs.com/blog/ai-search-overlap/?app=1); [Ahrefs: ChatGPT vs Google citations](https://ahrefs.com/blog/chatgpt-google-citations); [GEO Software Rankings: Myth-tested, overlap is 6.82%](https://www.geosoftwarerankings.com/blog/myth-tested-ranking-1-on-google-gets-you-cited-by-chatgpt-the-overlap/)
- [vendor, Seer Interactive, 2024-2025 data, possibly outdated] Seer Interactive's widely cited finding is that about 87% of ChatGPT/SearchGPT citations matched Bing's top results, versus a 56% match rate for Google (median rank 17, average rank 28). A later 1,000-citation analysis found 80% of cited URLs ranked in Bing's top 10, lower than the 87% figure. — [Frase: Which AI engines cite which sources (2026)](https://www.frase.io/blog/which-ai-engines-cite-which-sources); [Capconvert: What 1,000 ChatGPT citations reveal](https://www.capconvert.com/learn/blog/what-1000-chatgpt-citations-reveal-about-openai-s-hidden-ranking-signals)
- [vendor, contradicting] Grow and Convert found only about 40% of ChatGPT's cited sources appeared anywhere in the first 10 pages of Google or Bing for the fan-out queries. — [Frase summary](https://www.frase.io/blog/which-ai-engines-cite-which-sources)
- [vendor] Peec AI found only 1.5% of Labrador (OpenAI's own index) URLs appear in Bing's top 20. As OpenAI shifts toward its own index, Bing overlap figures from 2024-2025 may overstate today's correlation. — [Peec AI](https://peec.ai/blog/chatgpt-built-its-own-search-index)
- [vendor, 750 prompts] In an Ahrefs study of ChatGPT responses to 750 top-of-funnel prompts (including agency-recommendation prompts), recently updated "best X" lists were the most prominent page type among sources, and brands ranking high on third-party lists were more likely to feature in responses. Ahrefs frames this as correlation, not proof that self-published lists work. — [Ahrefs (best lists study)](https://ahrefs.com/blog/?p=193630)
- [LARGE-SAMPLE, vendor] Across 9.6 million ChatGPT queries, Ahrefs found the most-cited domains in the U.S. were Reddit, Wikipedia, Amazon, Forbes and Business Insider. — [Ahrefs: Most cited domains in ChatGPT](https://ahrefs.com/blog/most-cited-domains-in-chatgpt/)
- [ANECDOTAL case study] A mature B2B marketing agency that passed nearly all technical checks got zero ChatGPT citations. For "best B2B marketing agency," citations came from third-party listicles in which the agency did not appear, despite many Clutch/DesignRush-type directory links. The author concludes that inclusion in editorial listicles mattered more than directory backlinks. — [Todd O'Rourke: Why ChatGPT won't cite your site](https://toddmorourke.com/learn/how-chatgpt-picks-sources/)
- [vendor, 7,000+ queries, Aug 2025] Wellows found consulting firms received only 4.8% of citations versus 46.5% for tech news sites (not agency-specific). — [Barchart/Wellows report](https://www.barchart.com/story/news/33884379/7-000-queries-analyzed-masab-s-wellows-report-explores-how-chatgpt-picks-its-mentions)
- [practitioner reverse-engineering, 2025, likely outdated] Metehan Yesilyurt found references in ChatGPT's front-end configuration to a reranker named "ret-rr-skysight-v3" and a freshness-scoring flag. PPC Land covered it on August 20, 2025. Later trackers say the search pipeline was rebuilt in mid-August 2026. — [Metehan: How I reverse-engineered ChatGPT's ranking algorithm](https://metehanai.substack.com/p/how-i-reverse-engineered-chatgpts); [PPC Land: ChatGPT configuration files reveal ranking mechanism](https://ppc.land/chatgpt-configuration-files-reveal-sophisticated-search-ranking-mechanism/); [Suganthan tracker](https://suganthan.com/ai-seo-research/chatgpt/)
- [vendor, correlational] Pages updated within three months reportedly averaged 6 citations versus 3.6 for stale content. — summarized in [Suganthan tracker](https://suganthan.com/ai-seo-research/chatgpt/)
- [PREPRINT] The Tannenbaum stage model separates citation (evidence exposure, then selection) from brand mention, and allows mentions without any observed citation through a "prior-compatible" path. — [arXiv 2609.23162](https://arxiv.org/pdf/2609.23162)

### Inferences
- Getting recommended for "best digital agency in Canada" works mainly through third parties. ChatGPT retrieves roundup pages, directory category pages (Clutch, DesignRush, GoodFirms, etc.) and Reddit threads, then names the brands that appear consistently across them. The agency's own site is mostly used for verification and details, not discovery.
- Freshness and an explicit current-year label likely matter for list pages, because fan-outs add the year and recency filters reportedly apply.
- Bing ranking is a reasonable but weakening proxy. Google top-10 rank alone is a poor predictor of ChatGPT citation.

### Gaps
- No study with agency- or Canada-specific citation breakdowns was found (e.g. Clutch's share of citations for "best agency" prompts).
- Seer's original sample size and date could not be confirmed this session. The 87% figure circulates widely, mostly secondhand.
- How ChatGPT chooses which brands to name from retrieved pages (e.g. a frequency or consensus threshold) is undocumented.

## 6. Local business recommendations: what data powers ChatGPT local/map results

### Takeaway
The best-documented local data source as of October 2026 is **Yelp**, under a non-exclusive licensing deal reported July 23, 2026: 330M reviews, 8M+ listings, Yelp-branded attribution, and a planned "Request a Quote" lead feature. The widely repeated claim that Foursquare powers 60-70% of ChatGPT local results rests on a tiny 2025 study, and an August 2026 vendor test found Foursquare in 0% of structured business-card data. Bing is often claimed as a supplementary source but isn't verified.

### Cited Findings
- [press, exclusive] Yelp is licensing reviews, photos and business information to OpenAI so ChatGPT can surface them in local recommendations. The deal covers 330 million cumulative reviews and more than 8 million listings. Yelp branding and links appear when its content is used, though OpenAI controls the design. Financial terms are undisclosed, and the deal is non-exclusive. — [Axios: Yelp partners with ChatGPT (July 23, 2026)](https://axios.com/2026/07/23/yelp-reviews-chatgpt-geo-partnership); [Search Engine Land: OpenAI-Yelp deal](https://searchengineland.com/openai-yelp-deal-483326); [MarTech: Yelp brings reviews and local leads to ChatGPT](https://martech.org/yelp-brings-reviews-and-local-leads-to-chatgpt/)
- [press] Yelp's "Request a Quote" feature was announced as coming to ChatGPT, letting users contact local service providers for quotes inside ChatGPT. — [Axios](https://axios.com/2026/07/23/yelp-reviews-chatgpt-geo-partnership); [MarTech](https://martech.org/yelp-brings-reviews-and-local-leads-to-chatgpt/)
- [single source] An August 19, 2026 report says the partnership was extended to restaurant reservations and waitlists across the U.S. and Canada. — [SOCi](https://www.soci.ai/?p=37711)
- [conflict] Some sources date Yelp's formal confirmation to February 12, 2026 investor communications. Others quote CEO Jeremy Stoppelman from the July 23 earnings release. — [TechWyse](https://www.techwyse.com/news/platform-updates/yelp-openai-licensing-deal-chatgpt-local-reviews); [SEO Sherpa](https://seosherpa.com/yelp-partners-with-chatgpt-to-license-business-information/)
- [vendor, 2,880 prompts, Aug 2026] Steady Demand found Yelp in the structured business-card data of 95.83% of ChatGPT local responses, and Foursquare in 0.00%. — summarized in [Surface Local: How ChatGPT Finds Local Businesses (2026)](https://www.surfacelocal.com/blog/how-chatgpt-finds-local-businesses); [Cicero Studio: ChatGPT just bought 330M Yelp reviews](https://cicero.studio/en/blog/chatgpt-yelp-330-million-reviews-local-seo-2026/)
- [SMALL, likely outdated] The often-repeated "Foursquare powers 60-70% of ChatGPT local results" figure traces to a May 2025 study of 50 prompts in five Spanish cities that looked only at the first-ranked result. Sources disagree on when any OpenAI-Foursquare partnership began (December 2024 versus January 2026). — [Surface Local](https://www.surfacelocal.com/blog/how-chatgpt-finds-local-businesses); [Mediaelx: ChatGPT shows local results from Foursquare](https://mediaelx.net/en/news/2270/chatgpt-shows-local-results-from-foursquare/); [iLocalSEO: Foursquare SEO 2026](https://ilocalseo.com/blog/foursquare-seo/)
- [marketing blogs, unverified] Several guides say ChatGPT also queries Bing's index or Bing Places for supplementary local information. — [Twenty One Solutions guide](https://twentyonesolutions.com/resources/local-businesses-show-up-in-chatgpt-ai-search-guide); [Radveo guide](https://radveo.com/guides/how-to-show-up-in-chatgpt-answers-local-business)

### Inferences
- "Top web design agency in Toronto" may produce Yelp-sourced business cards and map results, whereas "best digital agency in Canada" (national, B2B) more likely produces web-search answers built from listicles and directories (§5). Agencies should cover both: a complete Yelp business profile (including Canadian listings) and presence on editorial and directory lists.
- If Yelp "Request a Quote" is live in ChatGPT, agencies that respond to Yelp quote requests may get direct leads from ChatGPT. Availability in Canada is unconfirmed.

### Gaps
- No OpenAI first-party announcement of the Yelp deal was found. Coverage relies on Axios and Yelp.
- No 2026 evidence was found on whether Apple Maps, TripAdvisor, Google Business Profile or Bing Places feed ChatGPT local cards.
- Whether local business cards appear for B2B professional-services queries (versus restaurants and home services) is undocumented.
- Canada-specific coverage of ChatGPT local results was not found.

## 7. Memory, personalization and location effects on recommended brands

### Takeaway
Officially, ChatGPT estimates approximate location from the user's IP address and shares that approximate location (not the IP itself) with search providers. With memory on, it can rewrite search queries using saved memories. So two users asking the same "best agency" question can trigger different searches and get different brands. No controlled study measures the size of this effect on brand recommendations.

### Cited Findings
- [OFFICIAL] ChatGPT estimates general location from the IP address and may share that approximate location with search providers to improve results. It does not send the IP address itself. Precise device location is separate and optional. — [OpenAI Help: Searching the web with ChatGPT](https://help.openai.com/en/articles/9237897-chatgpt-search)
- [OFFICIAL] With memory on, ChatGPT can use saved memories to rewrite a search query. OpenAI's example: a user who has said they are vegan and live in San Francisco asks for nearby restaurants, and the query is rewritten to be vegan-specific. — [OpenAI Help: Searching the web with ChatGPT](https://help.openai.com/en/articles/9237897-chatgpt-search)
- [OFFICIAL] Deleting a chat does not automatically delete a memory saved from it. Precise location sharing is not available in Enterprise workspaces. — [OpenAI Help: Privacy Center in ChatGPT](https://help.openai.com/en/articles/20001488-privacy-center-in-chatgpt); [OpenAI Help: ChatGPT search for Enterprise and Edu](https://help.openai.com/en/articles/10093903-chatgpt-search-for-enterprise-and-edu)
- [OFFICIAL] OpenAI says advertisers do not get access to users' conversations or memories, and ads are matched using the conversation topic, past chats and past ad interactions. — [OpenAI: Testing ads in ChatGPT](https://openai.com/blog/testing-ads-in-chatgpt/)
- [academic, small] "The Algorithmic Self-Portrait" analyzed conversation histories from 80 users and found that in 96% of cases examined, ChatGPT created or updated memories without an explicit request. The study used a since-updated version of memory. — [arXiv 2602.01450](https://arxiv.org/pdf/2602.01450)
- [marketing commentary, no data] Duo Marketing Group describes logged-out and logged-in users with memory receiving different brand lists for the same query. This is an illustration, not a measurement. — [Duo Marketing Group: The brand you see in ChatGPT isn't the one everyone sees](https://duogroup.com/the-brand-you-see-in-chatgpt-isnt-the-one-everyone-sees/)
- [academic] An arXiv paper argues that offline LLM evaluations miss personalization effects in model behavior. — [arXiv 2509.19364](https://arxiv.org/pdf/2509.19364)

### Inferences
- A Canadian user's IP-based location will likely localize "best digital agency" queries toward Canada or their city even without "Canada" in the prompt. Agency monitoring should therefore use Canadian IPs and both logged-in and logged-out states.
- Earlier in-conversation context (e.g. "we're a Shopify brand in Vancouver") will reshape fan-outs and recommendations. Content that addresses specific niches and cities is more likely to match personalized sub-queries.

### Gaps
- No controlled study quantifies how memory, location or logged-in state change which brands are recommended.
- Whether memory influences answers when ChatGPT does not search (parametric-only answers) is undocumented.

## 8. 2025-2026 product changes relevant to recommendations

### Takeaway
The main changes: ChatGPT **ads** (announced Jan 16, 2026; launched Feb 9, 2026 for U.S. Free/Go users, then expanded internationally) under an official "answer independence" principle. **Product-feed ads** and Ads Manager feeds (May/June 2026). **Sponsored Agents** (reported September 2026, U.S. test). The **Yelp** local deal (July 2026). **Instant Checkout/Agentic Commerce Protocol** (Sept 2025), later reportedly scaled back in favor of discovery. **Shopping Research** (Nov 2025). The **Atlas** browser (Oct 21, 2025), which one search snippet suggests OpenAI has since deprecated (unverified). None of these yet provides a paid way into organic agency recommendations. Officially, ads sit separate from answers.

### Cited Findings
- [OFFICIAL] OpenAI's ad principles include "answer independence": ads do not influence the answers ChatGPT gives, conversations stay private from advertisers, and ads are clearly labeled as sponsored and visually separated from the organic answer. — [OpenAI: Our approach to advertising and expanding access](https://openai.com/index/our-approach-to-advertising-and-expanding-access/); [OpenAI: Testing ads in ChatGPT](https://openai.com/blog/testing-ads-in-chatgpt/)
- [OFFICIAL, via search summary] A March 2026 OpenAI update reported no impact on consumer-trust metrics and low ad-dismissal rates. A May 7, 2026 update expanded the pilot to the UK, Mexico, Brazil, Japan and South Korea. — [OpenAI: Testing ads in ChatGPT](https://openai.com/blog/testing-ads-in-chatgpt/)
- [third-party timeline] Ads were announced January 16, 2026 and first appeared February 9, 2026 for U.S. Free and Go users. Launch advertisers included Target, Adobe, Williams-Sonoma and Albertsons. — [Common Thread Co: Every ChatGPT Ads Update in 2026](https://commonthreadco.com/blogs/coachs-corner/every-chatgpt-ads-update-in-2026-updated-weekly); [Context Hints: ChatGPT Ads timeline](https://www.contexthints.com/guide/chatgpt-ads-news.html)
- [third-party, conflicting dates] Product-feed ads launched May 12, 2026 per one guide. Feed management moved into a "Feeds" section of ChatGPT Ads Manager on June 2, 2026 per another. Google Shopping-format feeds can reportedly be reused. — [Passionfruit: ChatGPT Product Feed Ads](https://www.getpassionfruit.com/blog/chatgpt-product-feed-ads-what-retailers-need-to-know); [Novadata: Ads Manager opens product feeds (June 2026)](https://novadata.io/resources/news/chatgpt-ads-manager-product-feeds-june-2026)
- [third-party, unverified] "Sponsored Agents" were reportedly announced September 16, 2026: after clicking an ad, users can open a labeled conversation with the sponsor's agent. It is described as a U.S. test, alongside a Shopify App Store integration. Ads were reportedly live in 60+ countries by September 23, 2026. — [Qwestyon: ChatGPT Ads Updates (October 2026)](https://www.qwestyon.com/blog/chatgpt-ads-updates); [Common Thread Co](https://commonthreadco.com/blogs/coachs-corner/every-chatgpt-ads-update-in-2026-updated-weekly)
- [vendor study, title only] One study reports ChatGPT ads appear on 26% of commercial prompts. Method not reviewed. — [ZoomYourTraffic](https://zoomyourtraffic.com/study-chatgpt-ads-appear-on-26-of-commercial-prompts/)
- [press, 2025] Instant Checkout launched late September 2025 (single-item purchases; Etsy first, Shopify merchants to follow), built on the Agentic Commerce Protocol co-developed with Stripe. — [AOL/news: OpenAI adds Instant Checkout](https://www.aol.com/news/openai-adds-instant-checkout-chatgpt-185200906.html); [Coresight: Agentic Commerce Protocol](https://coresight.com/research/agentic-commerce-how-retailers-can-employ-openais-agentic-commerce-protocol-to-unleash-a-true-ai-shopping-agent)
- [press, single report] In March 2026, OpenAI reportedly scaled back Instant Checkout after weak uptake and shifted focus to product discovery and research-driven shopping. — [Storyboard18: OpenAI scales back ChatGPT shopping ambitions](https://www.storyboard18.com/amp/digital/openai-reduces-chatgpt-shopping-focus-shifts-to-product-discovery-ws-l-93192.htm)
- [secondary, OpenAI figures] Shopping Research (November 2025) is a dedicated mode for high-consideration purchases. OpenAI evaluations reportedly showed 52% product match on multi-constraint queries versus 37% for standard ChatGPT Search. — [Cobus Greyling: Agentic Commerce](https://cobusgreyling.substack.com/p/agentic-commerce)
- [OFFICIAL] ChatGPT Atlas launched October 21, 2025 on macOS, with agent mode in preview for Plus/Pro/Business users. Agent mode can open tabs, scroll and click, and pauses on sensitive sites. Browsing data is not used for training by default. — [OpenAI: Introducing ChatGPT Atlas](https://openai.com/index/introducing-chatgpt-atlas/); [SiliconANGLE](https://siliconangle.com/2025/10/21/openai-launches-chatgpt-atlas-browser-embedded-ai-agent/)
- [unverified] A search-result summary indicated OpenAI's Atlas announcement page now carries a note that Atlas has been deprecated. I could not open the page to confirm. — [OpenAI: Introducing ChatGPT Atlas](https://openai.com/index/introducing-chatgpt-atlas/)
- [press] The Yelp deal (§6) adds licensed review content and a planned quote-request lead flow for local service providers. — [Axios](https://axios.com/2026/07/23/yelp-reviews-chatgpt-geo-partnership)

### Inferences
- For an agency, the relevant paid channel is ChatGPT Ads (conversation-topic targeting). Officially it can't buy placement in the organic recommendation list. Whether ads are available to Canadian advertisers or shown to Canadian users as of October 2026 is unconfirmed.
- Shopping and merchant feeds are product-oriented and largely irrelevant to service-agency recommendations. Yelp quote requests and Sponsored Agents are the closest service-lead analogs.

### Gaps
- Apps in ChatGPT / Apps SDK (DevDay, October 2025): I found no source this session detailing how apps are surfaced or recommended in conversations, or whether that affects service recommendations.
- OpenAI publisher partnerships (AP, Axel Springer, FT, News Corp, Condé Nast, etc., signed 2023-2024): not researched this session. Whether partner content gets preferential citation in 2026 is undocumented.
- No "ChatGPT recommends"/badge-style feature for businesses was found.
- Canadian availability of ads, Sponsored Agents and Yelp quote requests is unverified.
- The Atlas deprecation claim needs confirmation.

## 9. Volatility: how consistent are ChatGPT's brand recommendations?

### Takeaway
Very inconsistent at the level of the full list. The SparkToro/Gumshoe study (2,961 runs, November-December 2025) found under a 1-in-100 chance of getting the same recommendation list twice. Whether a brand appears at all is much more stable than its rank, and tighter niches are more stable than big categories. Fan-out queries themselves are only about 27% stable. Visibility should be measured as "share of runs in which the brand appears," across many runs, not as a single rank.

### Cited Findings
- [mid-size, vendor-partnered] SparkToro and Gumshoe.ai (Rand Fishkin, Patrick O'Donnell): about 600 volunteers ran 12 identical prompts through ChatGPT, Claude and Google's AI a combined 2,961 times over November-December 2025. The odds of the same list appearing twice were under 1 in 100. Lists varied in brands, order and length. Claude was only slightly more consistent. — [Search Engine Land: AI recommendation lists rarely repeat](https://searchengineland.com/ai-recommendation-lists-rarely-repeat-study-468076); [Search Engine Journal: AI recommendations change with nearly every query](https://www.searchenginejournal.com/ai-recommendations-change-with-nearly-every-query-sparktoro/566242)
- Some brands appeared again and again across dozens of runs even though their position varied. The authors recommend measuring visibility (the percentage of responses that include a brand) over rank. Smaller, tighter markets were more stable, while large categories scattered. — [Search Engine Land](https://searchengineland.com/ai-recommendation-lists-rarely-repeat-study-468076); [RetailDetail EU](https://www.retaildetail.eu/news/general/ai-recommendations-for-brands-or-products-are-extremely-inconsistent/)
- Funding and limitations: not peer reviewed. Fishkin disclosed that the work was done with Gumshoe, a company selling AI tracking tools, and called for larger follow-up studies. — [Search Engine Land](https://searchengineland.com/ai-recommendation-lists-rarely-repeat-study-468076); [Communicate Online](https://communicateonline.me/news/ai-brand-recommendations-vary-marketers-warned-on-tracking-tools/)
- [vendor] Only about 27% of ChatGPT fan-out queries remain stable across repeated searches. — [Surfer: Query Fan-Out](https://surferseo.com/blog/query-fan-out/)
- [SMALL] Distinct sub-queries rise from fewer than 3 (1 run) to 10.3 (4 runs) for the same branded prompt. — [MJ Cachón](https://www.mjcachon.com/en/blog/study-query-fan-out-chatgpt-brand/)
- [vendor] Search-trigger rates for the same prompt vary run to run (e.g. 31% for one tracked commercial prompt), so some runs are search-grounded and others parametric. — [Graphite](https://graphite.io/five-percent/research/do-not-force-search-prompt-tracking)

### Inferences
- "Digital agency in Canada" is a large, fragmented category, so expect high volatility. "Shopify Plus agency in Vancouver" or "web design agency for dentists in Toronto" is tighter and likely more stable, which favors a niche-positioning strategy.
- Monitoring should run each prompt many times (dozens), from Canadian IPs, logged-out and logged-in, without forcing search, and report share-of-appearance with confidence intervals.

### Gaps
- No large-sample study isolates volatility for B2B agency prompts or Canadian markets.
- The SparkToro/Gumshoe data predates ChatGPT's 2026 changes (Labrador index tests, the August 2026 search-call rebuild, GPT-5.5). Current volatility levels are unmeasured.
