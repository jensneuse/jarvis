# YouTube Content Playbook

Instructions for an agent to transform source content (blog posts, docs, ideas) into structured YouTube episode packages.

## Who This Is For

Jens Neuse, CEO of WunderGraph. The channel covers GraphQL, API architecture, GraphQL Federation, and AI-related developer topics. The audience is professional developers and technical leaders.

## Output Structure

Given source content, produce this directory structure:

```
youtube/episodes/<episode-slug>/
  README.md           # Episode overview, metadata, and chapter summary
  thumbnail.md        # Thumbnail concept and title options
  chapter-01-hook/
    script.md         # Spoken word script for this chapter
    notes.md          # Visual directions, B-roll cues, diagram descriptions
    examples/         # Code snippets, config files, or example data (if applicable)
  chapter-02-<name>/
    script.md
    notes.md
    examples/
  chapter-03-<name>/
    script.md
    notes.md
    examples/
  ... (as many chapters as needed)
```

---

## Episode README.md Template

```markdown
# Episode: <Title>

## Metadata
- **Target length**: <X> minutes
- **Format**: <explainer | deep-dive | hot-take | tutorial | comparison>
- **Target audience**: <description>
- **Search keywords**: <comma-separated>
- **Publish day**: Tuesday or Wednesday, 9 AM EST

## One-sentence thesis
<The single core idea this video communicates.>

## Description (for YouTube)
<First 2 lines: hook + primary keyword. These show in search results.>

<Body: 150-300 words with natural keyword usage.>

## Chapters
1. [0:00] <Chapter name> - <one-line summary>
2. [X:XX] <Chapter name> - <one-line summary>
3. [X:XX] <Chapter name> - <one-line summary>
...

## Hashtags
#tag1 #tag2 #tag3 (max 5)
```

---

## Episode thumbnail.md Template

```markdown
# Thumbnail Concept

## Style
<One of: diagram-driven | face-reaction | logo-comparison | icon-driven>

## Visual description
<Describe the thumbnail image: what's shown, layout, colors.>

## Text on thumbnail
<3-4 words max, bold sans-serif, readable at mobile size.>

## Color palette
<Dark background (navy/charcoal) + 1-2 accent colors (orange/cyan, yellow/blue, or red/white).>

## Title options (pick best CTR)
1. <option — under 60 chars, front-load keyword>
2. <option>
3. <option>
4. <option>
5. <option>

## Title-thumbnail relationship
<Title and thumbnail must complement, not duplicate. Explain how they work together.>
```

---

## Chapter script.md Template

```markdown
# Chapter: <Name>

**Duration**: ~<X> minutes
**Visual mode**: <talking-head | screen-recording | diagram-animation | whiteboard | mixed>

---

<Script text here. Written for spoken delivery, not reading.>

<Use [VISUAL: description] inline cues for what should be on screen.>
<Use [CUT TO: description] for scene transitions.>
<Use [CODE: filename] to reference code in the examples/ folder.>
<Use [DIAGRAM: description] for animated diagram moments.>
```

---

## Chapter notes.md Template

```markdown
# Visual & Production Notes: <Chapter Name>

## On-screen visuals (in order)
1. <timestamp> — <what's on screen>
2. <timestamp> — <what's on screen>

## B-roll / inserts
- <description of any meme inserts, stock footage metaphors, or screen recordings>

## Diagrams to create
- <description of each diagram, including what to reveal progressively>

## Code to show
- <reference to files in examples/, with notes on which lines to highlight>
```

---

## How to Transform Source Content

When given a blog post, doc, or idea, follow these steps:

### Step 1: Extract the thesis

Read the source and write one sentence: "The key idea is ___."

This becomes the throughline for the entire video. Everything in the video must serve this idea. If the source covers multiple ideas, pick the strongest one or split into multiple episodes.

### Step 2: Choose the format

