---
name: visualize
description: >
  Create ASCII/Unicode diagrams, wireframes, and visualizations using rich box-drawing characters
  and expressive Unicode symbols. Use this skill whenever a visual representation would communicate
  something more clearly than text alone — UI mockups, page wireframes, component trees, data flows,
  process diagrams, file hierarchies, timelines, state machines, network topology, tables, side-by-side
  comparisons, or any spatial relationship. If there's even a 1% chance a diagram would help the user
  understand something faster, use this skill. Trigger on: "show me", "sketch", "wireframe", "diagram",
  "layout", "draw", "visualize", "map out", "what does X look like", "how does X flow", or any request
  where structure and space matter more than prose. Also use when writing or updating any documentation,
  markdown files, code plans, task files, READMEs, or specs — diagrams embedded in docs are almost always
  clearer than prose descriptions of structure or flow.
---

# Visualize

Use rich Unicode box-drawing characters and symbols to create expressive, immediately readable diagrams.
A great diagram communicates structure at a glance — lean into that.

## When to Reach for a Diagram

Default to diagrams whenever you're explaining:
- **Layout or space** — page wireframes, component positions, grid structures
- **Flow** — user journeys, data pipelines, request/response cycles, decision trees
- **Hierarchy** — file trees, component trees, org charts, inheritance
- **Sequence** — step-by-step processes, timelines, state transitions
- **Comparison** — options side by side, before/after, trade-offs
- **Relationships** — dependencies, connections, network topology

If a diagram would replace a paragraph, draw the diagram.

**Documentation is a first-class use case.** Whenever writing or updating markdown files — plans,
READMEs, task files, specs, code docs — reach for diagrams to illustrate structure, flow, or
relationships. A well-placed diagram in a plan file makes it far easier to review and reason about
than the same content in prose. Embed them inline; they render as monospace in any text editor.

---

## Unicode Character Palette

### Box Drawing
```
Single:    ─ │ ┌ ┐ └ ┘ ├ ┤ ┬ ┴ ┼
Double:    ═ ║ ╔ ╗ ╚ ╝ ╠ ╣ ╦ ╩ ╬
Mixed:     ╒ ╓ ╕ ╖ ╘ ╙ ╛ ╜ ╞ ╟ ╡ ╢ ╤ ╥ ╧ ╨ ╪ ╫
Rounded:   ╭ ╮ ╯ ╰
Bold:      ┏ ┓ ┗ ┛ ┣ ┫ ┳ ┻ ╋ ━ ┃
Dashed:    ╌ ╍ ┄ ┅ ┆ ┇ ┈ ┉ ┊ ┋
```

### Arrows & Connectors
```
Thin:      → ← ↑ ↓ ↔ ↕ ↗ ↘ ↙ ↖
Double:    ⇒ ⇐ ⇑ ⇓ ⇔ ⇕
Bold:      ➜ ➡ ⬅ ⬆ ⬇
Triangle:  ▶ ◀ ▲ ▼ ▸ ▹ ◂ ◃
```

### Fills & Shading
```
Light → Dark:   ░ ▒ ▓ █
Blocks:         ▀ ▄ ▌ ▐ ▪ ▫
```

### Markers & Symbols
```
Status:    ✓ ✗ ✦ ● ○ ◉ ◎ ◆ ◇ ★ ☆
Flow:      ❯ ❮ « » ‹ › • · …
```

### Separators
```
━━━━━━━━━━   ─────────   ═════════   ╌╌╌╌╌╌╌╌╌   ┄┄┄┄┄┄┄┄┄
```

---

## Diagram Patterns

### Page Wireframe
```
╔══════════════════════════════════════════════════╗
║  ░░ LOGO ░░       Nav Item    Nav Item    Nav ▾  ║
╠══════════════════════════════════════════════════╣
║                                                  ║
║   ╔══════════════════════════════════════════╗   ║
║   ║                                          ║   ║
║   ║            HERO HEADLINE                 ║   ║
║   ║        Subtext line goes here…           ║   ║
║   ║                                          ║   ║
║   ║         [ Primary CTA Button ]           ║   ║
║   ╚══════════════════════════════════════════╝   ║
║                                                  ║
║   ┌──────────┐  ┌──────────┐  ┌──────────┐      ║
║   │  Card 1  │  │  Card 2  │  │  Card 3  │      ║
║   │  ░░░░░░  │  │  ░░░░░░  │  │  ░░░░░░  │      ║
║   └──────────┘  └──────────┘  └──────────┘      ║
╚══════════════════════════════════════════════════╝
```

