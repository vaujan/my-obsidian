# Low-cost and open-model report, with OpenCode Go coverage

**Research date:** 13 July 2026  
**Scope:** Every model currently documented in the OpenCode Go subscription, plus inexpensive proprietary baselines that help determine whether Go is a good fit.

## Executive recommendation

OpenCode Go is unusually good value for agentic coding: **$5 for the first month, then $10/month**, with usage budgets of **$12 per five hours, $30 per week, and $60 per month** measured at Go's internal token prices. It is not unlimited, but the monthly included usage is high relative to the subscription fee.

Recommended Go routing:

- **Default for hard coding:** **GLM-5.2** or **MiniMax M3**.
- **Best code-specialist value:** **Kimi K2.7 Code**.
- **Best long-running engineering alternatives:** **MiMo-V2.5-Pro** or **MiniMax M3**.
- **Best balanced economical model:** **Qwen3.7 Plus**.
- **Cheapest useful worker:** **DeepSeek V4 Flash** or **MiMo-V2.5** for search, triage, boilerplate, simple fixes, and subagents.
- **Best workflow:** plan/review with a strong model; delegate mechanical implementation, tests, searches, and summaries to cheap workers.

For business analysis and polished copywriting, Go can be useful, but it is primarily curated and benchmarked for coding agents. If those non-code tasks are central, compare it against Claude Sonnet 5, GPT-5.6 Luna/Terra, or Gemini 3.5 Flash rather than assuming the cheapest Go model will be equally reliable.

## What OpenCode Go includes today

The official list currently contains 13 models. The catalog may change as OpenCode tests and adds models.

| Model | Go price in/out per MTok | Est. requests / 5h | Est. requests / month | Practical role |
|---|---:|---:|---:|---|
| GLM-5.2 | $1.40 / $4.40 | 880 | 4,300 | Premium planner, complex coding |
| GLM-5.1 | $1.40 / $4.40 | 880 | 4,300 | Previous GLM fallback |
| Kimi K2.7 Code | $0.95 / $4.00 | 1,350 | 9,250 | Code-focused agent, repo work |
| Kimi K2.6 | $0.95 / $4.00 | 1,150 | 5,750 | Previous general/agentic Kimi |
| MiMo-V2.5 | $0.14 / $0.28 | 30,100 | 150,400 | Extremely cheap multimodal worker |
| MiMo-V2.5-Pro | $1.74 / $3.48 | 3,250 | 16,300 | Complex long-horizon code/agents |
| MiniMax M3 | $0.30 / $1.20 | 3,200 | 16,000 | Frontier coding, agents, multimodal |
| MiniMax M2.7 | $0.30 / $1.20 | 3,400 | 17,000 | Production engineering and debugging |
| Qwen3.7 Max | $2.50 / $7.50 | 950 | 4,770 | High-end general/agentic model |
| Qwen3.7 Plus ≤256K | $0.40 / $1.60 | 4,300 | 21,600 | Balanced daily driver |
| Qwen3.6 Plus ≤256K | $0.50 / $3.00 | 3,300 | 16,300 | Previous Qwen fallback |
| DeepSeek V4 Pro | $1.74 / $3.48 | 3,450 | 17,150 | Strong reasoning and agentic coding |
| DeepSeek V4 Flash | $0.14 / $0.28 | 31,650 | 158,150 | Cheapest fast worker |

The request counts are OpenCode's estimates based on observed Go usage patterns, including large cached contexts. They are not guaranteed quotas. Long prompts can also move Qwen Plus into a higher price band. Source: [OpenCode Go documentation](https://opencode.ai/docs/go).

## Capability comparison

The following ratings are editorial workflow-fit estimates, not cross-vendor benchmark scores.

