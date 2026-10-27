# On-site and Content Tactics for Getting Cited and Recommended by ChatGPT (GEO / AI search optimization), as of October 2026

> **Method note for the report writer.** In this session, direct page fetching (WebFetch and curl) was blocked by the network policy: arxiv.org, openai.com, growth-memo.com, searchenginejournal.com and other hosts were refused. Every finding below therefore comes from search-engine result summaries of the cited pages, not from full-text reads. Figures marked "secondary" were reported by a third party rather than seen in the original. Verify exact numbers against the primary source before publishing them.
>
> **Vendor conflicts of interest.** Most large-sample "AI citation" studies come from companies that sell AI-visibility tracking or SEO tools. Examples: Ahrefs (Brand Radar), SE Ranking, Semrush, Peec AI, Profound, Otterly, and Prerender.io (sells pre-rendering). Vercel sells server-rendered hosting, SOCi sells local marketing software, and Microsoft owns Bing and Copilot. Their results are correlational and are not peer-reviewed. Academic arXiv work is mostly unreviewed preprints. Exceptions noted below: C-SEO Bench (NeurIPS 2025), AutoGEO (ICLR 2026) and "Whose Facts Win?" (ACL 2026).

## Q1. What did the original GEO paper (Aggarwal et al., KDD 2024) find, and what have 2025–2026 papers replicated, extended or challenged?

### Takeaway
The original GEO paper reported relative visibility lifts of up to about 40% from adding statistics, quotations and citations. Those lifts were measured only for documents already placed in the model's context window. Later work, notably C-SEO Bench (NeurIPS 2025), E-GEO, "What Gets Cited" (2026) and a July 2026 critical survey of 45 studies, finds these heuristics largely fail to replicate. The levers that do reproduce are topical relevance and position or retrieval rank (i.e., classic SEO), while authority and earned-media signals dominate in real engines.

