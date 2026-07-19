---
title: "vercel-labs/deepsec: Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents"
source: "https://github.com/vercel-labs/deepsec"
published:
created: 2026-07-19
description: "Deepsec is a security harness for finding vulnerabilities in your codebase powered by coding agents - vercel-labs/deepsec"
---
`deepsec` an agent-powered vulnerability scanner that you can run in your own infrastructure, optimized to perform on-demand review of all code in existing large-scale repos.

`deepsec` is designed to surface hard-to-find issues that have been lurking in applications for a long time. It is configured to use the best models at maximum thinking levels (tunable via `--thinking-level`, see [docs/models.md](/vercel-labs/deepsec/blob/main/docs/models.md)), meaning scans can cost thousands or even tens-of-thousands of dollars for large codebases. Our customers have found the cost worth it for how quickly they were able to patch vulnerabilities that would have otherwise gone unfixed.

For large codebases, work fans out across worker machines in parallel. If a run is interrupted or errors out partway through, just re-run the same command — deepsec picks up where it left off, skipping files it already analyzed and only investigating the rest.