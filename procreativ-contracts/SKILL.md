---
name: procreativ-contracts
description: Generate tailored Schedule A (Scope of Work) and Schedule B (Pricing & Payment Terms)  documents for ProCreativ client agreements. Use this skill when Manny needs to create  or draft contract schedules for new clients. Supports three engagement types -  (1) Fixed-scope projects with defined deliverables and milestone payments,  (2) Retainer/subscription engagements with monthly fees and unlimited requests,  (3) Hourly engagements with time and materials pricing. Outputs clean markdown  ready for paste into Google Docs and DocuSign workflow.
---

# ProCreativ Contracts

Generate Schedule A and Schedule B documents for client agreements.

## Workflow Overview

1. **Identify engagement type** → Fixed-scope, Retainer, or Hourly
2. **Gather project details** via intake questions
3. **Generate Schedule A** (Scope of Work)
4. **Generate Schedule B** (Pricing & Payment Terms)
5. **Output markdown** ready for Google Docs

## Engagement Type Selection

Ask: "What type of engagement is this?"

| Type | When to Use |
|------|-------------|
| **Fixed-scope** | Defined deliverables, clear end date, project-based pricing |
| **Retainer** | Ongoing relationship, monthly fee, unlimited requests model |
| **Hourly** | Time & materials, estimated hours, periodic invoicing |

## Intake Framework by Type

### Fixed-Scope Projects

Gather these details (ask conversationally, not as a checklist):

**Project basics:**
- Client name (registered business name)
- Project name
- Project objective (1-2 sentences on the "why")
- Background context (what problem are we solving?)

**Deliverables:**
- What are we delivering? (be specific)
- What's explicitly excluded?

**Timeline:**
- Total duration (weeks)
- Key milestones and what's delivered at each
- Any hard deadlines?

**Client responsibilities:**
- What do they need to provide?
- Who's the primary contact?
- Feedback turnaround expectations?

**Pricing:**
- Total project fee
- Payment structure (50/50, milestones, other)
- Change order hourly rate (default: $175/hr)

### Retainer Engagements

Gather these details:

**Basics:**
- Client name
- Service tier/package name (e.g., "ProCreativ Partnership")

**Included services:**
- What categories of work are included?
- Any specific deliverable types to highlight?
- Monthly strategy consultation hours included?

**Service levels:**
- Turnaround times by request complexity
- Business hours and response times
- How is "unlimited" defined/bounded?

**Exclusions:**
- What's NOT included?

**Pricing:**
- Monthly subscription fee
- Rush request pricing
- Weekend work pricing
- Any add-on services?

### Hourly Engagements

Gather these details:

**Basics:**
- Client name
- Engagement description

**Scope:**
- Types of work covered
- Estimated hours (range)
- What triggers out-of-scope?

**Pricing:**
- Hourly rate
- Deposit/retainer amount
- Invoicing frequency (weekly, bi-weekly, monthly)
- Payment terms (Net 15, Net 30, etc.)

## Document Generation

After gathering details, generate documents in this order:

1. **Schedule A** — See `references/schedule-a-patterns.md`
2. **Schedule B** — See `references/schedule-b-patterns.md`

Output as clean markdown with:
- Proper heading hierarchy (# for main sections, ## for subsections)
- Tables where appropriate (deliverables, timelines, pricing)
- Bold for defined terms on first use
- Placeholder syntax: `_______________` for signature blanks, `[CLIENT NAME]` for variable insertions

## Quality Checklist

Before outputting, verify:

- [ ] All placeholder fields are clearly marked
- [ ] Deliverables are specific and measurable
- [ ] Exclusions are explicit (prevents scope creep disputes)
- [ ] Payment terms match engagement type
- [ ] Termination provisions included
- [ ] Contact information sections present

## Reference Files

- `references/schedule-a-patterns.md` — Section structures by engagement type
- `references/schedule-b-patterns.md` — Payment terms patterns
- `references/boilerplate.md` — Reusable language blocks
- `references/msa-reference.md` — MSA content for context (do not output, reference only)

## Output Format

Output each schedule as a separate markdown code block, clearly labeled:

```
## Schedule A: Scope of Work
[content]
```

```
## Schedule B: Pricing & Payment Terms  
[content]
```

This allows easy copy-paste into Google Docs while preserving structure.