| Model | Coding | Agent autonomy | Business analysis | Copywriting | Cost efficiency | Suggested use |
|---|:---:|:---:|:---:|:---:|:---:|---|
| GLM-5.2 | 5.0 | 5.0 | 4.5 | 4.0 | 4.0 | Plan and execute difficult changes |
| GLM-5.1 | 4.6 | 4.6 | 4.2 | 3.9 | 3.8 | Stable fallback if 5.2 regresses |
| Kimi K2.7 Code | 4.9 | 4.8 | 3.9 | 3.7 | 4.5 | Repository-scale coding and tool use |
| Kimi K2.6 | 4.4 | 4.4 | 4.0 | 3.8 | 3.8 | General agent tasks and fallback |
| MiMo-V2.5 | 3.8 | 4.0 | 3.8 | 3.5 | 5.0 | Cheap subagents, multimodal triage |
| MiMo-V2.5-Pro | 4.8 | 4.9 | 4.4 | 4.0 | 4.5 | Long-horizon execution and large codebases |
| MiniMax M3 | 4.9 | 4.9 | 4.4 | 4.1 | 5.0 | Best all-round Go candidate |
| MiniMax M2.7 | 4.6 | 4.7 | 4.2 | 3.9 | 4.8 | Debugging, SRE, production engineering |
| Qwen3.7 Max | 4.8 | 4.8 | 4.6 | 4.2 | 3.3 | Difficult general tasks when Qwen behavior fits |
| Qwen3.7 Plus | 4.5 | 4.4 | 4.3 | 4.1 | 4.8 | Balanced daily tasks under 256K context |
| Qwen3.6 Plus | 4.2 | 4.1 | 4.1 | 4.0 | 4.1 | Compatibility fallback |
| DeepSeek V4 Pro | 4.7 | 4.7 | 4.5 | 4.0 | 4.6 | Reasoning, planning, and complex code |
| DeepSeek V4 Flash | 3.9 | 4.0 | 4.0 | 3.6 | 5.0 | High-volume workers with strong verification |

## Notes on the leading Go choices

### GLM-5.2

Best treated as a premium Go planner/executor for difficult tasks and long-horizon coding. Its relative cost means it consumes the Go allowance faster than the Flash/Plus models, so route only difficult work to it.

### Kimi K2.7 Code

