# Blog Writer

Write a new SEO-optimized blog post that ranks on Google and reads like it was written by a thoughtful human expert.

## Runtime Setup

Before writing anything, read the brand context file at:
`Project Docs/Predis Context Document.md`

Extract and apply:
- Brand name and product details
- Target audience segments
- Brand voice and tone rules
- Verified statistics (use only these — never invent numbers)
- CTA patterns
- Content categories and blog taxonomy
- Any agent usage notes specific to blog content

All brand-specific decisions (product name, stats, CTAs, audience tone) must come from this file at runtime. Never rely on memory or hardcode brand details into this skill.

---

## Input

The user will supply one of:
- A blog title
- A keyword or topic
- A full brief

Apply the edge case rules in Step 4 to handle each case.

---

## Step 1 — Research the Topic

Do not skip this step. Web research is required before writing.

### 1a. Identify the Primary Keyword

Pick a broad, high-volume keyword — not a niche long-tail phrase. Think umbrella term with significant search demand.

**Good examples:**
- "AI content creation" (broad, high volume)
- "social media scheduling" (broad, competitive)

**Avoid:**
- "how to use AI to write Instagram captions faster" (too specific for primary)

Estimate the keyword's metrics honestly:
- **Search volume:** rough monthly searches (e.g. ~10K/mo, ~50K/mo)
- **Keyword difficulty (KD):** Low / Medium / High / Very High
- **Search intent:** Informational / Navigational / Commercial / Transactional

### 1b. Identify Long-Tail Keywords

Find 5–8 long-tail variations that support the primary keyword. These are specific, lower-competition phrases that reinforce topical depth. They go into the body naturally — in subheadings, sentences, and FAQ sections where present.

### 1c. Analyze Competing Content

Search for the primary keyword and examine what the top 10 results cover. Identify:
- What angle do most posts take?
- What subtopics appear in nearly every ranking post?
- What is missing? (shallow treatment, outdated info, no examples, no data, skipped use cases)

The content gap is the post's differentiation angle. The post must cover everything top results cover, plus fill at least one clear gap they don't.

---

## Step 2 — Plan the Post (Internal — Do Not Show the User)

Work out privately:
- **Target audience:** who is this for, and what do they already know?
- **Tone:** calibrate based on post type:
  - Thought leadership / opinion → confident, first-person, punchy
  - How-to / tutorial → clear, numbered steps, patient
  - Product/category explainer → authoritative but plain
  - Trend analysis → analytical, forward-looking
- **Content gap:** the one angle top results skip that this post will address
- **Post format:** listicle, how-to guide, explainer, comparison, data post, trend post — choose based on topic and search intent

---

## Step 3 — Write the Post

### Structure

```
[H1: Title — primary keyword near the front, 50–60 characters]

[Hook — 2–3 sentences. A sharp observation, a surprising stat, or a direct address to the reader's problem. Never a definition. Never "In today's fast-paced world..."]

[Quick Answer / Summary Table — on list posts and research posts: a scannable table summarizing the main points. Place right after the intro. Helps skimmers and improves featured snippet chances.]

[Jump-to Table of Contents — descriptive, benefit-led anchors, not generic section names]

[Section 1: Set up the problem or context]
[Section 2: Core insight / main argument / how-to steps]
[Section 3: Real examples or case studies — see rules below]
[Section 4: Comparison or data table — see rules below]
[Section 5: Nuance, caveats, or deeper dive]
[Section 6: Practical takeaways or next steps]
[Mid-article CTA — place at the 50–60% mark, once the reader has consumed enough value]
["How to do this with [Brand]" section — one dedicated section showing how the brand's product maps to the post's main topic. 3–5 steps. Position it where the reader naturally asks "okay, but how do I actually do this?"]
["More like this" section — minimum 3 related internal links at the bottom]

[Conclusion — 2–3 sentences. Forward motion, something to think about or do. Not a recap of what was just said.]
[Optional: Final CTA — short, action-first, low-friction, matching the brand's CTA patterns from the context file]
```

### Real Examples or Case Studies

