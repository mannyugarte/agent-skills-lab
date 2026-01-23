# Synthesize My AI Preferences

A Claude Code skill that helps you maintain consistent, calibrated personalization instructions across multiple AI tools from a single source of truth.

## What It Does

Instead of manually writing and maintaining separate instructions for each AI tool you use, this skill lets you:

1. **Create a Master Profile** - Define your identity, preferences, and context rules once
2. **Generate tool-specific instructions** - Automatically adapt your profile for each platform's constraints and strengths
3. **Keep everything in sync** - Update one place, regenerate for all tools

## Supported Tools

- Claude
- ChatGPT
- Perplexity
- Gemini
- Grok
- Cursor
- Dia Browser
- Breeze by HubSpot
- (and more can be added)

## Installation

1. Download `synthesize-my-ai-preferences.skill`
2. In Claude Code, run:
   ```
   /install-skill /path/to/synthesize-my-ai-preferences.skill
   ```

## Usage

After installation, use the skill by running:

```
/synthesize-my-ai-preferences
```

### Workflows

| Command | What it does |
|---------|--------------|
| Initial setup | Build your Master Profile and generate instructions for all your tools |
| Update | Change something in your profile and regenerate affected tools |
| Audit | Check if your current instructions have drifted from your Master Profile |
| Add new tool | Set up personalization for a tool you just started using |

## Example

**Master Profile excerpt:**
- Name: Jane
- Role: Product Manager
- Tone: Direct, no fluff
- Avoid: Jargon, hedging

**Generated for ChatGPT (1,500 char limit):**
> I'm Jane, a Product Manager. Be direct and concise. Skip jargon and hedging. Match depth to question complexity.

**Generated for Claude (longer format):**
> I'm Jane, a Product Manager at [Company]. I prefer direct communication without unnecessary hedging or corporate jargon. Challenge my assumptions when you see gaps in my reasoning...

## License

MIT
