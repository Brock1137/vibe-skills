---
name: vibe-code
description: Implement a feature from a spec, feature description, or fresh request — while keeping specs in sync. Use for all implementation work. Handles spec management (find, update, or create minimal spec), writes the code, then self-verifies via a Vibe:check subagent. Trigger on: "vibe:code X", "implement X", "build X", "code up X", "make X work", or any direct implementation request. Takes an argument: spec filename, feature description, or a new feature request with no preexisting spec.
---

# Vibe:Code — Spec-Driven Implementation

Implements features while keeping specs in sync. The argument tells you what to build: a spec filename, a feature description, or a fresh request.

## Resolve Spec Directory

- Read `CLAUDE.md` → look for a spec directory path
- Found → use it
- Not found → ask the user, then write the **Specs folder** line to `CLAUDE.md` before proceeding

## Resolve Validation

- Read `CLAUDE.md` → look for validation commands (test runner, lint, build check, type check, etc.)
- Found → note them for Step 4
- Not found → ask the user: "What validation should I run after implementing? (e.g. `godot --check`, `npm test`, `pytest` — or 'nothing' if none applies)" Then write their answer to `CLAUDE.md` as a **Validation** line before proceeding. Even "nothing" is a valid answer and should be recorded so you don't ask again.

---

## Step 1: Resolve the Target Spec

Find or create the spec for this work:

1. **Exact filename given** → load that spec directly
2. **Description given** → search the spec directory resolved above, scan titles and overviews, pick the best match. Tell the user which spec you matched.
3. **No matching spec found** → create a minimal spec before implementing (see below)
4. **Feature differs from existing spec** → note the difference and update the spec to reflect the new intent before writing any code

### When to create a minimal spec

If no spec exists, create one now. Keep it lean — just enough to record intent and scope:

```markdown
# Feature Name — Design Spec
**Date:** YYYY-MM-DD
**Status:** Draft — created during implementation

## Overview
[What this does]

## Scope
[Files affected]

## Behavior
[Key behaviors — fill in as you implement]
```

Update this file as implementation reveals details. It's a living record, not upfront design.

## Step 2: Implement

Follow the spec. If you discover details during implementation that change the design, update the spec to reflect reality — keep them in sync.

Refer to the project's CLAUDE.md for coding conventions specific to this project.

## Step 3: Run Validation

Run the validation commands resolved above. If validation is "nothing", skip this step.

If validation fails, fix the issues before proceeding. Update the spec if the failures reveal a design misunderstanding.

## Step 4: Self-Verify

After implementation, spawn a subagent to run Vibe:check against the spec you just worked with. Pass the spec file path explicitly.

Subagent prompt:
```
Using the vibe-check skill, check the implementation against this spec: <spec-file-path>.
Be thorough. Report all differences between spec and implementation.
```

Report the subagent's findings to the user. If the check finds real discrepancies, fix them before calling the work done.