Include at least one real-world example, mini case study, or "how X company did Y" story. Options:
- A known brand doing the tactic being described
- A realistic hypothetical anchored in a specific business type
- A pattern observed across similar businesses

Use examples relevant to the brand's actual audience — not just mega-corporations. If the brand's audience is SMBs, solopreneurs, or e-commerce brands, reflect that in the examples.

When citing a brand example, give at least 3 specific reasons why the example works — not a vague one-liner.

### Comparison or Data Table

If the topic lends itself to a comparison, feature list, tool breakdown, pros/cons, or "X vs Y" — include a Markdown table. Good candidates:
- Tool comparisons
- Strategy options
- Tier breakdowns
- Step-by-step flows with outcomes
- Platform-by-platform breakdowns

Skip the table only if forcing one would feel genuinely awkward — and flag this in the SEO checklist with a reason.

### Brand Mention

Somewhere in the post — naturally, not as an ad — mention the brand as a relevant tool, example, or reference. Work it into a sentence the way you'd mention any tool you genuinely use. It should feel like the writer happened to know about it. One mention is enough unless the post is specifically a product how-to.

If the brand doesn't fit naturally in the topic, mention it in the context of its product category (e.g. AI tools for content, social media scheduling) — find a natural home, don't force a non-sequitur.

### Per-Platform Breakdowns

For any post covering platform-specific topics (posting times, formats, analytics, trends), break the content into per-platform subsections. Never give one-size-fits-all answers on platform topics.

### Internal Linking

Every mention of a concept that has a related brand blog post or feature page behind it should carry an internal link. High-traffic posts must route readers toward related content — never leave them as dead ends.

---

## SEO Rules (Non-Negotiable)

- Primary keyword in: H1 title, first 100 words, at least one H2, and the meta description
- Long-tail keywords: woven into subheadings and body copy naturally — never forced or stuffed
- Meta description: must contain the primary keyword, 150–160 characters, written to earn the click
- Title: 50–60 characters; lead with the keyword or a strong hook word
- H2s: descriptive and literal — treat them as content signals, not creative headlines
- No keyword stuffing: primary keyword no more than once every ~300 words
- Tables: use Markdown table syntax — they improve featured snippet placement chances
- Publish/update date: include prominently on time-sensitive posts; add "(Updated [Month Year])" in the title for living-document posts

---

## Human-Sounding Writing Rules

These matter as much as the SEO rules.

**Open with a real observation, not a definition.** A specific fact, a counterintuitive claim, a short story, or a direct question to the reader.

**Write in plain language.** The reader is smart but busy. No jargon unless unavoidable — if used, define it in one plain sentence immediately after.

**Show genuine opinions.** Hedge less. "This works best when..." not "some might argue that...". Authority reads as human.

**Use concrete examples.** Abstract claims feel machine-generated. Specifics feel real.

**Vary structure.** Mix paragraphs, short punchy lines, and bullets. Don't make every section the same shape.

**Establish stakes before solutions.** Frame why this matters before jumping into tactics. Structure: problem context → solution.

**End with forward motion.** The last line gives the reader something to think about or do — not a restatement of what they just read.

**Avoid AI tells:**
- ❌ "It's worth noting that..."
- ❌ "In conclusion, we have explored..."
- ❌ "Delve into", "leverage", "utilize", "robust", "at the end of the day", "game-changer"
- ❌ Sentences starting with "This means that..." or "This is because..."
- ❌ Paragraphs opening with "Furthermore," or "Moreover,"
- ✅ Plain verbs: use, build, run, help, cut, find, write, ship
- ✅ Contractions where they feel natural
- ✅ Occasional rhetorical questions — not in every section

---

## Brand Voice Rules (From Context File)

Apply the specific voice rules loaded from the brand context file. Generally enforce:
- Outcome-first sentences: lead with results, not process
- Active voice only — no passive constructions
- Short sentences — split any sentence over 25 words
- Second-person address ("you/your") — speak directly to the reader
- No filler phrases: "In today's fast-paced world", "It goes without saying", "In conclusion", "Needless to say", "As we all know"
- No hollow adjectives without a backing claim: cutting-edge, seamless, robust, revolutionary, state-of-the-art
- Verified stats only — use only numbers confirmed in the brand context file; never invent figures
- Preserve irreverent, self-assured edge where appropriate — professional but never corporate-dry

