---
name: synthesize-my-ai-preferences
description: Maintain consistent, calibrated personalization instructions across multiple AI tools (Claude, ChatGPT, Perplexity, Gemini, Grok, Cursor, Dia Browser, Breeze by HubSpot, etc.) from a single source of truth. Use when user wants to (1) set up personalization for a new AI tool, (2) update instructions after role/preference changes, (3) audit existing instructions for drift across tools, (4) add a new AI tool to their workflow, or (5) do periodic maintenance/refresh of their AI personalization.
---

# Synthesize My AI Preferences

Translate a single Master Profile into tool-specific instructions that respect each platform's constraints and strengths. Instructions are *adapted*, not copy-pasted.

## Core Concepts

### Master Profile (Source of Truth)
Stored within this skill containing:
- **Identity**: Name, role(s), business context, industries
- **Preferences**: Tone, formatting, certainty signaling, depth, what to avoid
- **Context Rules**: When professional context applies, special handling by content type

### Tool Profiles
Each tool has: primary use case, character limit, formatting support, platform quirks, strengths to leverage. See `references/tool-registry.md` for current registry.

### Translation Logic
- Prioritize preferences relevant to tool's primary use case
- Respect character limits (leave ~5% buffer)
- Use formatting the platform supports
- Address known platform quirks

---

## Workflows

All workflows are **conversational**. Prompt step-by-step, wait for responses, confirm before proceeding.

### A. Initial Setup

**Step 0: Import or Create**

Start every new setup with this question:

"Let's start by building your Master Profile—the source of truth for all your AI tools.

**Option 1: Paste existing instructions**
If you already have personal preferences set up somewhere, copy and paste your best/most complete instructions from whichever AI tool you use most (Claude, ChatGPT, Perplexity, etc.). I'll use that as our starting point and extract the key elements.

**Option 2: Generate from memory**
If you use an AI tool with memory (ChatGPT, Claude, etc.) but haven't written formal instructions yet, run this prompt in that tool to generate a draft based on what it already knows about you:

---
*'Based on everything you know about me from our conversation history, help me write personal preferences I can use across AI tools. Structure it as: (1) Identity—my name, role, business context, industries I work in; (2) Preferences—how I want responses to sound, formatting, depth, what to avoid; (3) Context rules—when to apply my professional context vs. answer generally. Keep it under 1,500 characters total.'*

---

Then paste the output here and I'll refine it into your Master Profile.

**Option 3: Start fresh**
No existing preferences and no AI memory to pull from? No problem—I'll walk you through creating your Master Profile step by step.

Which option works best for you: (1) paste existing, (2) generate from memory, or (3) start fresh?"

**If user chooses Option 1 or 2 (pastes content):**
1. Parse the pasted content to extract: identity, preferences, context rules
2. Present extracted Master Profile: "Here's what I pulled from your instructions: [structured summary]"
3. Ask: "Does this capture everything? Anything to add or change?"
4. Proceed to Step 5 (Identify Active Tools)

**If user chooses Option 3 (start fresh):**
Continue to Step 1 below.

---

**Step 1: Identity** *(skip if imported above)*
Ask one at a time:
1. "What's your name?"
2. "What's your role or title? If you wear multiple hats, list the functions you're responsible for."
3. "What's your business or company context?"
4. "What industries or domains do you primarily operate in?"

Confirm: Show identity summary, ask "Does this look right? (Yes / Edit)"

**Step 2: Preferences** *(skip if imported above)*
Ask one at a time:
1. "How should responses sound? (e.g., direct, warm, formal, casual, blunt)"
2. "Default format preference? (e.g., bullets, prose, tables, minimal formatting)"
3. "Do you want AI to state certainty/confidence levels? (Yes / No / Only when uncertain)"
4. "Default depth? (e.g., concise unless asked, comprehensive, match question complexity)"
5. "What should responses avoid? (e.g., fluff, jargon, hedging, emojis)"

Confirm: Show preferences summary, ask "Does this look right? (Yes / Edit)"

**Step 3: Context Rules** *(skip if imported above)*
Ask one at a time:
1. "Topics where professional context should always apply?"
2. "Topics where it should NOT apply unless explicitly relevant?"
3. "Content types needing special handling? (e.g., sales content = direct, technical = beginner-friendly)"

Confirm: Show context rules summary, ask "Does this look right? (Yes / Edit)"