### Cited Findings
**Original GEO paper (Aggarwal et al., KDD 2024, arXiv 2311.09735)**
- It introduced "GEO" and the GEO-bench benchmark, described as about 10,000 queries across multiple domains, with nine optimization methods tested. — [Gracker summary](https://gracker.ai/data-and-research-reports/geo-generative-engine-optimization-acm-sigkdd-2024); [neuroflash](https://neuroflash.com/blog/ai-visibility/generative-engine-optimization/) (secondary)
- The top methods were Cite Sources, Quotation Addition and Statistics Addition. Each reportedly gave a 30–40% relative lift on "Position-Adjusted Word Count" and 15–30% on "Subjective Impression". The 15–30% figure appears in only one summary. — [Gracker summary](https://gracker.ai/data-and-research-reports/geo-generative-engine-optimization-acm-sigkdd-2024) (secondary)
- Keyword stuffing and other classic-SEO-style tactics performed near zero or negative. — [Gracker summary](https://gracker.ai/data-and-research-reports/geo-generative-engine-optimization-acm-sigkdd-2024) (secondary)
- Gains were uneven by rank. A site ranked about 5th that added citations reportedly gained 115.1% visibility, while the top-ranked site lost visibility. The paper's interpretation is that GEO helps lower-ranked sites more. — [Gracker summary](https://gracker.ai/data-and-research-reports/geo-generative-engine-optimization-acm-sigkdd-2024) (secondary)

**Critical survey (Martinez, arXiv 2607.14035, July 2026; reviews 45 GEO studies)**
- The "up to 40%" result comes from a setting where the document is already in the engine's context. It measures the probability of citation given retrieval, not whether a page gets retrieved in the first place. — [arXiv 2607.14035](https://arxiv.org/abs/2607.14035); [summary by R. Galasso](https://robertgalasso.com/writing/geo-research-in-practice/)
- "No reviewed technique shows a stable, longitudinal, cross-platform causal effect on organic discoverability or downstream behavior." — [arXiv 2607.14035](https://arxiv.org/abs/2607.14035)
- What replicates: topical relevance and position in the context are the most reproducible levers. Generic heuristics transfer poorly, competition erodes individual gains, citation-oriented rewrites can hurt retrieval, and keyword stuffing does not transfer. — [arXiv 2607.14035](https://arxiv.org/abs/2607.14035)
- Visibility is unstable. The same query on different days, or a slight paraphrase, can return an entirely different set of cited sources, so there is "no universal GEO rank". — [arXiv 2607.14035](https://arxiv.org/abs/2607.14035)
- The survey says "optimization and manipulation share a channel": helpful rewrites, adversarial sequences and indirect prompt injections all change the text the engine consumes. — [arXiv 2607.14035 (html)](https://arxiv.org/html/2607.14035v1)
- One commentary notes that the survey's corpus selection cannot be audited. — [Pith review](https://pith.science/paper/2607.14035)

**C-SEO Bench (Puerto et al., NeurIPS 2025 Datasets & Benchmarks)**
- Most conversational-SEO methods are "largely ineffective" and frequently hurt document ranking. Traditional SEO, meaning raising a source's position in the LLM context, is "significantly more effective". — [OpenReview](https://openreview.net/forum?id=oTeixD3oZO); [NeurIPS paper PDF](https://papers.neurips.cc/paper_files/paper/2025/file/27aa3aeff0f8460a7b43d30fa6c5c032-Paper-Datasets_and_Benchmarks_Track.pdf)
- Gains shrink as more competitors adopt C-SEO methods. — [arXiv 2506.11097](https://arxiv.org/pdf/2506.11097)
- Only 3 of 54 method-domain combinations were significantly positive, and none were positive for question answering. The only gains came from "Content Improvement" (Retail only) and "LLM Guidance" (Retail and Video Games, with gpt-4o-mini only). — [C-SEO Bench via search summary](https://www.semanticscholar.org/paper/C-SEO-Bench:-Does-Conversational-SEO-Work-Puerto-Gubri/760bf666f45bb5de64532b3f446ef5e3eff4c0b3); also cited in [arXiv 2607.14035](https://arxiv.org/abs/2607.14035)

**E-GEO (Bagga et al., 2025, e-commerce testbed)**
- Ten of 15 initial GEO heuristics were neutral or negative. Systematically optimized prompts performed better. — [arXiv 2511.20867](https://arxiv.org/pdf/2511.20867); summarized in [arXiv 2607.14035](https://arxiv.org/abs/2607.14035)

**AutoGEO ("What Generative Search Engines Like and How to Optimize Web Content Cooperatively", accepted at ICLR 2026)**
- LLMs explain why one document in a pair is more visible than the other, and those explanations are distilled into "preference rules". The rules power a prompt-based rewriter (AutoGEO API) and a cheaper model (AutoGEO Mini, about 0.0071x the cost). The authors report better visibility on GEO-bench and two real-query benchmarks "while preserving search utility". — [arXiv 2510.11438](https://arxiv.org/abs/2510.11438); [ICLR 2026 proceedings](https://proceedings.iclr.cc/paper_files/paper/2026/file/dd5dfba659a7ec010414de1c1debdeb4-Paper-Conference.pdf)
- The project page reports 78–84% overlap of preference rules across LLMs. This figure was not verified in the paper. — [AutoGEO project page](https://zhongshsh.github.io/AutoGEO/)

**"What Gets Cited: Competitive GEO in AI Answer Engines" (Vishwakarma, arXiv 2605.25517, 2026)**
- 252,000 paired trials across six LLMs. Topical relevance and list position were the biggest drivers of being cited first, and formatting-only edits had little effect. — [arXiv 2605.25517](https://arxiv.org/pdf/2605.25517) (search-result summary)

**Measurement and other frameworks (2026)**
- Citations concentrate on a small set of outlets, and different engines pick different ones (low agreement across platforms). The paper separates "citation selection" (the engine searches and chooses sources) from "citation absorption" (the cited page's language, evidence or structure is used in the answer). — [arXiv 2604.25707](https://arxiv.org/html/2604.25707v2)
- A "Matthew effect" has been reported: LLMs prefer sources that are already heavily cited. — reported via survey in search summary of [arXiv 2607.14035](https://arxiv.org/pdf/2607.14035)

**Source-preference and earned-media research**
- Chen, Wang, Chen & Koudas (University of Toronto, arXiv 2509.08919, Sept 2025) found AI search shows a "systematic and overwhelming bias towards Earned media (third-party, authoritative sources) over Brand-owned and Social content", unlike Google's more balanced mix. They also report a "big brand bias" against niche players. — [arXiv 2509.08919](https://arxiv.org/pdf/2509.08919)
- An example from the same study (secondary, unverified): for US automotive queries, Google showed 39.5% Brand / 15.4% Social / 45.1% Earned, while AI search showed 81.9% Earned / 18.1% Brand. — [Gracker summary](https://gracker.ai/data-and-research-reports/generative-engine-optimization-how-to-dominate-ai-search)
- "Whose Facts Win?" (Schuster, Gautam, Markert, ACL 2026; arXiv 2601.03746) tested 13 open-weight models. When facts conflict, models prefer institutional sources in a consistent order: government > newspaper > person > social media. Repeating a low-credibility claim can reverse that preference. — [arXiv 2601.03746](https://arxiv.org/pdf/2601.03746); [ACL Anthology](https://aclanthology.org/2026.acl-long.1357.pdf)
- "Is Deep Research Reliable?" (arXiv 2607.20891, 2026) found higher-authority sources are adopted more often, though not strictly monotonically, and that "paper-style presentation" is an even stronger cue than authority. — [arXiv 2607.20891](https://arxiv.org/pdf/2607.20891) (search-result summary)

### Inferences
- Statistics, quotations and source citations may raise the share of a document used once it has been retrieved. They are not proven to make a page retrievable or recommended in live ChatGPT. Grade: **some evidence (conditional)**. The evidence for discoverability is weak, and the strongest replication attempt (C-SEO Bench, peer-reviewed) is mostly negative.
- The most robust academic signal is "be relevant and rank or retrieve high", which is ordinary SEO plus authority. For an agency, that means focused pages that directly match buyer queries, plus third-party (earned) coverage. Earned coverage is off-site but likely dominates.
- The authority and "paper-style" findings suggest that well-sourced, research-style pages with clear attribution, such as original data reports, fit what LLMs prefer. This is an inference from lab settings, not from ChatGPT production data.
- The original GEO results are now best treated as dated (2023–2024 engines and a simulated pipeline) and should be flagged as such.

### Gaps
- I could not read the full texts of CITECHOICE ([arXiv 2609.15164](https://arxiv.org/pdf/2609.15164), "A Causal Audit of How Document Presentation Redistributes Citation Credit in Agentic Search") or "When Optimization Becomes Manipulation" ([arXiv 2609.02964](https://arxiv.org/pdf/2609.02964)). Their findings are unknown beyond the titles.
- The exact AutoGEO preference rules, and whether AutoGEO gains hold on production ChatGPT, were not retrievable.
- I did not verify the original paper's real-world Perplexity test numbers from the primary source.

## Q2. Which content formats does ChatGPT tend to cite, and what do large-sample studies say about length, structure, freshness and answer-first writing?

### Takeaway
For recommendation queries ChatGPT has heavily cited "best X" listicles and comparison pages, but their share fell sharply after a 2026 model update. Fresher content and content containing the current year is favored, and fan-out queries often add "reviews", "pricing", "comparison" and the year. Evidence on length conflicts (long pages correlate with more citations, while focused pages beat "ultimate guides"). Front-loaded, definitional, answer-first writing has correlational support. All of this is vendor data.

### Cited Findings
**Page types**
- In an Ahrefs sample, "best of" lists were 43.8% of URLs ChatGPT cited for recommendation-style questions. — [gogochimp 6-study analysis](https://www.gogochimp.com/blog/what-chatgpt-actually-cites-2026) (secondary)
- Peec AI analysed about 1M prompts before and after the GPT-5.6 rollout (2026). Listicles fell from 15.77% to 7.80% of ChatGPT citations, and comparison pages from 9.08% to 6.17%. Total citations per chat roughly doubled, so listicles per chat stayed flat at about 1.97 versus 1.99. — [Lily Ray / Peec AI data](https://x.com/lilyraynyc/article/2090256147441746150); [SEO Handbook](https://seohandbook.co.uk/seo-news-updates/chatgpt-fan-out-query-shift-listicles/) (secondary)
- Self-promotional listicles: in Lily Ray's study of 100 B2B "best software" queries, when a brand's own listicle was cited, the brand was left out of the recommendation 69% of the time. This was measured on Google AI Overviews, not ChatGPT. — [gogochimp](https://www.gogochimp.com/blog/what-chatgpt-actually-cites-2026) (secondary; mislabelled in some summaries)
- In EMGI's July 2026 pilot of 48 SaaS buying prompts, 56% of ChatGPT citations pointed to vendor-owned pages, not third-party editorial. This is a small sample and conflicts with Chen et al.'s earned-media bias. — [EMGI](https://emgigroup.com/blog/query-fan-out-saas/)
- Semrush and Growth Memo looked at 1,094 US categories and 600k+ ChatGPT citations from Jan–Jun 2026. Only 21% of the most-cited domains in a category were also the most-mentioned brand, i.e., the cited source is not the recommended brand. — [Kevin Indig note](https://substack.com/@kevinindig/note/c-298265127); [Semrush 50k-brand study](https://www.semrush.com/blog/chatgpt-topic-authority-study/)
- Across 1.2M ChatGPT responses, the top 30 domains captured 67% of citations for a topic (high concentration). — [Kevin Indig note](https://substack.com/@kevinindig/note/c-231952797)

**Length and focus**
- SE Ranking (129,000 domains; 216,524 pages; 20 niches; XGBoost + SHAP; Nov 2025): content over 2,900 words averaged 5.1 citations versus 3.2 for content under 800 words. — [Search Engine Journal](https://www.searchenginejournal.com/new-data-top-factors-influencing-chatgpt-citations/561954/); [NOVASTACKS](https://www.novastacks-ai.com/blog/what-drives-ai-citations) (secondary)
- This is contradicted by Growth Memo's analysis of 815,000 query-page pairs, which concluded that comprehensive "ultimate guide" pages get worse citation results than focused, shorter pages. — [Growth Memo, "Shorter, Focused Content Wins in ChatGPT"](https://www.growth-memo.com/p/shorter-focused-content-wins-in-chatgpt) (via search summary)

**Position within the page and writing style (Kevin Indig "ski ramp", Feb 2026)**
- 44.2% of ChatGPT citations came from the first 30% of a page, about 31% from the middle, and about 25% from the final third. — [ALM Corp](https://almcorp.com/blog/chatgpt-citations-study-44-percent-first-third-content/); [GEO Briefing](https://thegeobriefing.com/do-ai-assistants-read-your-whole-page/) (secondary; reported sample sizes conflict: 1.2M responses versus 3M responses / 18,012 verified citations)
- Cited passages were reportedly about twice as likely to use clear definitions ("X is…"). Question-format headers were reportedly cited 18% of the time versus 8.9% for statement headers. — [marketing4ecommerce](https://marketing4ecommerce.net/en/ai-focuses-on-the-first-part-of-your-content/); [Passionfruit](https://www.getpassionfruit.com/blog/how-llms-search-for-citations-what-they-look-for-and-what-they-actually-find) (secondary; unverified)
- An "entity density" figure (20.6% for cited content versus 5–8% for typical web content) appears in only one secondary blog. — [Passionfruit](https://www.getpassionfruit.com/blog/how-llms-search-for-citations-what-they-look-for-and-what-they-actually-find) (unverified)

**Freshness**
- Ahrefs (17M cited URLs, July 2025): AI-assistant citations averaged 1,064 days old versus 1,432 days for organic SERPs (25.7% "fresher"). ChatGPT was the most freshness-biased and tended to place newer content first. The average cited page is still about 2.9 years old. Ahrefs notes John Mueller's warning against changing publish dates without real content changes. — [Ahrefs](https://ahrefs.com/blog/do-ai-assistants-prefer-to-cite-fresh-content/)
- A claim that "95% of ChatGPT citations come from content published in the last 10 months" circulates, attributed to SE Ranking. It is unverified and is in tension with Ahrefs' 2.9-year average. — [NOVASTACKS](https://www.novastacks-ai.com/blog/what-drives-ai-citations) (secondary)

**Fan-out queries (what ChatGPT actually searches)**
- Nectiv (Oct 2025; 8,500+ prompts): the most frequent modifiers were "reviews", the current year, "features" and "comparison". 31% of prompts triggered at least one web search. — [Nectiv](https://nectivdigital.com/blog/chatgpt-tripled-fan-out-queries-data-study); [PPC Land](https://ppc.land/what-chatgpt-actually-searches-for-5-million-fanout-queries-analyzed/)
- Ahrefs (15M fan-out queries): "price" and "review" fan-outs rose up to 47% in a month. "2026" appeared in 22.9% and "price" in 8.9% in September. — [Ahrefs](https://ahrefs.com/blog/query-fan-out-chatgpt/)
- EMGI SaaS pilot: 86% of ChatGPT fan-out queries contained a year, and 51% asked about pricing. — [EMGI](https://emgigroup.com/blog/query-fan-out-saas/) (small sample)

### Inferences
- For an agency, the formats most aligned with fan-out behaviour are: (1) service pages that state pricing ranges; (2) comparison pages (e.g., "agency vs freelancer vs in-house", "[service] pricing in [city] 2026"); (3) visible, dated, genuinely updated content; and (4) review and case-study evidence. Grade: **some evidence** (fan-out data are vendor-collected and correlational).
- Answer-first structure (key claim and definition in the first third, question-style H2s) is **some evidence / plausible**. It is low-risk and also good for human readers.
- Length: **conflicting → speculative**. Match depth to the query rather than padding. Indig's focused-page result and the C-SEO Bench "relevance wins" result point the same way.
- Self-published "best agencies in [city]" lists that rank yourself first are **risky / low-value**. ChatGPT's listicle share is dropping, and self-serving lists often fail to get the brand recommended (AIO evidence).
- Original data (surveys, benchmarks, pricing studies) fits the academic findings on statistics, quotations and authority, and earns third-party citations. Grade: **some evidence / plausible**. I found no ChatGPT-specific causal test.

### Gaps
- I found no reliable large-sample study isolating FAQ pages, how-to guides or pricing pages as cited page types for ChatGPT, beyond the small EMGI pilot.
- The "120–180 words per section" claim widely attributed to SE Ranking could not be verified.
- Peec's GPT-5.6 page-type shift comes from a social-post write-up and needs corroboration.

## Q3. Technical requirements: OAI-SearchBot access, JavaScript rendering, page speed, Bing indexing and IndexNow, sitemaps

### Takeaway
Allowing OAI-SearchBot is a documented, necessary condition for appearing in ChatGPT search answers. Serving core content in the initial HTML is strongly advised: OpenAI's crawlers did not execute JavaScript as of the 2024–2025 studies, and there is only one unverified September 2026 anecdote suggesting a change. Page speed correlates with citations. The Bing and IndexNow link to ChatGPT is unconfirmed: ChatGPT increasingly uses OpenAI's own "Labrador" index plus other providers, though Bing still matters for Copilot.

### Cited Findings
**OpenAI crawlers (first-party documentation)**
- OAI-SearchBot "is used to surface websites in search results in ChatGPT's search features. Sites that are opted out of OAI-SearchBot will not be shown in ChatGPT search answers, though can still appear as navigational links." — [OpenAI crawler docs](https://developers.openai.com/api/docs/bots)
- GPTBot (training) is controlled separately. A site can allow OAI-SearchBot and disallow GPTBot. — [OpenAI crawler docs](https://developers.openai.com/api/docs/bots)
- Robots.txt changes take "~24 hours" to take effect. ChatGPT-User (user-triggered fetches) is not the control for search: "Please use OAI-SearchBot in robots.txt for managing Search opt outs and automatic crawl." — [OpenAI crawler docs](https://developers.openai.com/api/docs/bots)
- For content to appear in summaries and snippets, OAI-SearchBot must not be blocked. Disallowed pages can still show as link and title. `noindex` is the way to prevent that, but the crawler must be allowed to fetch the page to see the tag. — [OpenAI Publishers & Developers FAQ](https://help.openai.com/en/articles/12627856)
- OpenAI publishes crawler IP ranges (openai.com/searchbot.json) and advises verifying bots by user agent, firewall allowlists and provider-level verification. This is relevant because CDN/WAF bot-blocking can silently block OAI-SearchBot. — [OpenAI advertiser guidance](https://help.openai.com/en/articles/20001243-advertiser-guidance-for-allowing-openai-web-crawlers)

**JavaScript rendering**
- Vercel and MERJ (Dec 2024): none of the major AI crawlers rendered JavaScript, including OAI-SearchBot, ChatGPT-User, GPTBot, ClaudeBot and PerplexityBot. Googlebot (Gemini) is the exception. ChatGPT and Claude crawlers fetch JS files (11.50% and 23.84% of requests) but do not execute them. GPTBot made 569M requests per month on Vercel's network. Note that Vercel sells SSR hosting. — [Vercel blog](https://vercel.com/blog/the-rise-of-the-ai-crawler); [SEJ coverage](https://www.searchenginejournal.com/ai-crawlers-account-for-28-of-googlebots-traffic-study-finds/535948/)
- SEJ reports that ChatGPT and Claude spent over 34% of their requests on 404 pages. — [SEJ](https://www.searchenginejournal.com/ai-crawlers-account-for-28-of-googlebots-traffic-study-finds/535948/)
- 2026 tests (Tripledart, Hall) still list OAI-SearchBot, GPTBot and ChatGPT-User as raw-HTML-only. — [Tripledart](https://www.tripledart.com/research/why-your-site-is-invisible-to-chatgpt-and-claude); [Hall](https://usehall.com/guides/chatgpt-ai-crawlers-javascript-rendering)
- Possible change: a single Indie Hackers post claims OAI-SearchBot (verified by IP) began fetching JS-generated prefetch URLs on a Next.js site from 25 Sept 2026. There is no OpenAI announcement. — [Indie Hackers](https://www.indiehackers.com/post/traffic-from-chatgpt-jumped-is-it-because-its-crawlers-now-run-javascript-5dea2e48d0); [GeoToolbox](https://geotoolbox.ai/blog/javascript-seo) (treats this as an open question)

**Page speed**
- SE Ranking reports that pages with First Contentful Paint under 0.4s averaged about 6.7 ChatGPT citations versus about 2.1 for pages slower than 1.13s. FCP and LCP were inversely correlated with citations. INP ran the other way: the fastest-INP pages got fewer citations. These are correlational XGBoost results. — [SEJ](https://www.searchenginejournal.com/new-data-top-factors-influencing-chatgpt-citations/561954/); [SE Ranking](https://seranking.com/blog/how-to-optimize-for-chatgpt/)
- The "crawler timeout" explanation is speculation by bloggers. — [Appsrow](https://www.appsrow.com/blog/why-page-speed-decides-whether-ai-engines-cite-you-and-how-to-fix-it)

**Bing, OpenAI's own index and IndexNow**
- Peec AI (Sept 2026): ChatGPT's server-side events between May 21 and July 21, 2026 showed a `result_source` field with four values: "Labrador" (OpenAI's own index), "Bright", "Oxylabs" (scraping providers) and "SERP". An experiment, "prefer-index-over-serp-v3", reportedly affected about 8% of conversations in mid-August 2026 (one shopping experiment). — [Peec AI](https://peec.ai/blog/chatgpt-built-its-own-search-index); [Search Engine Watch](https://searchenginewatch.com/chatgpt-own-search-engine/); [Otterly](https://otterly.ai/blog/openai-searchindex/)
- RESONEO reportedly found only 1.5% of URLs from OpenAI's index appear in Bing's top 20 for the same queries. Nick Turley (head of ChatGPT) testified to a target of 80% of searches served from OpenAI's own index by end of 2025, which has slipped. — [Search Engine Watch](https://searchenginewatch.com/chatgpt-own-search-engine/) (secondary)
- OpenAI's help pages say ChatGPT search uses third-party search providers. I found no first-party OpenAI statement linking Bing indexing or IndexNow to ChatGPT visibility, and OpenAI is not an IndexNow participant (participants: Bing, Yandex, Seznam, Naver, Yep, Internet Archive, Amazon). — [eSEOspace](https://eseospace.com/blog/bing-webmaster-tools-indexnow-ai-search/); [MeshWorld](https://meshworld.in/blog/web-dev/seo/indexnow/search-engines-supporting-indexnow/)
- Bing Webmaster Tools' "AI Performance" report (public preview, early 2026) shows citations, cited pages and "grounding queries" for Copilot, Bing AI summaries and select partners. It does not cover ChatGPT. A June 2026 update added Citation Share, Intents, Topics and a compare view. — [SEJ](https://www.searchenginejournal.com/bing-webmaster-tools-adds-ai-citation-performance-data/566874/); [Search Influence](https://www.searchinfluence.com/blog/bing-ai-performance-report-copilot-citations/); [CXL](https://cxl.com/blog/bing-ai-visibility-tracking-webmaster-tools/)

### Inferences
- **Strong evidence:**
  - Explicitly allow OAI-SearchBot (and ChatGPT-User) in robots.txt.
  - Make sure the CDN or WAF (e.g., Cloudflare bot-fight or AI-blocking defaults) does not block them.
  - Do not `noindex` pages you want cited.
  - Check server logs for OAI-SearchBot hits.
- **Strong evidence (as risk mitigation):** use SSR, SSG or pre-rendering so service descriptions, pricing, locations and case-study text are in the raw HTML. Even if OpenAI begins rendering JS, raw HTML remains the safe baseline for every AI crawler. Flag the Vercel study as dated (Dec 2024) and the Sept 2026 rendering anecdote as unverified.
- **Some evidence:** fast FCP. The cause is unproven, but it is cheap to fix and fixing it is aligned with SEO.
- **Speculative for ChatGPT, useful for Copilot:** Bing Webmaster Tools, IndexNow and sitemap submission. They are low cost and help Bing/Copilot, which has its own measurement report. The ChatGPT benefit is unconfirmed and probably shrinking as OpenAI's own index grows.
- Sitemaps: **hygiene, speculative for ChatGPT**. No ChatGPT-specific evidence was found.

### Gaps
- No OpenAI documentation on JS rendering, crawl budget, sitemap use or IndexNow was found.
- How much of ChatGPT's retrieval now comes from Labrador versus Bing versus scraped Google SERPs is unknown and changes with experiments.

## Q4. Does schema markup (Organization, LocalBusiness, ProfessionalService, Service, FAQPage, Review, sameAs) affect ChatGPT citations?

### Takeaway
The best available tests find no measurable direct lift in ChatGPT citations from adding schema. FAQ schema even correlates slightly negatively in one dataset. Any benefit is likely indirect, through search-engine understanding and entity disambiguation. Grade: **speculative** for a direct ChatGPT effect, and low-cost hygiene otherwise.

### Cited Findings
- Ahrefs tracked 1,885 pages that added JSON-LD and found no statistically significant citation gain on Google AI Overviews, AI Mode or ChatGPT. The sample was already heavily cited pages, which limits generalisation. — [Ahrefs](https://ahrefs.com/blog/schema-ai-citations/)
- An SSRN preprint (Fischman) on 730 ChatGPT and Gemini citations found a null effect for schema presence. A reanalysis reportedly found "attribute-rich" schema beat generic schema with a significant gap. — [SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6284518); [AuthorityTech](https://authoritytech.io/blog/schema-markup-structured-data-ai-search-citations-impact-2026)
- A separate experiment, reported second-hand, found that ChatGPT, Claude, Perplexity, Gemini and Google AI Mode extracted only visible HTML, not hidden JSON-LD. — [AuthorityTech curated](https://authoritytech.io/curated/schema-markup-ai-citations-ahrefs-study-2026) (unverified)
- In SE Ranking's data, pages with FAQ schema averaged 3.6 ChatGPT citations versus 4.2 without. — [NOVASTACKS summary of SE Ranking](https://www.novastacks-ai.com/blog/what-drives-ai-citations) (secondary)
- Widely quoted claims such as "71% of ChatGPT-cited pages have schema" are correlational and vendor-sourced. A vendor also claims Microsoft confirmed its LLMs use structured data, which I could not verify. — [AuthorityTech](https://authoritytech.io/blog/schema-markup-structured-data-ai-search-citations-impact-2026)
- Google's guidance: no special schema is needed for AI Overviews or AI Mode, but structured data should match visible text and remains useful for rich results. — [Google Search Central: AI features and your website](https://developers.google.com/search/docs/appearance/ai-features); [Previsible](https://previsible.io/seo-ai-news/google-published-its-first-guide-to-ai-search-optimization/)

### Inferences
- For an agency, Organization or ProfessionalService/LocalBusiness schema with `sameAs` links to LinkedIn, Clutch, Google Business Profile and other profiles is worth adding as cheap entity hygiene. It may help search engines (Bing, Google) that feed or influence AI systems, but it should not be sold as a ChatGPT citation lever. Grade: **speculative (indirect)**.
- The important part is that the same facts (services, cities, pricing, team) appear in visible HTML. Evidence suggests LLM fetchers read visible text, so schema-only facts may be invisible to ChatGPT.
- FAQPage schema: **myth as a ChatGPT lever**. Visible Q&A content may still help (see Q2), but the markup itself shows no lift.

### Gaps
- No controlled test was found for ProfessionalService, Service, Review or sameAs schema specifically on ChatGPT.
- Bing's and Microsoft's statements on structured data use in Copilot grounding were not verified first-hand.

## Q5. llms.txt: what is it, how widely is it adopted, and is there evidence AI crawlers use it?

### Takeaway
llms.txt is a proposed markdown file that points LLMs to a site's key content. Adoption is rising (about 10% of domains), but log studies show negligible crawler requests and no citation correlation. Google says it does not use it, and no major AI vendor has said production systems use it. Grade: **myth** as a ChatGPT visibility lever. It is harmless and low-cost.

### Cited Findings
- It is a proposal, "not a way to control AI bots", and "not a widely used and accepted standard". — [SEJ](https://www.searchenginejournal.com/google-says-llms-txt-comparable-to-keywords-meta-tag/544804/)
- SE Ranking (about 300,000 domains): 10.13% had llms.txt, up from 0.4% in April 2025. No statistically significant correlation with AI citations. — [SE Ranking](https://seranking.com/blog/how-to-optimize-for-chatgpt/); [NOVASTACKS](https://www.novastacks-ai.com/blog/what-drives-ai-citations)
- An Oct 2026 dataset of 261–285 major sites: 81 of 241 determinable sites (34%) serve a valid llms.txt, and 35% block at least one AI training crawler. — [Mendeley Data](https://data.mendeley.com/datasets/vv5v5x8h52/1)
- Log studies: one 90-day window had 408 llms.txt requests out of more than 500M AI-bot visits. OtterlyAI saw 84 llms.txt requests out of 62,100 AI-bot visits. Ahrefs reportedly found 97% of llms.txt files received zero traffic (about 137k sites). — [RichDevTools](https://richdevtools.com/articles/web/llms-txt-evidence-2026); [1ClickReport](https://www.1clickreport.com/blog/llms-txt-evidence-2026) (secondary)
- A claim that GPTBot requested llms.txt on about 60% of implementing sites has no verifiable data behind it. — [Worknido](https://www.worknido.com/blog/does-llmstxt-actually-work-evidence-from-2026-server-logs) (unreliable)
- One practitioner (Ray Martinez) posted logs showing OpenAI fetching his llms.txt about every 15 minutes. This is an anecdote, and fetching is not the same as using. — [Search Engine Land](https://searchengineland.com/google-says-normal-seo-works-for-ranking-in-ai-overviews-and-llms-txt-wont-be-used-459422)
- John Mueller (Google) compared llms.txt to the keywords meta tag and said: "As far as I know, none of the AI services have said they're using LLMs.txt." — [SEJ](https://www.searchenginejournal.com/google-says-llms-txt-comparable-to-keywords-meta-tag/544804/)
- Gary Illyes (Google, July 2025 Search Central event in APAC; reported venues differ) said Google doesn't support llms.txt and isn't planning to. — [Search Engine Land](https://searchengineland.com/google-says-normal-seo-works-for-ranking-in-ai-overviews-and-llms-txt-wont-be-used-459422)
- Reportedly, on June 15, 2026, Google added a changelog note to its AI-optimization guide ("Clarifying guidance on llms.txt files"): the file is not needed, and it neither helps nor harms. The same source reports Chrome Lighthouse began auditing llms.txt. — [TechWyse](https://www.techwyse.com/news/ai-search/google-ai-search-optimization-guide-llms-txt-lighthouse-audit) (unverified against Google docs)
- No public statement from OpenAI, Google, Anthropic, Meta, Perplexity or Mistral says production systems read or act on llms.txt. One source claims Perplexity and Claude retrieve it. — [1ClickReport](https://www.1clickreport.com/blog/llms-txt-evidence-2026); [Search Engine Land](https://searchengineland.com/google-says-normal-seo-works-for-ranking-in-ai-overviews-and-llms-txt-wont-be-used-459422) (secondary)

### Inferences
- Do not prioritize llms.txt or sell it to clients as a GEO tactic. If added, treat it as a 15-minute nice-to-have, e.g., for developer docs or agent tooling.
- A Lighthouse audit, if confirmed, may push adoption but does not imply ChatGPT uses the file.

### Gaps
- I found no OpenAI documentation mentioning llms.txt in either direction.
- The Chrome Lighthouse llms.txt audit claim is unverified.

## Q6. Service page and "about" page best practices for agencies (who you serve, location, specialties, pricing, case studies, credentials, client logos)

### Takeaway
I found no rigorous study testing agency service or about pages in ChatGPT. Indirect evidence suggests that what drives recommendations is consistent, corroborated entity facts across third-party sources (earned media, reviews, directories) plus focused, query-matching owned pages. The evidence covers local and brand recommendations, fan-out modifiers and source-authority research. Most agency-page "best practices" are therefore **speculative or plausible**, not proven.

### Cited Findings
- SOCi's 2026 Local Visibility Index found ChatGPT recommended only 1.2% of brand locations, versus 11.0% for Gemini and 7.4% for Perplexity. Note that SOCi is a local-marketing vendor. — [National Law Review press release](https://natlawreview.com/press-releases/ai-search-recommends-only-12-local-businesses-rest-are-invisible)
- In a field test (Aug 2026), 57 of 81 (70%) page-one Google Maps businesses were never named in ChatGPT's written recommendation. — [dev.to / PresenceScanner](https://dev.to/scriptmasterlabs01/do-top-ranked-local-businesses-get-recommended-by-chatgpt-70-never-named-and-the-oct-26-1j1h) (anecdotal, unverified)
- Microsoft Advertising reportedly found only about 4% of cited links in local AI answers point to the business's own website; city and national editorial was the largest share. Gemini reportedly sends about 60% of local citations to the business's own site, so the pattern is engine-specific. — [Elev8 Operations stats roundup](https://www.elev8operations.com/guides/ai-search-statistics-for-local-businesses-2026); [Driven Metrics](https://driven-metrics.com/blog/chatgpt-local-business-recommendation-rate-2026/) (secondary)
- ChatGPT "usually names a local business when several trusted sources agree on the same entity, location, services and customer reputation". — [BGR Review](https://bgrreview.com/insights/chatgpt-local-business-recommendations-2026) (vendor opinion)
- Strongest single predictors of ChatGPT citation: referring domains (a threshold at about 32,000), Quora and Reddit presence (7–8 citations) and review-platform listings (4–6). These are domain-level correlations. — [SEJ on SE Ranking](https://www.searchenginejournal.com/new-data-top-factors-influencing-chatgpt-citations/561954/); [NOVASTACKS](https://www.novastacks-ai.com/blog/what-drives-ai-citations)
- Within a single high-authority domain, referring domains showed no positive relationship with page-level citations. — [Green Flag Digital](https://greenflagdigital.com/chatgpt-citation-study/)
- Fan-out queries frequently add "reviews", "pricing", "comparison" and the year (see Q2). In a SaaS pilot, 51% of fan-outs asked about pricing. — [Nectiv](https://nectivdigital.com/blog/chatgpt-tripled-fan-out-queries-data-study); [EMGI](https://emgigroup.com/blog/query-fan-out-saas/)
- AI search is biased toward earned media and big brands (Chen et al. 2025), and LLMs prefer institutional sources (Schuster et al., ACL 2026). — [arXiv 2509.08919](https://arxiv.org/pdf/2509.08919); [arXiv 2601.03746](https://arxiv.org/pdf/2601.03746)
- Author-credential lift claims range from 40% to 60% to 2.3x. The 2.3x traces to an Onely finding that 76.4% of AI-cited content had attributed authors. All are correlational and vendor-sourced. — [AuthorityTech](https://authoritytech.io/blog/eeat-trust-signals-earn-machine-citations-2026); [Qwairy](https://www.qwairy.co/blog/eeat-for-ai-authority-signals-guide) (weak)
- BrightLocal's 2026 consumer survey reportedly found 45% of US consumers use ChatGPT or another generative AI tool for local business recommendations. — [Elev8 Operations](https://www.elev8operations.com/guides/ai-search-statistics-for-local-businesses-2026) (secondary; not verified against BrightLocal)

### Inferences
- **Plausible / some evidence (low risk, aligned with SEO and conversion):** these items line up with fan-out modifiers and the entity-consistency logic:
  - One focused page per service, plus a service-by-location or industry page where genuinely relevant.
  - Explicit "who we serve / where / what we specialize in" statements in the first paragraph (answer-first).
  - Stated pricing ranges or engagement minimums.
  - Dated case studies with specific, verifiable numbers and named clients where permitted.
  - Named team members with credentials and links to their profiles.
- Client logos are images and carry little text an LLM can read. A text list of named clients and industries is more machine-readable. This is an inference, not tested.
- Keep the same facts (name, address, service list, cities, founding year, team size) identical on the site, Google Business Profile, LinkedIn, Clutch/G2/DesignRush-type directories and review sites. **Speculative but logical**, given the "multiple sources agree" mechanism and the earned-media bias.
- The on-site work is necessary but probably not sufficient. For ChatGPT, third-party lists, directories, reviews and press appear to be the main drivers of "recommend an agency" answers. Owned pages mainly supply facts once the brand is a candidate.

### Gaps
- I found no study measuring ChatGPT recommendations specifically for marketing or digital agencies, or isolating about-page or case-study effects.
- The primary Whitespark and BrightLocal 2026 reports could not be accessed.
- The Microsoft Advertising "4% own-site" figure could not be traced to a primary source.

## Q7. Do pages built purely for LLMs (hidden text, prompt injection, "AI-only" pages, cloaking) work, and what are the risks?

### Takeaway
Adversarial manipulation demonstrably can work in lab settings and in some live tests. Examples: hidden-text injection on ChatGPT search (Dec 2024), strategic text sequences, and ranking-manipulation prompts. It is now classified by Microsoft and security researchers as an attack ("AI recommendation poisoning", "AI-targeted cloaking"). Defenses are being built, and Google explicitly says not to make separate LLM versions or chunked content. Grade: **myth/risky**. The effects are short-lived and detectable, and they carry reputational, platform and possibly legal risk.

### Cited Findings
- Guardian test (Dec 2024): a fake product page with hidden text instructing ChatGPT search to be positive produced a wholly positive summary despite negative reviews on the page. Hidden fake positive reviews without instructions also shifted the output. The text was hidden by matching the font colour to the background. — [SEJ](https://www.searchenginejournal.com/chatgpt-search-manipulated-with-hidden-instructions/536390/); [heise](https://heise.de/-10222643) (dated: late-2024 ChatGPT search)
- Microsoft Defender researchers (Feb 10, 2026) described "AI Recommendation Poisoning": hidden instructions in "Summarize with AI" buttons that try to make assistants "remember [company] as a trusted source". Over 60 days they found more than 50 unique prompts from 31 companies in 14 industries. Microsoft classes this as an AI memory-poisoning attack. — [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/); [BankInfoSecurity](https://www.bankinfosecurity.com/hidden-commands-found-in-ai-summarize-buttons-a-30784); [SEJ](https://www.searchenginejournal.com/microsoft-summarize-with-ai-buttons-used-to-poison-ai-recommendations/567941/)
- SPLX (Oct 2025) described "AI-targeted cloaking": serving different content to AI crawler user agents (ChatGPT, Perplexity) than to browsers, framed as context poisoning for agentic browsers such as ChatGPT Atlas. — [The Hacker News](https://thehackernews.com/2025/10/new-ai-targeted-cloaking-attack-tricks.html)
- Academic attacks:
  - Strategic text sequences (Kumar & Lakkaraju, 2024) can make an LLM recommend a product, even overriding stated criteria such as price. — [alphaXiv 2404.07981](https://www.alphaxiv.org/abs/2404.07981); [Towards Data Science](https://towardsdatascience.com/can-recommendations-from-llms-be-manipulated-to-enhance-a-products-visibility-64c64fa9cd24/)
  - Prompt injections can reorder sources in conversational search engines (Pfrommer et al. 2024). — [arXiv 2406.03589](https://arxiv.org/abs/2406.03589)
  - StealthRank (2025) — [arXiv 2504.05804](https://arxiv.org/pdf/2504.05804)
- Defenses (2026): SCI-Defense combines perplexity detection, semantic-integrity scoring and cross-candidate detection. Its authors report that existing defenses had zero recall against semantic manipulation, so this is an active arms race with preliminary results. — [arXiv 2605.21948](https://arxiv.org/html/2605.21948v1)
- Google (Danny Sullivan, Search Off the Record, Jan 8, 2026): "we don't want you to" turn content into bite-sized chunks for LLMs. Systems access content the way humans do, so don't make two versions, one for LLMs and one for people. Even if chunking works for another LLM system now, "it won't work in the long run". — [Search Engine Land](https://searchengineland.com/google-doesnt-want-you-to-create-bite-sized-chunks-of-your-content-467269); [PPC Land](https://ppc.land/google-warns-against-breaking-content-into-chunks-for-ai/); [SE Roundtable](https://www.seroundtable.com/google-content-bite-sized-chunks-40728.html)
- C-SEO Bench: gains shrink as more competitors adopt manipulation-style methods. — [arXiv 2506.11097](https://arxiv.org/pdf/2506.11097)

### Inferences
- Hidden text, prompt injection, "Summarize with AI" memory prompts, user-agent cloaking and AI-only doorway pages are all **myth/risky** for an agency. Reasons:
  - They are now publicly labelled as attacks by Microsoft and security vendors.
  - Defenses and detection are being built.
  - They would likely violate Google's spam policies on hidden text and cloaking, so they risk organic rankings that ChatGPT retrieval partly depends on.
  - An agency caught doing this damages client trust.
  - Gains are fragile and erode under competition.
- "AI-friendly" restructuring that also serves humans (clear headings, summaries, tables) is fine. Separate machine-only pages or chunk-farms are not.

### Gaps
- I found no OpenAI public statement or policy specifically about penalizing manipulative pages in ChatGPT search.
- I did not retrieve a source for Google's spam-policy text on hidden text and cloaking in this session (the policy is well known, but it is uncited here).

## Q8. How does Google's 2025–2026 "GEO is just SEO" stance compare with evidence that AI search rewards different things?

### Takeaway
Google's position is that its AI features need no special optimization: good SEO is good GEO, and you shouldn't chunk or duplicate content. That is largely about Google's own surfaces. For ChatGPT, the evidence shows meaningful divergence:
- Low overlap with Google's top 10 (about 8%).
- A strong earned-media and big-brand bias.
- Fan-out sub-queries different from the user's prompt.
- A freshness preference.
- A growing proprietary index.

Academic replication work nevertheless supports Google's core claim that relevance and retrieval rank, not textual tricks, are the main levers.

### Cited Findings
- Google Search Central: AI Overviews and AI Mode have "no additional technical requirements". A page must be indexed and snippet-eligible, and "all existing SEO fundamentals continue to be worthwhile". — [Google: AI features and your website](https://developers.google.com/search/docs/appearance/ai-features); [Practical Ecommerce](https://www.practicalecommerce.com/google-says-ai-optimization-is-just-seo)
- Danny Sullivan (Search Central Live Toronto): "Good SEO is good GEO". He and Mueller said hiring a "GEO expert" is no different from hiring an SEO. — [Search Engine Land](https://searchengineland.com/google-doesnt-want-you-to-create-bite-sized-chunks-of-your-content-467269); [Nikki Pilkington](https://nikki-pilkington.com/google-confirms-geo-is-bollocks-and-chunking-your-content-wont-help/); [SEJ](https://www.searchenginejournal.com/google-downplays-geo-but-lets-talk-about-garbage-ai-serps/564901/)
- Ahrefs (15,000 long-tail queries) found about 11–12% average overlap between AI-assistant citations and the Google/Bing top 10. ChatGPT was about 8% for in-text citations and about 6% for bottom references, versus about 28.6% for Perplexity. — [Ahrefs](https://ahrefs.com/blog/ai-search-overlap/); [Quattr](https://www.quattr.com/blog/takeaway-from-ahrefs-ai-search-study)
- Another Ahrefs analysis put the overlap of ChatGPT fan-out-query citations with SERPs at 6.82%. — [GEO Software Rankings](https://www.geosoftwarerankings.com/blog/myth-tested-ranking-1-on-google-gets-you-cited-by-chatgpt-the-overlap/) (secondary)
- Even for Google AI Overviews, the top-10 overlap fell from 76% (2025) to 37.9% (March 2026; 863k SERPs). In 2026, 31.0% of AIO citations came from outside the top 100, partly because of parsing changes. — [Ahrefs via search summary](https://ahrefs.com/blog/ai-search-overlap/)
- AI search shows a strong earned-media bias versus Google's balanced mix, and engines differ in domain diversity, freshness and sensitivity to phrasing. — [arXiv 2509.08919](https://arxiv.org/pdf/2509.08919)
- ChatGPT favours fresher content more than Google does (Ahrefs). OpenAI's own index overlaps only 1.5% with Bing's top 20 (RESONEO, secondary). — [Ahrefs](https://ahrefs.com/blog/do-ai-assistants-prefer-to-cite-fresh-content/); [Search Engine Watch](https://searchenginewatch.com/chatgpt-own-search-engine/)
- Academic evidence that relevance and context position, i.e., classic retrieval and SEO, outperform GEO-specific rewrites. — [C-SEO Bench](https://openreview.net/forum?id=oTeixD3oZO); [arXiv 2607.14035](https://arxiv.org/abs/2607.14035)

### Inferences
- The two positions are compatible once separated. The mechanics (crawlability, indexability, relevance, authority, quality content) are SEO. The targets differ:
  - ChatGPT retrieves for fan-out sub-queries ("pricing", "reviews", "2026", "vs"), not the head term.
  - It leans much more on third-party and earned sources.
  - It weights freshness more.
  - It uses partly non-Google indexes.
- "Rank #1 on Google" is therefore neither necessary nor sufficient for ChatGPT citation, but SEO fundamentals remain prerequisites.
- Google's "don't chunk / don't make LLM versions" advice is self-interested (it protects Google rankings), but it is consistent with the academic finding that formatting-only and rewrite tricks are unreliable.

### Gaps
- Most divergence data comes from AI-visibility vendors with a commercial interest in "GEO is different". I found no independent academic study measuring ChatGPT-versus-Google source overlap in 2026.

## Q9 (Objective synthesis). Evidence-graded list of on-site tactics for a digital agency seeking ChatGPT citations and recommendations

### Takeaway
Only a handful of on-site tactics have strong evidence. They are mostly access and retrieval prerequisites (OAI-SearchBot access, raw-HTML content, indexability, topical relevance). Content tactics such as statistics, answer-first writing, freshness, pricing transparency and comparison pages have some (mostly correlational) evidence. Schema, Bing/IndexNow and E-E-A-T page elements are speculative for ChatGPT specifically. llms.txt, FAQ schema as a lever, chunking, hidden text, cloaking and memory-poisoning prompts are myths or risky.

### Cited Findings
- See the citations in Q1–Q8. The key anchors are listed below.
  - [OpenAI crawler docs](https://developers.openai.com/api/docs/bots)
  - [Vercel/MERJ](https://vercel.com/blog/the-rise-of-the-ai-crawler)
  - [C-SEO Bench](https://openreview.net/forum?id=oTeixD3oZO)
  - [Critical GEO survey](https://arxiv.org/abs/2607.14035)
  - [Chen et al. earned media](https://arxiv.org/pdf/2509.08919)
  - [Ahrefs freshness](https://ahrefs.com/blog/do-ai-assistants-prefer-to-cite-fresh-content/)
  - [Ahrefs overlap](https://ahrefs.com/blog/ai-search-overlap/)
  - [Ahrefs schema](https://ahrefs.com/blog/schema-ai-citations/)
  - [SE Ranking via SEJ](https://www.searchenginejournal.com/new-data-top-factors-influencing-chatgpt-citations/561954/)
  - [Microsoft AI recommendation poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)
  - [Google AI features guidance](https://developers.google.com/search/docs/appearance/ai-features)

### Inferences
**Graded tactic list (my grading, based on the sources above)**

| Tactic | Grade | Why |
|---|---|---|
| Allow OAI-SearchBot (and ChatGPT-User) in robots.txt; make sure CDN/WAF bot rules don't block them; no `noindex` on target pages | **Strong evidence** | First-party OpenAI documentation: blocked sites are excluded from ChatGPT search answers |
| Core content (services, pricing, locations, case-study text) in server-rendered or static HTML | **Strong evidence** (risk mitigation) | OpenAI crawlers did not execute JS in the 2024–2026 tests. One unverified Sept 2026 anecdote suggests change, so the Vercel study is dated |
| Topically focused pages that directly answer the buyer's (sub-)query: one page per service, industry or location where real | **Strong evidence** (academic) | Relevance and retrieval position are the most reproducible levers (C-SEO Bench, critical survey, "What Gets Cited"). Focused pages beat "ultimate guides" (Growth Memo) |
| Standard SEO, indexability and authority (backlinks, referring domains) | **Strong evidence (correlational) / necessary** | Strongest SE Ranking predictor. Google says AI features need nothing extra. ChatGPT retrieval still depends on search indexes |
| Statistics, expert quotations, cited sources in text | **Some evidence** (conditional on retrieval) | Original GEO lift of about 30–40% once in context. Not reliably replicated (C-SEO Bench, E-GEO). Helps "absorption" more than "selection" |
| Original data or research the agency publishes (benchmarks, pricing surveys) | **Some evidence / plausible** | Fits the statistics, authority and "paper-style" findings, and earns third-party citations. No ChatGPT causal test |
| Answer-first writing: key definition or claim in the first third; question-style H2s; clear "X is…" statements | **Some evidence** (correlational, secondary) | Indig ski-ramp: 44% of citations from the first 30% of the page. Question headers reportedly cited more |
| Visible "last updated" dates with genuine updates; year-specific content (e.g., "2026 pricing") | **Some evidence** | ChatGPT is the most freshness-biased (Ahrefs 17M). Fan-outs frequently add the year. Fake date bumps are risky (Mueller) |
| Transparent pricing ranges / engagement minimums | **Some evidence** (fan-out data, small samples) | Fan-outs frequently add "price". 51% in a SaaS pilot |
| Comparison pages ("X vs Y", "in-house vs agency") and honest "best X" lists | **Some evidence, declining** | High citation share historically. Halved after the GPT-5.6 update (Peec). Self-ranked lists often fail to win the recommendation (Lily Ray, AIO) |
| Fast FCP/LCP | **Some evidence** (correlational) | SE Ranking: FCP under 0.4s ≈ 6.7 versus about 2.1 citations. Mechanism unproven |
| Content length >2,900 words | **Speculative / conflicting** | SE Ranking (longer = more) versus Growth Memo (focused = better) |
| Schema (Organization, ProfessionalService, LocalBusiness, Service, Review, sameAs) | **Speculative (indirect only)** | Ahrefs 1,885-page test and SSRN study: no significant direct lift. Fine as entity hygiene; keep facts in visible text |
| FAQPage schema as a ChatGPT lever | **Myth** | No lift. Slightly negative correlation in SE Ranking data. Visible Q&A content is a separate question |
| E-E-A-T page elements (author bios and credentials, team pages, case studies with numbers, client names) | **Speculative / plausible** | Source-authority research supports credibility cues in general. Agency-page effects are untested and vendor stats are weak |
| Entity consistency (NAP, services, cities) across site, GBP, LinkedIn, directories, review sites | **Speculative / plausible** | "Multiple sources agree" mechanism. Earned and third-party sources dominate ChatGPT local and brand recommendations |
| Bing Webmaster Tools, IndexNow, XML sitemaps | **Speculative for ChatGPT; useful for Copilot** | No OpenAI confirmation. OpenAI's own index is growing. BWT AI Performance measures Copilot only |
| llms.txt | **Myth** (harmless) | No citation correlation (300k domains), negligible crawler requests, Google says unused, no AI vendor confirms use |
| Chunking content into "bite-sized" LLM pieces; separate LLM-only versions | **Myth / risky** | Google explicitly advises against it. Formatting-only edits have little effect in controlled trials |
| Keyword stuffing | **Myth** | Near-zero or negative in the original GEO paper. Not transferable (survey) |
| Hidden text, prompt injection, "Summarize with AI" memory prompts, AI-user-agent cloaking | **Myth / risky** | Works in some lab and 2024 tests, but is now classed as an attack (Microsoft, SPLX). Defenses are emerging, gains erode under competition, and there is spam, reputational and possibly legal risk |

**Outdated findings to flag:**
- Original GEO results (2023–2024 engines and a simulated pipeline).
- Vercel/MERJ JS-rendering study (Dec 2024).
- Guardian hidden-text test (Dec 2024).
- Ahrefs freshness (July 2025) and top-10 overlap (2025).
- Mueller and Illyes llms.txt remarks (2025).
- Any pre-GPT-5.6 page-type citation-share data.
- The ChatGPT–Bing dependence assumption, which has weakened given the 2026 evidence on OpenAI's Labrador index.

### Gaps
- Because page fetching was blocked in this session, every number above is from search-result summaries. Verify the primary figures (SE Ranking, Indig, Peec, Ahrefs, the GEO paper) before quoting them.
- I found no controlled, production-ChatGPT experiment on any single on-site tactic for agency or professional-service websites.
- OpenAI has published nothing about ranking or citation factors beyond crawler access and noindex.
