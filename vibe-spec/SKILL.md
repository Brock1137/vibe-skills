---
name: vibe-spec
description: Plan and spec out a new feature before any implementation. Use this skill when the user wants to think through a feature, explore design space, check for existing spec coverage, and produce a written spec file. Always use this before building something non-trivial when the user says things like "spec out X", "plan X", "let's think through X before building", "design doc for X", "update the spec for X", or "I want to add X" in a planning context. If there's even a 10% chance the user wants to plan before coding, invoke this skill.
---

# Vibe:Spec — Spec-Driven Planning

Planning phase only — no implementation. Goal: move from idea to an approved, written spec.

## Step 1: Understand the Feature

Get a clear picture of what the user wants. If the description is vague, ask **one** targeted clarifying question. Don't ask multiple questions at once — one question unblocks the rest.

## Resolve Spec Directory

- Read `CLAUDE.md` → look for a spec directory path
- Found → use it
- Not found → ask the user, then write the **Specs folder** line to `CLAUDE.md` before proceeding

---

## Step 2: Check Existing Specs

Search for specs that may overlap or relate to this feature. Look in the spec directory resolved above.

Read any that seem related and look for:
- **Full coverage** — this feature is already specced; discuss whether to extend or replace
- **Partial coverage** — the feature intersects an existing spec; consider updating rather than creating a new one
- **Refactor opportunity** — multiple related specs that could be consolidated

Report what you found before moving on. If nothing relevant exists, say so briefly and continue.

## Step 3: Brainstorm Approaches

Propose 2–3 distinct design approaches. For each, give:
- A brief description of the approach
- Key trade-offs (complexity, performance, maintainability)
- Your recommendation and why

Ask the user which direction they want to take. Don't proceed until they pick one.

## Step 4: Write or Update the Spec

Create or update the spec file. Use this naming convention, with the spec directory resolved above:
```
<spec-dir>/YYYY-MM-DD-feature-name-design.md
```

Use this structure (match the detail level of existing specs — precise and implementation-close, not hand-wavy):

```markdown
# Feature Name — Design Spec
**Date:** YYYY-MM-DD
**Status:** Draft

## Overview
One paragraph: what this does and why.

## Scope
What files and systems are affected.

## [Behavior sections as needed]
Detailed behavior, state changes, edge cases.
```

If updating an existing spec, preserve the original date and add a note about what changed.

## Step 5: Review and Iterate

After writing, re-read the spec and flag:
- Ambiguities or under-specified behaviors
- Edge cases not addressed
- Decisions that need the user's input before implementation

Ask for clarification. Revise. Repeat until the user confirms the spec is complete.

On confirmation, update `**Status:** Draft` → `**Status:** Approved`.
