# Tool Registry

Reference for AI tool constraints, quirks, and translation guidelines.

## Registry Table

| Tool | Primary Use | Char Limit | Format | Key Quirk |
|------|-------------|------------|--------|-----------|
| Claude | Co-creation, strategy, writing, complex tasks | ~4,000 | Markdown | Projects allow separate instructions; memory runs parallel |
| ChatGPT | Quick tasks, writing, general assistance | 1,500 | Plain text | Memory feature can conflict with instructions |
| Perplexity | Research, fact-checking, citations | ~1,387 | Plain text | Auto-applies profile context; can over-index |
| Gemini | TBD | TBD | TBD | TBD |
| Grok | TBD | TBD | TBD | Defaults to casual/irreverent tone |
| Cursor | Code assistance, development | TBD | TBD | IDE-integrated; context from codebase |
| Dia Browser | TBD | TBD | TBD | TBD |
| Breeze (HubSpot) | CRM tasks, sales/marketing | TBD | TBD | CRM-integrated; context from HubSpot data |

*TBD entries: Verify and update when user calibrates each tool.*

---

## Detailed Translation Guidelines

### Claude (User Preferences)

**Character limit:** ~4,000 characters

**Prioritize:**
- Tone and communication style
- Depth and formatting preferences
- Strategic thinking style
- Challenge/pushback behavior
- Content-type-specific rules (sales, technical, creative)

**Can include:** Most detail—longest limit allows comprehensive instructions

**Format:** Markdown supported; can handle nuanced, multi-layered instructions

**Watch for:**
- Redundancy with Project Instructions if using Claude Projects
- Memory system holds parallel context—instructions should complement, not duplicate
- User Preferences vs. Project Instructions serve different scopes

---

### ChatGPT

**Character limit:** 1,500 characters (strict)

**Prioritize:**
- Tone
- Formatting defaults
- What to avoid
- Depth preference

**Must trim:** Aggressive editing required—every word counts

**Format:** Plain text only (no markdown rendering in instructions field)

**Leverage:** Memory feature can hold identity context, so instructions can focus on *behavior* rather than *who you are*

**Watch for:**
- Memory conflicts—if memory stores outdated info, it may override instructions
- Prompt user to audit ChatGPT memory separately when updating instructions
- Memory and instructions can contradict; instructions usually win but not always

---

### Perplexity

**Character limit:** ~1,387 characters

**Prioritize:**
- Answer structure (lead with answer, skip preamble)
- Source quality preferences (credible, recent, primary over aggregators)
- Certainty signaling (flag when sources conflict)
- Concise default with depth on demand

**Must include:**
- Context-application rules: when to apply professional lens, when not to
- Explicit "don't assume every query relates to my work" guidance

**Format:** Plain text only

**Leverage:** Research strength—emphasize source credibility, recency, citation preferences

**Watch for:**
- Over-indexes on profile context for unrelated queries
- May add unwanted follow-up questions like "Is this related to your work?"
- Needs explicit rules to answer general questions broadly

---

### Gemini

**Character limit:** TBD (verify upon setup)

**Prioritize:** TBD based on user's primary use case

**Format:** TBD

**Watch for:** TBD

**Notes:** User should test and document after initial setup

---

### Grok

**Character limit:** TBD (verify upon setup)

**Prioritize:** TBD based on user's primary use case

**Format:** TBD

**Watch for:**
- Defaults to casual, irreverent tone—may need explicit tone override
- Personality is baked in more than other tools

**Notes:** User should test and document after initial setup

---

### Cursor

**Character limit:** TBD (verify upon setup)

**Prioritize:**
- Code style preferences
- Explanation depth for technical content
- Framework/language preferences
- Comment style

**Format:** TBD

**Context note:** IDE-integrated—pulls context from codebase automatically

**Watch for:**
- Instructions may interact with project-level settings
- Keep personalization focused on *how* to communicate, not *what* codebase context to use
- Codebase context is automatic; instructions should guide explanation style

**Notes:** Focus on communication preferences, not code context

---

### Dia Browser

**Character limit:** TBD (verify upon setup)

**Prioritize:** TBD based on user's primary use case

**Format:** TBD

**Watch for:** TBD

**Notes:** User should test and document after initial setup

---

### Breeze (HubSpot)

**Character limit:** TBD (verify upon setup)

**Prioritize:**
- CRM task communication style
- Sales/marketing content tone
- Brevity (CRM context is often quick-action)

**Format:** TBD

**Context note:** Pulls context from HubSpot data automatically

**Watch for:**
- Instructions may have limited impact on deeply CRM-integrated responses
- Focus on tone and output format rather than identity context
- HubSpot data provides most of the relevant context

**Notes:** May be more limited in customization than general-purpose AI tools

---

## Adding New Tools

When adding a tool not in this registry:

1. **Research or test** the tool's personalization settings
2. **Document:**
   - Character limit (test by adding characters until rejected)
   - Format support (markdown? plain text? headers?)
   - Primary use case for this user
   - Any quirks or default behaviors to override
3. **Add to registry table** above
4. **Create detailed section** following the pattern above
5. **Generate instructions** from Master Profile
6. **Create test prompt** and verify behavior

---

## Maintenance

- **Verify limits** when platforms update (they change)
- **Update quirks** when tool behavior changes
- **Add new tools** as user adopts them
- **Remove deprecated tools** to keep registry clean