---

## Length Rules

| Request | Target |
|---|---|
| Default (no length specified) | 1,500–1,800 words |
| "Long post" / "deep dive" / "pillar" | 2,000–2,500 words |
| "Short" explicitly requested | 1,200 words minimum — note if asked |

**Minimum is 1,500 words. No exceptions on default requests.**

---

## Step 4 — Format the Output

Deliver in this exact order:

---

### 📊 Keyword Brief

| | |
|---|---|
| **Primary keyword** | [keyword] |
| **Est. monthly search volume** | [e.g. ~18,000/mo] |
| **Keyword difficulty** | [Low / Medium / High / Very High] |
| **Search intent** | [Informational / Commercial / etc.] |
| **Content gap addressed** | [One sentence: what top results miss that this post covers] |

**Long-tail keywords used:**
1. [keyword 1]
2. [keyword 2]
3. [keyword 3]
4. [keyword 4]
5. [keyword 5]

---

### 📝 Blog Post

[Full post in Markdown, minimum 1,500 words]

---

### 🔍 SEO Checklist

- Primary keyword in title: ✓ / ✗
- Primary keyword in first 100 words: ✓ / ✗
- Primary keyword in at least one H2: ✓ / ✗
- Primary keyword in meta description: ✓ / ✗
- Long-tail keywords placed naturally: ✓ / ✗
- Table included: ✓ / ✗ (if ✗, reason: [why])
- Brand mentioned naturally: ✓ / ✗
- "How to do this with [Brand]" section included: ✓ / ✗
- Quick Answer / summary table included: ✓ / ✗
- Per-platform breakdowns included (if applicable): ✓ / ✗ / N/A
- Mid-article CTA placed: ✓ / ✗
- Related posts section at bottom: ✓ / ✗
- Estimated word count: ~[N] words

**Meta description** (150–160 chars, contains primary keyword):
> [meta description here]

---

## Step 5 — Save the Output

After generating the complete output (Keyword Brief + Blog Post + SEO Checklist), save the blog post section as a `.md` file in the `New blogs/` folder.

File naming: kebab-case matching the post title. Example: `best-instagram-reel-ideas-2025.md`

Confirm the file path to the user once saved.

---

## Edge Cases

| Input type | How to handle |
|---|---|
| Title only | Treat as topic + implied keyword; infer audience and angle from brand context |
| Keyword only | Target it; default to informational intent; infer format from SERP landscape |
| Full brief | Follow it; fill gaps with judgment; flag any conflicts with brand context |
| Specific word count requested | Hit it within ±10%; never go below 1,500 words without flagging it |
| Guest blog requested | Apply all the same rules; omit or adjust brand-specific CTAs and product sections as appropriate; confirm with user before saving to `New blogs/` |

---

## Do / Don't Reference

| Do | Don't |
|---|---|
| Jump-to table of contents with benefit-led anchors | Open with "In today's fast-paced world…" or a dictionary definition |
| Contrarian or uncomfortable truth in the intro | Use mega-brand examples with no relevance to the actual audience |
| Cited third-party stats per major section | Publish data claims without sources |
| Quick Answer / summary table on list posts | Place all CTAs only at the end |
| Per-platform breakdowns on platform-specific topics | Write broad posts with no audience segmentation |
| Inline CTAs tied to the specific section content | Keep TOFU posts as dead ends with no internal links |
| "How to do this with [Brand]" section in every guide | Describe product features generically without showing real use |
| Author name, publish date, last-updated date | Leave time-sensitive posts without an update timestamp |
| "More like this" related posts section at the bottom | Publish without a related content section |
| Audience-relevant examples (SMBs, solopreneurs, agencies) | Default only to Fortune 500 brand examples |
| Proprietary data or brand-native stats where available | Invent statistics or cite unverifiable numbers |
