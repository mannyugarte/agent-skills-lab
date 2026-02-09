---
name: talk-to-camera-script-converter
description: Convert transcribed voice memos into short-form talk-to-camera video scripts optimized for pause-and-cut recording. Produces line-by-line scripts, hook alternatives, CTAs, SEO captions, and hashtags tailored to specific platforms (TikTok, Instagram Reels, YouTube Shorts, YouTube Long-form). Use when user provides a voice memo transcript and wants a video script, selfie video script, talking head script, or short-form content script. Triggers on phrases like "convert to script," "talk to camera," "video script," "make this a reel," "turn this into a short."
---

# Talk-to-Camera Script Converter

Convert raw voice memo transcripts into platform-optimized, line-by-line scripts for talk-to-camera videos using the pause-and-cut recording technique.

## Required Inputs

1. **Transcript** — The transcribed voice memo (raw text)
2. **Platform** — Target platform (determines length and optimization)
3. **Polish Level** — Optional (default: medium)

## Platform Parameters

| Platform | Default Length | Hashtag Count | Optimization Notes |
|----------|---------------|---------------|-------------------|
| TikTok | 30-60 sec | 3-5 | Fast hooks (<3 sec), raw energy, trending format awareness, pattern interrupts |
| Instagram Reels | 30-90 sec | 5-10 | Visual hook emphasis, slightly more polished, carousel-friendly hooks |
| YouTube Shorts | 30-60 sec | 3-5 | SEO-heavy title/description, can be more informational, keyword-rich |
| YouTube Long-form | 2+ min | 3-5 | Slower build allowed, chapter-friendly structure, deeper exploration |

## Polish Levels

| Level | Description |
|-------|-------------|
| **Low** | Preserves original phrasing, minimal restructuring, "raw thoughts" energy |
| **Medium** | Balanced—tightens structure while keeping natural voice (default) |
| **High** | Tighter, more edited, cleaner delivery—still authentic but polished |

## Workflow

### Step 1: Extract Core Insight
- Identify the single main argument or insight from the transcript
- Note supporting examples and comparisons used
- Flag any natural hooks or quotable moments

### Step 2: Structure for Platform
- **Hook (first 3 seconds):** Question, provocative statement, or pattern interrupt
- **Body (3-5 points):** Supporting arguments with concrete examples
- **Close:** Open loop or reflection prompt (not hard conclusion)

Adjust pacing based on platform:
- TikTok/Reels: Front-load value, fast transitions
- YouTube Shorts: Can be slightly more methodical
- YouTube Long-form: Allow breathing room, deeper tangents okay

### Step 3: Deletion Pass
Before formatting, cut aggressively:
- Remove filler words and phrases
- Eliminate redundant explanations
- Cut hedging language ("I think," "maybe," "sort of")
- Tighten any line over 15 words

### Step 4: Format as Line-by-Line Script
- Each line = one paragraph
- 8-15 words per line maximum
- Each line should be deliverable in one breath
- Natural pause points between lines

### Step 5: Generate Supporting Elements
- 2-3 hook alternatives
- 2-3 CTA suggestions
- SEO/AEO optimized caption
- Platform-appropriate hashtags
- 2-3 follow-up content ideas

## Voice Guide

**CRITICAL:** Before generating any script, read `references/voice-guide.md` to understand the user's voice patterns, cringe list, and authenticity tests. All output must pass the anti-BS filter.

Key voice characteristics:
- Thinks in questions, then answers them
- Uses "right?" as conversational checkpoints
- Builds arguments through concrete comparisons
- Comfortable with open loops and "I don't have the full answer"
- Direct, slightly sarcastic, self-deprecating when appropriate

## Output Format

```
## MAIN SCRIPT
[Platform: X | Length: X sec | Polish: X]

[Line 1 - Hook]

[Line 2]

[Line 3]

[Continue with single-line paragraphs...]

[Final line - Open loop/reflection]

---

## HOOK ALTERNATIVES

1. [Alternative hook option]
2. [Alternative hook option]
3. [Alternative hook option]

---

## CTA SUGGESTIONS

1. [Soft CTA option]
2. [Soft CTA option]
3. [Soft CTA option]

---

## CAPTION (SEO/AEO Optimized)

[Platform-optimized caption with keywords naturally integrated]

---

## HASHTAGS

[Hashtag 1] [Hashtag 2] [Hashtag 3] [etc.]

---

## FOLLOW-UP CONTENT IDEAS

1. [Spin-off idea with brief description]
2. [Spin-off idea with brief description]
3. [Spin-off idea with brief description]
```

## Examples

### Example Input

**Transcript:**
"I've been thinking about aesthetics versus design. Like, aesthetics is just the form, right? But design is form AND function. And I think we overlook the form sometimes. Like, the Cybertruck didn't have to look like that. You can debate whether it's good looking or not, but it catches your eye. That's the point. You can either be the Cybertruck or another F-150 that nobody notices."

**Platform:** TikTok
**Polish Level:** Medium

### Example Output

```
## MAIN SCRIPT
[Platform: TikTok | Length: 45 sec | Polish: Medium]

Aesthetics is not the same as design.

But we keep treating them like they are.

Aesthetics is form.

Design is form AND function.

Here's the thing most brands miss:

The Cybertruck didn't have to look like that.

You can hate it. You can love it.

But you noticed it, right?

That's the point.

You can either be the Cybertruck—

Or another F-150 that blends into traffic.

Which one is your brand choosing?

---

## HOOK ALTERNATIVES

1. "Stop confusing aesthetics with design. They're not the same."
2. "The Cybertruck is ugly. And that's exactly why it works."
3. "Most brands are F-150s. Here's why that's a problem."

---

## CTA SUGGESTIONS

1. "Drop a comment—Cybertruck or F-150?"
2. "Follow for more brand strategy breakdowns"
3. "Which category does your brand fall into? Be honest."

---

## CAPTION (SEO/AEO Optimized)

Aesthetics ≠ design. One is form, the other is form + function. The Cybertruck proves you don't have to be pretty to be memorable—you just have to be impossible to ignore. Most brands play it safe and blend in. The ones that win? They make a choice. Cybertruck or F-150—which one are you building?

---

## HASHTAGS

#brandstrategy #designthinking #marketing #cybertruck #brandidentity

---

## FOLLOW-UP CONTENT IDEAS

1. **"The F-150 trap"** — Deep dive on why "safe" brand choices backfire
2. **"Ugly brands that win"** — Examples of brands that prioritized distinctiveness over beauty
3. **"Form vs function: when to prioritize which"** — Framework for making the tradeoff
```

## Quality Checklist

Before delivering output, verify:

- [ ] Hook lands in first 3 seconds
- [ ] Every line is 8-15 words max
- [ ] No cringe phrases from voice guide
- [ ] Passes all 4 anti-BS filter tests
- [ ] Ends with open loop, not lecture conclusion
- [ ] Hashtag count matches platform
- [ ] Caption includes searchable keywords naturally