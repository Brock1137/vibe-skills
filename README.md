# Claude Code Skills

A collection of custom skills for [Claude Code](https://claude.ai/code).

## Skills

### vibe-spec
Plan and spec out a new feature before any implementation. Guides you through understanding the feature, checking for existing specs, brainstorming design approaches, and producing an approved written spec file.

**Trigger:** "spec out X", "plan X", "let's think through X before building", "design doc for X"

---

### vibe-code
Implement a feature from a spec, feature description, or fresh request — while keeping specs in sync. Handles finding or creating a spec, writing the code, running validation, and self-verifying via `vibe-check`.

**Trigger:** "implement X", "build X", "code up X", "make X work"

---

### vibe-check
Verify that the codebase implementation matches one or more specs. Non-interactive — reads specs, finds implementation files, compares them, and returns a written report.

**Trigger:** "check the spec", "verify implementation", "does the code match the spec", "check all specs"
**Arguments:** a spec filename, a description to fuzzy-match, or `all` to check every spec

---

### visualize
Create ASCII/Unicode diagrams, wireframes, and visualizations using rich box-drawing characters and expressive Unicode symbols. Use for UI mockups, component trees, data flows, process diagrams, state machines, timelines, and more. Also useful inline in documentation, READMEs, and specs.

**Trigger:** "show me", "sketch", "wireframe", "diagram", "draw", "visualize", "map out", "what does X look like"

---

## Usage

These skills are loaded automatically when you use Claude Code. Invoke them via slash commands or by describing what you want in natural language.

```
/vibe-spec      # Plan a feature
/vibe-code      # Implement a feature
/vibe-check     # Verify implementation against specs
/visualize      # Create a diagram or wireframe
```
