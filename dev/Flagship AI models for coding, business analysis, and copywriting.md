# Flagship AI models for coding, business analysis, and copywriting

**Research date:** 13 July 2026  
**Scope:** Current general-purpose text/vision models from OpenAI, Anthropic, and Google that are practical for professional building work. Deprecated models and specialized image, audio, embedding, and realtime endpoints are excluded.

## Executive recommendation

If you want one default model rather than a collection:

- **Best high-end default:** **GPT-5.6 Sol** for difficult coding, quantitative analysis, tool-heavy workflows, and structured deliverables.
- **Best quality/cost default:** **Claude Sonnet 5** while its introductory API price lasts through 31 August 2026; it is especially attractive for coding, nuanced writing, and collaborative knowledge work.
- **Best prose and judgment:** **Claude Opus 4.8** for executive analysis, editing, brand voice, and difficult long-running work where consistency matters more than lowest cost.
- **Best multimodal/grounded value:** **Gemini 3.5 Flash** for large-volume analysis, mixed media, and workflows that benefit from Google Search/Maps grounding.
- **Best budget frontier tier:** **GPT-5.6 Luna** when you want a full modern tool stack and 1.05M context without flagship pricing.

The practical operating pattern is a **two-model stack**: use a balanced model for most work, then escalate only ambiguous, high-stakes, or stubborn tasks to a flagship. My default stack would be **Claude Sonnet 5 or GPT-5.6 Terra** for daily work, with **GPT-5.6 Sol or Claude Opus 4.8** as the escalation model.

## At-a-glance comparison

Prices are standard API list prices in USD per one million input/output tokens. They do not include tool-call fees, priority processing, regional processing, or other modifiers.

| Model                  |          API price in/out |   Context | Coding | Business analysis | Copywriting | Relative speed | Best use                                            |
| ---------------------- | ------------------------: | --------: | :----: | :---------------: | :---------: | :------------: | --------------------------------------------------- |
| GPT-5.6 Sol            |                  $5 / $30 |     1.05M |  5.0   |        5.0        |     4.5     |     Medium     | Hard engineering, complex analysis, agents          |
| GPT-5.6 Terra          |               $2.50 / $15 |     1.05M |  4.8   |        4.8        |     4.4     |  Medium-fast   | Best OpenAI daily driver                            |
| GPT-5.6 Luna           |                   $1 / $6 |     1.05M |  4.3   |        4.2        |     4.1     |      Fast      | High-volume professional work                       |
| Claude Fable 5         |                 $10 / $50 |        1M |  5.0   |        5.0        |     5.0     |      Slow      | Maximum capability, long-running agents             |
| Claude Opus 4.8        |                  $5 / $25 |        1M |  5.0   |        5.0        |     5.0     |     Medium     | Judgment, prose, complex agentic work               |
| Claude Sonnet 5        |     $2 / $10 introductory |        1M |  4.9   |        4.8        |     4.9     |      Fast      | Best Claude balance; daily production               |
| Claude Haiku 4.5       |                   $1 / $5 |      200K |  3.8   |        3.8        |     4.1     | Fastest Claude | Classification, drafts, simple transforms           |
| Gemini 3.1 Pro Preview | $2 / $12 up to 200K input |        1M |  4.8   |        4.8        |     4.3     |     Medium     | Deep multimodal reasoning and long context          |
| Gemini 3.5 Flash       |                $1.50 / $9 | 1M family |  4.6   |        4.5        |     4.2     |      Fast      | Grounded, multimodal, high-throughput work          |
| Gemini 3.1 Flash-Lite  |             $0.25 / $1.50 |        1M |  3.5   |        3.5        |     3.5     |   Very fast    | Extraction, translation, routing, simple processing |

**How to read the scores:** the 1–5 numbers are editorial task-fit estimates, not universal benchmark scores. They synthesize vendor positioning, feature sets, model tier, and likely workflow fit. A 4.5 can beat a 5.0 on a particular prompt, language, repository, or agent harness. Run your own eval on representative work before committing spend.

## Model-by-model assessment

### OpenAI GPT-5.6 family

OpenAI recommends **GPT-5.6 Sol** for complex reasoning and coding, **Terra** for balance, and **Luna** for cost-sensitive workloads. All three list a 1.05M context window, 128K maximum output, image input, adjustable reasoning effort, and first-party functions, web search, file search, and computer-use tools.

- **Sol:** choose it when a wrong architectural decision, missed dependency, or shallow analysis costs more than the model call. Strongest fit for multi-step coding, financial or operational modeling, and tool-heavy agents.
- **Terra:** the sensible default for a product team standardized on OpenAI. It halves Sol's token price while keeping the same context, output ceiling, knowledge cutoff, and tool categories.
- **Luna:** use for code explanation, first-pass implementation, document analysis, research synthesis, and drafts at scale. Escalate novel architecture, subtle debugging, or board-level recommendations.

OpenAI's current catalog and prices: [OpenAI model guide](https://developers.openai.com/api/docs/models).

### Anthropic Claude family

Anthropic's current broadly available ladder is **Fable 5**, **Opus 4.8**, **Sonnet 5**, and **Haiku 4.5**. Fable, Opus, and Sonnet have 1M context and 128K synchronous output; Haiku has 200K context and 64K output.