Kimi positions K2.7 Code as an open-source agentic coding model and reports improvements over K2.6 while using fewer tokens. It is a good default when the job is clearly repository work rather than broad prose or business analysis. See [Kimi K2.7 Code](https://www.kimi.com/resources/kimi-k2-7-code).

### MiniMax M3 and M2.7

M3 combines coding/agentic focus, native multimodality, and a context window up to 1M tokens; it is one of the most attractive models in Go at $0.30/$1.20. MiniMax describes M2.7 as especially strong in real-world engineering, debugging, observability, databases, and SRE work. Sources: [MiniMax M3](https://www.minimax.io/models/text/m3) and [MiniMax M2.7](https://www.minimax.io/news/minimax-m27-en).

### MiMo-V2.5-Pro and MiMo-V2.5

MiMo-V2.5-Pro is optimized for complex agent and coding work with a 1M context window; the non-Pro model is the cheap multimodal worker. Go's very low cached-read price makes the non-Pro tier unusually inexpensive for context-heavy subagents. See [MiMo-V2.5-Pro](https://mimo.mi.com/models/mimo-v2.5-pro) and [MiMo-V2.5 release notes](https://mimo.mi.com/docs/en-US/news/latest/v2.5-open-sourced).

### DeepSeek V4 Pro and Flash

Both V4 variants support multiple reasoning-effort levels and 1M context in DeepSeek's published model materials. Pro is the stronger planner; Flash is a much cheaper worker. Flash's economics are excellent, but consequential changes should be tested and reviewed by a stronger model or a human. See [DeepSeek V4 announcement](https://api-docs.deepseek.com/news/news260424/) and [DeepSeek V4 Pro model card](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro).

### Qwen3.7 Max and Plus

Max is the expensive high-capability route; Plus is the more compelling Go daily driver. Watch the 256K threshold: OpenCode documents higher input/output/cache prices beyond it. Use explicit compaction or new sessions to avoid paying the long-context tier accidentally.

## “Open source” versus “open weight” versus hosted access

Do not treat these terms as interchangeable:

- **Hosted in Go** means OpenCode exposes an API endpoint for the model.
- **Open-weight** means downloadable weights exist, but the license may still restrict use.
- **Open source** should ideally cover weights, code, and a license permitting the intended use; vendors use the phrase inconsistently.

OpenCode markets Go as access to open coding models, but this report does **not** assume every Max/Plus/Pro endpoint has downloadable weights under the same terms as the hosted service. Verify the exact checkpoint and license before self-hosting, redistributing, fine-tuning for customers, or using output in a regulated workflow.

Models with clear current first-party open-weight/open-source signals include Kimi K2.7 Code, DeepSeek V4, and the MiMo V2.5 series. MiniMax announced/opened M3 materials around launch, but verify the exact current repository and license. Treat GLM and Qwen hosted variants individually rather than inferring license status from the family name.

## How Go compares with cheap proprietary APIs

| Alternative | API price in/out per MTok | Main advantage | When it may beat Go |
|---|---:|---|---|
| GPT-5.6 Luna | $1 / $6 | OpenAI tool stack, 1.05M context | Consistency and first-party tools matter more than subscription value |
| Claude Haiku 4.5 | $1 / $5 | Fast Claude behavior and prose | Lightweight writing, classification, Claude ecosystem |
| Gemini 3.5 Flash | $1.50 / $9 | Stable, multimodal, Search/Maps grounding | Grounded research and mixed-media production |
| Gemini 3.1 Flash-Lite | $0.25 / $1.50 | Very cheap multimodal API, free tier | Simple extraction/translation with direct API control |
| GPT-5.4 mini | $0.75 / $4.50 | Strong coding/subagent tier | You need OpenAI Responses tools and predictable API semantics |

Go usually wins on included value for coding agents. Direct APIs can win on stable model IDs, enterprise controls, provider-native tools, latency guarantees, and support. Subscription access also creates concentration risk: the catalog, internal prices, and usage estimates can change.

## Recommended OpenCode routing policy

Use four roles rather than one model for everything:

| Role | Preferred models | Responsibilities |
|---|---|---|
| Planner | GLM-5.2, MiniMax M3, MiMo-V2.5-Pro | Decompose work, identify risks, define tests |
| Builder | Kimi K2.7 Code, MiniMax M3/M2.7, Qwen3.7 Plus | Implement scoped changes and run tools |
| Cheap worker | DeepSeek V4 Flash, MiMo-V2.5 | Search, summarize, generate boilerplate, run repetitive subtasks |
| Reviewer | GLM-5.2, DeepSeek V4 Pro, or an external frontier model | Inspect diffs, test evidence, security, and requirement coverage |

Keep planner and reviewer independent for important changes. A model is more likely to overlook the same assumption when reviewing its own plan and implementation.

Example model IDs in OpenCode use the `opencode-go/` prefix, such as `opencode-go/kimi-k2.7-code`. The current list can be checked interactively with `/models` or through OpenCode's documented models endpoint.

## Operational caveats

- Go is limited by dollar-value budgets, not a fixed request count. Long contexts, reasoning, and loops alter actual usage.
- The official request estimates assume very large cached contexts, so they should be treated as directional.
- Only one member per OpenCode workspace can subscribe to Go.
- After Go limits are reached, free models remain available; a Zen balance can optionally fund overage.
- OpenCode says Go providers use zero retention and do not train on submitted data, with hosting in the US, EU, and Singapore. Confirm contractual details for sensitive or regulated data.
- A cheap model that loops, makes broad edits, or requires heavy review can cost more in engineer time than a premium model.

OpenCode's current terms, limits, prices, endpoint IDs, and privacy description are documented on [OpenCode Go](https://opencode.ai/docs/go); the marketing overview is at [OpenCode Go plans](https://opencode.ai/go).

## Bottom line

At $10/month, OpenCode Go is worth trying for anyone doing regular agentic coding. Start with **MiniMax M3** as the general Go default, **Kimi K2.7 Code** for code-specialized work, **GLM-5.2** for difficult planning, and **DeepSeek V4 Flash or MiMo-V2.5** for cheap worker tasks. Keep a premium external model available for final review of high-risk code, strategic business conclusions, or publication-quality copy.