**Step 4: Store Master Profile**
Store in this format:
```
## Master Profile
Last updated: [date]

### Identity
- Name: [X]
- Role(s): [X]
- Business context: [X]
- Industries: [X]

### Preferences
- Tone: [X]
- Format default: [X]
- Certainty signaling: [X]
- Depth default: [X]
- Avoid: [X]

### Context Rules
- Apply professional context when: [X]
- Don't apply when: [X]
- Special handling: [X]
```

**Step 5: Identify Active Tools**
Ask: "Which AI tools do you currently use? (I have templates for: Claude, ChatGPT, Perplexity, Gemini, Grok, Cursor, Dia Browser, Breeze by HubSpot—I can add others.)"

For each tool:
- "For [Tool]: What's your primary use case?"
- "Any frustrations or behaviors to correct?"

**Step 6: Generate Instructions**
For each active tool:
1. Pull relevant Master Profile elements
2. Prioritize based on primary use case
3. Consult `references/tool-registry.md` for limits/quirks
4. Trim to character limit (~5% buffer)
5. Output in platform-appropriate format

Output format:
```
**[Tool Name] Instructions**
Character count: [X] / [limit] ([X] remaining)

[Instructions ready to paste]
```

**Step 7: Generate Test Prompts**
For each tool:
```
**Test Prompt for [Tool Name]:**
"[Prompt text]"

**What to look for:**
- [Criterion 1]
- [Criterion 2]

**Red flags:**
- [Flag 1]
- [Flag 2]
```

---

### B. Update Workflow

Trigger: User says "update my instructions", "I changed my title", "something's not working"

1. **Identify change**: "What changed?"
2. **Clarify scope** (if needed): "Does this affect identity, preferences, context rules, or just one tool?"
3. **Update Master Profile**: Show current value → confirm new value → store
4. **Identify affected tools**: "This change affects [X]. I'll regenerate for: [tools]. Proceed?"
5. **Regenerate and output**: Include character counts
6. **Offer test prompt**: "Want a new test prompt to verify?"

---

### C. Audit Workflow

Trigger: User says "audit my instructions", "sync check", "instructions feel off"

1. **Request current instructions**: "Paste your current instructions for each tool, one at a time. Which first?"
2. **Compare against Master Profile** for each tool:
   - Identity match?
   - Preferences aligned?
   - Context rules present?
   - Character limit respected?
3. **Report findings**:
```
**Audit Results**

**Claude:**
- ✅ Identity matches
- ⚠️ Missing certainty signaling
- ✅ Character limit OK

**ChatGPT:**
- ❌ Role outdated
- ✅ Preferences aligned

**Recommended updates:**
1. [Specific fix]
2. [Specific fix]
```
4. **Confirm and regenerate**: "Want me to regenerate flagged tools? (Yes / Select specific / Skip)"
5. **Output and test**

---

### D. Quick Retrieval

Trigger: User asks "What are my current [tool] instructions?"

Output stored instructions with character count and last updated date.

---

### E. Add New Tool

Trigger: User says "I started using [tool]—can you set it up?"

1. Ask primary use case and frustrations
2. Check `references/tool-registry.md` for existing profile; if missing, ask user to help document limits/quirks
3. Add to registry
4. Generate instructions from Master Profile
5. Output with test prompt

---

## Translation Guidelines Summary

| Tool | Prioritize | Watch For |
|------|-----------|-----------|
| Claude | Tone, depth, challenge/pushback, content-type rules | Redundancy with Projects; memory runs parallel |
| ChatGPT | Tone, formatting, avoid list, depth | 1,500 char limit is tight; memory conflicts |
| Perplexity | Lead with answer, source quality, certainty, concise | Over-indexes on profile context |
| Cursor | Code style, explanation depth, framework prefs | IDE context; focus on communication style |
| Breeze | CRM tone, brevity | HubSpot data context; limited instruction impact |
| Grok | TBD | Defaults to casual tone—may need override |
| Gemini | TBD | TBD |
| Dia | TBD | TBD |

Full details in `references/tool-registry.md`.

---

## Stored Data

This skill stores:
1. **Master Profile** — Source of truth
2. **Tool Registry** — Active tools with use cases, limits, quirks
3. **Generated Instructions** — Latest version per tool with character counts
4. **Last Updated Date** — Per Master Profile and per tool