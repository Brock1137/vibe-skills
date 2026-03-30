---
name: vibe-check
description: Verify that the codebase implementation matches one or more specs. Non-interactive — runs a full review and returns a written report. Takes an argument: a spec filename, a description to fuzzy-match, or "all" to check every spec. Always use this when asked to check, verify, or validate implementation against specs. Also called internally by vibe-code after implementation. Trigger on: "vibe:check X", "does the code match the spec", "check the spec", "verify implementation", "are we following the spec for X", "check all specs".
---

# Vibe:Check — Spec vs Implementation Review

Non-interactive. Read specs, find implementation, compare, report. No clarifying questions during the check.

## Resolve Spec Directory

- Read `CLAUDE.md` → look for a spec directory path
- Found → use it
- Not found → ask the user, then write the **Specs folder** line to `CLAUDE.md` before proceeding

---

## Step 1: Resolve Target Spec(s)

- **Exact filename given** → load that file directly
- **Description given** → search the spec directory resolved above, scan titles and overviews, pick the best match. State which spec you matched.
- **"all"** → check every spec file found in the spec directory

## Step 2: For Each Spec

1. Read the spec fully
2. Identify implementation files:
   - Check the spec's **Scope** section first — it usually names the relevant files
   - If not listed, search the codebase based on the feature described (Grep for key identifiers, function names, class names from the spec)
3. Read the implementation files
4. Compare spec to code

What to look for:
- Behaviors described in the spec that aren't implemented
- Behaviors implemented but absent from the spec (spec is stale)
- State/variables the spec defines that differ in code (wrong name, type, initial value, etc.)
- Edge cases the spec calls out explicitly — are they handled?
- Open questions in the spec that were silently resolved (or ignored) in the code

## Step 3: Report

Produce one report block per spec:

```
## Vibe:Check — [Spec Name]
**Spec:** path/to/spec.md
**Files reviewed:** list of implementation files

### Matches
- [What aligns between spec and code]

### Differences
- [Spec says X, code does Y] → recommend: update code / update spec
- ...

### Open Questions
- [Items in the spec marked as open or unresolved]

### Summary
One paragraph overall assessment: is the implementation faithful to the spec?
```

When checking multiple specs ("all"), produce one block per spec, then close with:

```
## Overall Health
[Brief summary across all specs — what's clean, what needs attention]
```

Deliver the full report without stopping to ask questions. If something is ambiguous, note it in the report under Open Questions rather than blocking.
