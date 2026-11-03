---
name: context-aware-ui
description: Design and improve readable, distinctive, resilient UI. Use for visual hierarchy, avoiding generic AI-looking designs, responsive layouts, Japanese/CJK text wrapping, CSS clipping, overflow, and alignment bugs (日本語の折り返し・ずれ・はみ出し・見やすいUI). Not for backend-only work.
---

# Context-aware UI

Create interfaces that people can **read, understand, and use naturally**. Keep the user's scope, brand, architecture, and content language. This Skill is platform-agnostic; apply CSS guidance only to CSS-based interfaces.

## Design intentionally

1. Understand the main task, audience, content, usage frequency, input method, and risks. For a small fix, avoid unrelated redesigns.
2. Build clear hierarchy through grouping, alignment, typography, spacing, contrast, and a deliberate focal point. Give the interface an appropriate tone and distinct character; do not confuse "minimal" with "bland."
3. Avoid default AI-looking decoration: arbitrary blue-purple gradients, glow, glass effects, oversized hero sections, repetitive cards, excessive whitespace, and faint text. **These are not bans**; use any of them when they serve the product.
4. Keep interactions and content truthful: no dead controls, fake metrics presented as real, unclear feedback, or unprotected destructive actions.

## Design for changing content

- Test realistic **Japanese/CJK and mixed-language text**, long labels, URLs, filenames, changing data, empty/loading/error states, and narrow or enlarged displays.
- Decide **per component** whether to wrap, reflow, scroll within the region, or truncate. Natural wrapping is fine; clipping, overlap, and lost information are not.
- When something breaks, **fix the layout constraint, not the symptom**. Inspect parent/child widths, minimum sizes, fixed heights, positioning, and text wrapping. Do not hide page-wide overflow as a quick fix.

### For CSS layouts

- Prefer content-aware Flex/Grid flow over unnecessary fixed heights, absolute positioning, or blanket `white-space: nowrap`.
- For Flex/Grid items that cannot shrink, consider **targeted** `min-width: 0` / `min-inline-size: 0`; for Grid tracks, `minmax(0, 1fr)`. Do not apply them universally.
- Let Japanese wrap naturally. Use `overflow-wrap: anywhere` when needed for unbreakable URLs or identifiers; avoid indiscriminate `word-break: break-all`.
- Reserve ellipsis, clipping, and horizontal scrolling for components where they are intentional and important information remains available. Keep table/code scrolling inside that region, not across the page.

Use equivalent layout and text-sizing mechanisms for desktop, mobile, games, VR, or other platforms. Never force Web-specific rules onto them.

## Check and report

- **Appearance:** hierarchy, legibility, appropriate density/tone, visual identity, and applicable contrast/accessibility requirements.
- **Robustness:** long Japanese text, mixed scripts, different widths, text enlargement, and changing states without clipping, overlap, or unintended page overflow.
- **Behavior:** working controls, input/focus, feedback, correct status/metrics, recovery, and safe irreversible actions.
- Use tools already available in the project; do **not** require Python, Playwright, or new dependencies. State what was actually checked and what remains unverified.

**Use the user's requested language for UI copy and replies.** English instructions do not mean English UI text. Keep fixes proportional and report the key change and verification briefly.
