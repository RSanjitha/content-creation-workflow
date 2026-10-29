# Claude Code — SEO & Content Team Workspace

## Workspace Overview

This is the SEO and content team workspace. It produces blog posts and long-form content for an AI-driven social media platform.

## Directory Structure

```
claude test/
├── Project Docs/
│   └── Predis Context Document.md   ← Brand context, voice guidelines, writing rules
├── New blogs/                        ← Output: newly created blog posts
└── Updated blogs/                    ← Output: revised/updated existing blog posts
```

## Brand Context — Always Load at Runtime

Before generating any content or building any skill/agent, read the full brand context file:

**Path:** `Project Docs/Predis Context Document.md`

This file contains:
- Company overview and product details
- Target customer segments
- Brand voice and writing style rules
- Content quality standards (plagiarism policy, tone rules)
- Verified statistics and claims approved for use
- Blog taxonomy and content categories
- Agent usage notes

Never rely on memory for brand details — always load from the context file at runtime.

## Output Conventions

- **New blog posts** → save to `New blogs/` as `.md` files
- **Updated/revised blog posts** → save to `Updated blogs/` as `.md` files
- File names: use kebab-case, e.g. `best-instagram-reel-ideas-2025.md`

## Skills — Design Principles

- Skills define **workflow and process only** — no brand-specific content baked in
- Skills must pull brand context at runtime by reading `Project Docs/Predis Context Document.md`
- Skills must work correctly if the brand context file is swapped out for a different brand
- Do not hardcode product names, statistics, CTAs, tone descriptors, or audience definitions into skill files

## Agents — Design Principles

- Agents must be **brand-agnostic at definition time** — no hardcoded brand details
- Each agent reads `Project Docs/Predis Context Document.md` at the start of every run
- Each agent has a **single, clearly scoped role** with no overlap with other agents
- Agent roles should be defined in terms of the task (e.g. "keyword researcher", "blog writer", "content updater"), not the brand
- Agents must not invent statistics — use only verified claims from the context document

## Content Quality Rules (Summary)

Full rules live in the context document (Section 13). Key enforced constraints:

1. **Zero plagiarism** — every sentence must be original; synonymizing existing content is not sufficient
2. **Outcome-first sentences** — lead with results, not process
3. **Active voice only** — no passive constructions
4. **Short sentences** — split any sentence over 25 words
5. **No filler phrases** — ban: "In today's fast-paced world", "It goes without saying", "In conclusion", etc.
6. **No hollow adjectives** — avoid: cutting-edge, seamless, robust, revolutionary, state-of-the-art unless backed by a specific claim
7. **Verified stats only** — do not invent numbers; use only the approved claims in the context document
8. **Second-person address** — always speak directly to the reader ("you/your")

## Blog Post Format

- H2/H3 headers for structure
- Short intro paragraph
- Numbered or bulleted sections where helpful
- One CTA per post
- File format: Markdown (`.md`)

---

## Agent Routing Rules

### When NOT to spin up an agent

Handle directly (no delegation) for:
- Quick edits to a single file — use the Edit tool
- One-off questions about brand voice, writing rules, or context file contents — read the file and answer
- A single bounded action (fix a meta description, rewrite one paragraph, check a stat) — do it inline
- Explaining what an agent or skill does — answer directly

**Rule of thumb:** if the task is a single action that one tool or skill can complete in one step, do it directly. Only delegate when the task is multi-step, open-ended, or requires the agent to synthesize decisions across several stages.

---

### Routing table

| User request | Route to | Notes |
|---|---|---|
| "Write a new blog post about X" / "Create a post for [keyword]" / "Write a post from this brief" | `/blog-writer` skill | New content creation. Invoke as a skill, not an agent. |
| "Do keyword research for X" / "Find keywords for [topic]" / "What should we write about?" / "Find content gaps in our keyword list" | `keyword-researcher` agent | Multi-step: discovery, SERP analysis, scoring, clustering, gap analysis, CSV export. Delegate even for a single topic — the 8-phase process and 50-keyword minimum warrant it. |
| "Prioritise this list of posts" / "Which posts need updating most urgently?" | `update-priority-checker` agent | Batch triage only — no audit or rewrite. Use when the user wants a priority queue without triggering a full update. |
| "Audit this post" / "What's wrong with this post?" / "Run a quality check" (no rewrite wanted) | `update-researcher` agent | Produces the improvements report (Document 1) only. Use when the user wants findings without a rewrite. |
| "Rewrite this post using this audit report" (improvements report already exists) | `update-writer` agent | Use only when an improvements report from update-researcher already exists. Do not invoke without a prior audit. |
| "Update/refresh this blog post" / "Improve this existing post" / "Audit and rewrite" / "Full update" | `content-updater` agent | Use when the task requires all three stages: prioritise (optional), audit, and rewrite. Content-updater orchestrates the full workflow end-to-end. |
| "Create infographics for this blog post" / "Generate visuals for [post URL or file]" | `blog-infographic-designer` agent | Full pipeline: content analysis, infographic planning, PNG generation (AI or Pillow), placement guide. Always delegate — this is inherently multi-step. |

---

### Parallel delegation

When a request covers multiple independent deliverables, delegate in parallel:
- Keyword research for topic A + keyword research for topic B → two `keyword-researcher` agents simultaneously
- Infographics for post A + update post B → `blog-infographic-designer` and `content-updater` simultaneously

Do not serialize work that has no dependency between tasks.
