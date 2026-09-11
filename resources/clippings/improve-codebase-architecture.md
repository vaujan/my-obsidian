---
title: "improve-codebase-architecture — mattpocock/skills"
source: "https://www.skills.sh/mattpocock/skills/improve-codebase-architecture"
published:
created: 2026-08-22
description: "Scan a codebase for deepening opportunities, present them as a visual HTML report, then grill through whichever one you pick."
---

## improve-codebase-architecture

Installation

Summary

**Analyze codebases for architectural friction and propose module-deepening refactors as testability improvements.**

- Explores codebases organically to surface shallow modules, tightly-coupled components, and untested seams rather than following rigid heuristics
- Applies John Ousterhout's "deep module" principle: small interfaces hiding large implementations for better testability and AI navigability
- Generates multiple radically different interface designs (minimalist, flexible, caller-optimized, ports & adapters) via parallel sub-agents, then recommends the strongest approach
- Creates GitHub issue RFCs documenting the problem space, design trade-offs, and refactoring rationale

SKILL.md

## Improve Codebase Architecture

Surface architectural friction and propose **deepening opportunities**: refactors that turn shallow modules into deep ones. The aim is testability and AI-navigability.

This command is *informed* by the project's domain model and built on a shared design vocabulary:

- Call the Skill tool with "codebase-design" for the architecture vocabulary (**module**, **interface**, **depth**, **seam**, **adapter**, **leverage**, **locality**) and its principles (the deletion test, "the interface is the test surface", "one adapter = hypothetical seam, two = real"). Use these terms exactly in every suggestion, and don't drift into "component," "service," "API," or "boundary."
- The domain language in `CONTEXT.md` gives names to good seams; ADRs in `docs/adr/` record decisions this command should not re-litigate.

## Process

### Explore

**Scope before you scan: YAGNI.** Deepening a module pays off by making future changes to it easier, so put extra weight on the parts of the codebase that have recently changed. Decide *where* to look before you look:

- If the user named a direction (a module, a subsystem, a pain point), take it, and skip the inference below.
- Otherwise, walk back a good stretch of the commit history (`git log --oneline`) to find the codebase's hot spots, the files and areas that keep coming up, and let those paths pull your attention first. If the changes are scattered with no clear hot spot, widen the net.

Read the project's domain glossary (`CONTEXT.md`) and any ADRs in the area you're touching first.

[mattpocock/skills](https://github.com/mattpocock/skills "mattpocock/skills")