### Flow / Process Diagram
```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│    Start    │ ──▶ │   Process   │ ──▶ │     End     │
└─────────────┘     └──────┬──────┘     └─────────────┘
                           │
                     ┌─────▼──────┐
                     │  Decision  │
                     └──┬──────┬──┘
                    Yes │      │ No
                 ┌──────▼──┐  ┌▼────────┐
                 │ Branch A │  │ Branch B│
                 └──────────┘  └─────────┘
```

### Component / File Tree
```
src/
├── components/
│   ├── Header.astro
│   ├── Footer.astro
│   └── ui/
│       ├── Button.astro
│       └── Card.astro
├── layouts/
│   └── BaseLayout.astro
└── pages/
    ├── index.astro
    └── about.astro
```

### Side-by-Side Comparison
```
┌────────────────────────┐  ┌────────────────────────┐
│       Option A         │  │       Option B         │
├────────────────────────┤  ├────────────────────────┤
│  ✓ Fast to implement   │  │  ✓ More flexible       │
│  ✓ Well understood     │  │  ✓ Scales better       │
│  ✗ Hard to extend      │  │  ✗ More complex        │
│  ✗ Couples components  │  │  ✗ Slower to ship      │
└────────────────────────┘  └────────────────────────┘
```

### Timeline
```
────────┬──────────────────┬──────────────────┬────────▶
        │                  │                  │
     Phase 1            Phase 2            Phase 3
    Jan – Mar           Apr – Jun          Jul – Sep
  ● Kickoff           ● Build core       ● Launch
  ● Design            ● Review           ● Monitor
```

### State Machine
```
            ┌─────────────────────────────┐
            │           submit            │
  ┌─────────▼──────┐             ┌────────┴───────┐
  │    PENDING     │ ──approve─▶ │   APPROVED     │
  └────────────────┘             └────────┬───────┘
            │                             │ publish
         reject                           ▼
            │                    ┌────────────────┐
            ▼                    │    PUBLISHED   │
  ┌─────────────────┐            └────────────────┘
  │    REJECTED     │
  └─────────────────┘
```

### Data / Network Relationship
```
  ┌──────────┐        ┌──────────┐
  │  Client  │ ──────▶│   API    │
  └──────────┘        └────┬─────┘
                           │
              ┌────────────┼────────────┐
              ▼            ▼            ▼
        ┌──────────┐ ┌──────────┐ ┌──────────┐
        │   Auth   │ │    DB    │ │  Cache   │
        └──────────┘ └──────────┘ └──────────┘
```

---

## Principles

**Visual weight = semantic weight.**
Use double borders `╔═╗` for primary containers, single `┌─┐` for secondary, dashed `╌` for
optional/placeholder areas. What looks important should *be* important.

**Annotate inside the diagram, not around it.**
Labels, arrow descriptions, and legends belong in the drawing. A diagram that needs a paragraph
of explanation has failed its purpose.

**Align precisely.**
Ragged box edges undermine the sense of structure. Count characters, use consistent padding,
and prefer symmetric layouts. In ambiguous cases, pad to the wider side.

**Use shading intentionally.**
`░░` fill = placeholder / low-fidelity. `▓▓` or `███` = active / selected / emphasized. Avoid
shading as decoration — it should carry meaning.

**Break complexity into multiple diagrams.**
If a single diagram exceeds ~40 lines or requires significant explanation, split it. Two focused
diagrams are clearer than one dense one.

**Prefer diagrams over tables for relationships.**
Tables suit structured data with clear columns. Diagrams suit anything with connections, flow,
or spatial meaning. When in doubt, diagram.