| Format | When to use | Target length |
|---|---|---|
| **Explainer** | Concept needs clear explanation | 8-12 min |
| **Deep dive** | Architecture, system design, under-the-hood | 12-20 min |
| **Hot take** | Reacting to news, controversial opinion | 8-12 min |
| **Tutorial** | Build something step by step | 15-25 min |
| **Comparison** | X vs Y, tradeoff analysis | 10-15 min |
| **Quick hit** | Single concept, high density | 3-5 min |

### Step 3: Write the hook (Chapter 1)

The first 30 seconds determine everything. Use one of these patterns:

- **The Contrarian**: "Everyone says [X], but they're wrong."
- **The Consequence**: "If you're using [X] like this, your production system will fail."
- **The Question**: "How does [company] serve 10 million requests per second?"
- **The News Peg**: "[Framework] just released v4, and it changes everything."
- **The Demo First**: Show the end result in the first 10 seconds, then explain how.
- **The Story**: "Last month, we had an outage that taught us..."

Rules for the hook:
- No "hey guys", no channel intro, no "in this video we'll..."
- Start mid-thought or with a provocative statement
- Create an open loop (mention something you'll explain later)
- First visual must be interesting (diagram, code result, animation) -- never a static frame

### Step 4: Structure the body (Chapters 2-N)

Break the core content into 3-5 segments. Each segment should:
- Cover one concept (max 3 minutes per concept)
- Include a visual demonstration (code, diagram, demo)
- End with a mini-summary or transition to the next segment
- Change the visual mode at least once within the segment

Use this structure for body chapters:

```
1. State what you'll explain in this segment (5 seconds)
2. Explain the concept (60-90 seconds, with diagrams/visuals)
3. Show proof / demo / code (60-90 seconds)
4. Summarize the key takeaway (10 seconds)
5. Transition to next segment with an open loop (10 seconds)
```

Place the most interesting content or a pattern interrupt around the 40-60% mark of the video. This is where retention typically dips.

### Step 5: Write the CTA chapter

Place the first CTA at ~40% through the video (brief, 3-5 seconds: "if this is helpful, a like helps the algorithm").

Final chapter (30-60 seconds):
- Summary of 2-3 key takeaways
- What to do next (try it, read the docs, watch next video)
- Comment prompt: ask a genuine question ("What's your experience with X?")
- Brief subscribe CTA tied to future value ("Next week I'm covering Y")

### Step 6: Generate thumbnail and title options

Create 5 title options using these formulas:
1. "[Tech] in [Time Constraint]" -- e.g., "GraphQL Federation in 10 Minutes"
2. "Why [Popular Thing] is [Contrarian Take]" -- e.g., "Why REST is Holding You Back"
3. "How [Big Company] Handles [Problem]" -- e.g., "How Netflix Scales GraphQL"
4. "[X] vs [Y] -- Which Should You Use?" -- e.g., "Federation vs Schema Stitching"
5. "Stop Using [X]. Do [Y] Instead" -- e.g., "Stop Writing Resolvers by Hand"
6. "I Built [X] and Here's What Happened"
7. "[Number] [Topic] Mistakes Every Developer Makes"
8. "The [Adjective] Guide to [Topic]"

Rules:
- Under 60 characters
- Front-load the most searchable keyword
- Use CAPS on max 1-2 words for emphasis
- Title and thumbnail must complement, not duplicate

Thumbnail should use:
- Dark background (navy/charcoal)
- 1-2 accent colors
- Max 3-4 words in bold sans-serif
- One clear visual element (tech logo, simplified diagram, or expressive face)
- Must be readable at mobile thumbnail size (~160x90px)

### Step 7: Adapt the source content for spoken delivery

When converting written content to script:

- **Cut 40% of the source.** A 2000-word blog post becomes ~1200 words of script (about 8 minutes at 150 wpm).
- **Short sentences.** If a sentence has a comma, consider splitting it.
- **One concept per sentence.** Viewers can't re-read; they must understand it the first time.
- **Use analogies.** "GraphQL is like ordering from a menu where you write down exactly what you want" beats a formal definition.
- **Say "you" constantly.** "You might be thinking..." / "When you deploy this..."
- **Convert text explanations to visual cues.** Every paragraph explaining a concept should become a [DIAGRAM] or [CODE] cue, not just narration.
- **Add personality.** Opinions, reactions, anecdotes that wouldn't be in the blog post: "When I first saw this, I thought it was insane. But then..."
- **Progressive revelation.** Don't present a complete picture then discuss it. Build it up piece by piece.

### Step 8: Write visual directions

For each chapter, specify:

- What's on screen at each moment (talking head, code, diagram, terminal, website)
- Diagram build-up sequence (never show a complete diagram at once -- animate it piece by piece)
- Code reveal sequence (build line by line or block by block, highlight the new/important parts)
- Where to zoom in on code (specific lines, 1.5-2x zoom)
- Pattern interrupts every 2-3 minutes (visual change, topic shift, humor)
- The visual should change every 30-60 seconds maximum

---

## Scripting Rules

### Voice and tone
- Direct, confident, opinionated
- Talk to one person, not an audience ("Let me show you" not "I'm going to show you all")
- Push back on conventional wisdom when warranted
- Use real production experience and WunderGraph/Cosmo examples as credibility anchors
- No filler phrases ("so basically", "you know", "kind of like")

### Pacing
- Target 140-160 words per minute (slightly faster than conversational)
- Slow down for complex concepts
- Speed up for context/background sections
- Never let the same visual sit for more than 60 seconds

### Open loops
- Throughout the script, plant forward references: "We'll see why this matters in a second"
- These measurably improve retention by giving viewers a reason to keep watching

### Analogies for API/GraphQL concepts
When explaining technical concepts, always include a real-world analogy. Examples:
- Federation = "Instead of one massive restaurant menu, each kitchen publishes its own menu, and the host combines them for the customer"
- API Gateway = "A bouncer at a club who checks your ID, tells you where to go, and makes sure you don't cause trouble"
- Schema stitching = "Duct-taping separate documents together vs. writing them as one coherent piece"
- Rate limiting = "A traffic light that only lets a certain number of cars through per minute"

---

## Content Format Reference

### For a GraphQL/API channel, prioritize these formats:

**70% Searchable/Evergreen** (compounds over time)
- Concept explainers: "What is GraphQL Federation?"
- Architecture breakdowns: "How [Company] Scales Their API"
- Comparisons: "REST vs GraphQL vs gRPC"
- Tutorials: "Build a Federated API from Scratch"

**20% Trending/Timely** (establishes thought leadership)
- React to new spec releases, industry news, major migrations
- Hot takes on API trends, AI in API development
- "[Company] just switched to [tech] -- here's why"

**10% Personal/Community** (builds loyalty)
- Behind the scenes at WunderGraph
- Lessons learned as a founder
- "How we built [feature] in Cosmo"

---

## SEO Checklist

For each episode, ensure:

- [ ] Title under 60 chars, primary keyword front-loaded
- [ ] Description: first 2 lines contain hook + keyword
- [ ] Description: full timestamps/chapters included
- [ ] Description: 150-300 word body with natural keyword usage
- [ ] Description: 3-5 hashtags (first 3 appear above title)
- [ ] Tags include: primary keyword, related terms, long-tail variations
- [ ] Thumbnail is readable at mobile size
- [ ] Playlist assignment identified
- [ ] End screen points to related video
- [ ] Pinned comment drafted (resources + engagement question)

---

## Production Quality Checklist

- [ ] Hook is in the first 15-30 seconds, no throat-clearing
- [ ] No segment exceeds 3 minutes without a visual change
- [ ] Code is zoomed to relevant lines (never full IDE at default zoom)
- [ ] Diagrams are built progressively (not shown complete first)
- [ ] CTA placed at ~40% mark (brief) and at end
- [ ] Script reads naturally when spoken aloud
- [ ] Every chapter has at least one [VISUAL], [DIAGRAM], or [CODE] cue
- [ ] Open loops are planted in at least 2 places
- [ ] Comment prompt asks a genuine question about the topic
