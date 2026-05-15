---
name: xiaohongshu-knowledge-card-html
description: Generate polished Xiaohongshu-style 3:4 HTML knowledge-card pages from Markdown content or .md files. Use when the user wants to turn notes, tutorials, guides, or structured Markdown into screenshot-ready HTML in an orange-blue editorial style, especially when they mention xiaohongshu, knowledge cards, long-form social post layouts, 3:4 pages, or Markdown-to-HTML conversion, or ask to process an md file directly.
---

# Generate Xiaohongshu Knowledge Cards

Read the user's Markdown content or the provided `.md` file first. Preserve the factual meaning, but rewrite headings and group points so the result reads like concise social knowledge cards rather than a document dump.

Use the fixed visual system in [references/layout-rules.md](references/layout-rules.md) and start from [assets/xiaohongshu-template.html](assets/xiaohongshu-template.html). Keep the palette, spacing, and card language consistent unless the user explicitly asks for a variant.

## Workflow

1. Extract the document structure.
2. Split the content into multiple `section.page` blocks at a 1080x1440 visual ratio, implemented at `540x720` for preview.
3. Remove any standalone cover page. Start directly from `Part 01`.
4. Keep every page content-dense. Avoid pages that feel empty or poster-like.
5. Reserve a `div.visual-placeholder` area on each page, usually 30%-40% of the page height, for later screenshot replacement or demo imagery.
6. Convert paths, commands, menus, and short steps to `<code>` tags where useful.
7. Present key conclusions, warnings, or takeaways in emphasized blocks using the accent colors.
8. Return one complete HTML document with embedded CSS and all page markup.

## Content Rules

- Prefer short Chinese headings with one highlighted keyword inside `<span>` when it improves emphasis.
- Merge low-value filler text. Expand only when needed to avoid sparse layout.
- Use `content-card` blocks for actionable points, comparisons, rules, or steps.
- Use ordered steps when the source content is procedural.
- Keep each page focused on one main idea plus supporting details.
- If the source Markdown is very long, paginate naturally rather than shrinking text aggressively.

## Output Rules

- Output valid, self-contained HTML.
- Keep the existing color tokens and typography priorities from the template.
- Use semantic structure that is easy to edit after generation.
- Do not include explanations before or after the HTML unless the user asks for commentary.

## Optional Adjustments

- If the Markdown has clear section headings, map one major heading to one page group.
- If the Markdown is a short note, expand it into 2-4 pages by separating overview, steps, pitfalls, and summary.
- If the user provides screenshots or asks for image slots, keep the placeholder labels explicit so they can replace them later.