- **Fable 5:** Anthropic's maximum-capability, widely released tier. Reserve it for the hardest long-horizon agents and high-value analysis because it costs twice Opus 4.8.
- **Opus 4.8:** the strongest practical Claude escalation model. Excellent choice when the work combines technical execution, judgment, stakeholder sensitivity, and voice.
- **Sonnet 5:** the best Claude default. It is fast, highly capable, and temporarily priced at $2/$10 per million tokens through 31 August 2026; standard pricing becomes $3/$15 on 1 September.
- **Haiku 4.5:** suitable for routing, extraction, classification, summaries, simple code edits, and inexpensive drafting. It is less attractive for autonomous repository changes or strategic conclusions without review.

Anthropic specs and standard prices: [Claude models overview](https://platform.claude.com/docs/en/about-claude/models/overview) and [Claude pricing](https://platform.claude.com/docs/en/about-claude/pricing).

### Google Gemini family

- **Gemini 3.1 Pro Preview:** use for demanding multimodal reasoning, long documents, video/image-heavy analysis, and complex coding. Its standard price rises from $2/$12 to $4/$18 when prompts exceed 200K tokens. It is a preview model, so lifecycle risk is higher than with a stable production ID.
- **Gemini 3.5 Flash:** Google's stable speed/intelligence model and the most broadly useful Gemini default. It is compelling for grounded research, multimodal pipelines, and high-volume agentic work.
- **Gemini 3.1 Flash-Lite:** a very low-cost processor for extraction, translation, classification, routing, and simple data transformation. It should not be the sole decision-maker for complex strategy or unsupervised code changes.

Google prices thinking tokens as output tokens. The paid tier does not use submitted content to improve Google's products, while free-tier content may be used. See [Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing) and [Gemini model lifecycle](https://ai.google.dev/gemini-api/docs/deprecations).

## Best model by job

### Writing and maintaining code

1. **GPT-5.6 Sol or Claude Opus 4.8** for difficult repository-scale changes, debugging, and architecture.
2. **Claude Sonnet 5 or GPT-5.6 Terra** for the best daily quality/cost balance.
3. **Gemini 3.5 Flash** when multimodal inputs, grounding, or throughput are central.
4. **GPT-5.6 Luna** for well-specified, high-volume implementation and review.

For coding, the agent harness matters almost as much as the model: repository search, shell access, test feedback, patch application, context compaction, and permission design can reverse a paper ranking.

### Business analysis

1. **GPT-5.6 Sol** for quantitative, tool-assisted, and structured analysis.
2. **Claude Opus 4.8** for judgment-heavy memos, scenario analysis, risks, and stakeholder-aware recommendations.
3. **Claude Sonnet 5 or GPT-5.6 Terra** for recurring research and operating work.
4. **Gemini 3.1 Pro** for very large or multimodal source packs.

Do not let any model invent market data. Supply primary sources or enable retrieval, require citations, separate evidence from inference, and have a human own the final recommendation.

### Copywriting and editing

1. **Claude Opus 4.8** for voice, taste, long-form consistency, and high-value final copy.
2. **Claude Sonnet 5** for most production copy and iteration.
3. **GPT-5.6 Sol/Terra** for structured campaigns, variants, SEO schemas, and copy combined with analysis or tools.
4. **Gemini 3.5 Flash** for large-scale variants, localization, and multimodal campaign inputs.

Model choice helps, but a strong brief matters more: provide audience, offer, proof, objections, voice samples, banned phrases, channel constraints, and a concrete success criterion.

## Cost scenarios

For a workload using 10M input and 2M output tokens per month, before caching or tool fees:

| Model                         | Approximate monthly inference cost |
| ----------------------------- | ---------------------------------: |
| GPT-5.6 Sol                   |                               $110 |
| GPT-5.6 Terra                 |                                $55 |
| GPT-5.6 Luna                  |                                $22 |
| Claude Fable 5                |                               $200 |
| Claude Opus 4.8               |                               $100 |
| Claude Sonnet 5, introductory |                                $40 |
| Claude Haiku 4.5              |                                $20 |
| Gemini 3.1 Pro, prompt ≤200K  |                                $44 |
| Gemini 3.5 Flash              |                                $33 |
| Gemini 3.1 Flash-Lite         |                              $5.50 |

These examples are arithmetic illustrations, not quotes. Real agent costs can be dominated by repeatedly resent context, reasoning/output tokens, search calls, and failed loops. Prompt caching and batch/flex processing can materially reduce cost.

## Procurement checklist

Before standardizing, evaluate each candidate on 20–50 tasks drawn from your actual work and track:

- [ ] task success and human correction time;
- [ ] total tokens and wall-clock time, not just per-token price;
- [ ] tool-call correctness and loop/failure rate;
- [ ] citation accuracy and unsupported claims;
- [ ] style adherence and edit distance for copy;
- [ ] security, retention, regional processing, and contractual requirements;
- [ ] stable model IDs, deprecation policy, and fallback behavior.

## Bottom line

- Choose **Claude Sonnet 5** for the best current all-round value, particularly if writing quality matters.
- Choose **GPT-5.6 Terra** for a balanced OpenAI stack with broad first-party tools.
- Escalate to **GPT-5.6 Sol** for difficult technical/analytical work or **Claude Opus 4.8** for difficult judgment/prose work.
- Choose **Gemini 3.5 Flash** when multimodal scale and Google grounding are decisive.
- Use cheap tiers for triage and volume, but keep a stronger reviewer in the loop for consequential code, analysis, and published copy.


