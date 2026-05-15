---
name: xiaohongshu-knowledge-card-html
description: Generate polished Xiaohongshu-style 3:4 HTML knowledge-card pages from Markdown content or .md files. Use when the user wants to turn notes, tutorials, guides, or structured Markdown into screenshot-ready HTML knowledge-promo or knowledge-presentation pages in an orange-blue editorial style, especially when they mention xiaohongshu, knowledge cards, long-form social post layouts, 3:4 pages, Markdown-to-HTML conversion, or ask to process an md file directly.
---

# Generate Xiaohongshu Knowledge Cards

Read the user's Markdown content or the provided `.md` file first. Preserve the factual meaning, but rewrite headings and group points so the result reads like concise knowledge-promo pages rather than a document dump.

Use the fixed visual system in [references/layout-rules.md](references/layout-rules.md) and start from [assets/xiaohongshu-template.html](assets/xiaohongshu-template.html). Keep the palette, spacing, and card language consistent unless the user explicitly asks for a variant.

## Workflow

1. Extract the document structure.
2. Rewrite the source into a sequence of distinct page roles instead of repeating one generic card layout.
3. Split the content into multiple `section.page` blocks at a 1080x1440 visual ratio, implemented at `540x720` for preview.
4. Remove any standalone cover page. Start directly from `Part 01`.
5. Keep every page content-dense. Avoid pages that feel empty or poster-like.
6. Use different content-led structures across pages: summary cards, step timelines, comparison grids, warning lists, checklists, metric chips, or action summaries.
7. Make every page fully finished and directly screenshot-ready. Do not leave empty image zones, screenshot slots, or generic placeholders unless the user explicitly asks for them.
8. Convert paths, commands, menus, and short steps to `<code>` tags where useful.
9. Present key conclusions, warnings, or takeaways in emphasized blocks using the accent colors.
10. Return one complete HTML document with embedded CSS and all page markup.

## Page Planning

- Plan page roles before writing HTML. Avoid generating four copies of the same structure with different text.
- Prefer a sequence like: overview -> process / method -> pitfalls / comparison -> summary / action.
- If the source content is procedural, make page 2 the strongest process page with timelines, steps, or structured checklists.
- If the source content includes results, demos, or before-after material, translate them into comparison cards, result summaries, or takeaway blocks instead of empty reserved areas.
- If there are fewer than 4 pages, keep the role progression compact without adding filler sections.
- If there are more than 4 pages, keep varying the page roles instead of cycling one repeated layout.

## Content Rules

- Prefer short Chinese headings with one highlighted keyword inside `<span>` when it improves emphasis.
- Merge low-value filler text. Expand only when needed to avoid sparse layout.
- Use `content-card` blocks for actionable points, comparisons, rules, or steps.
- Vary page structure with the modules defined in the template instead of reusing one module stack unchanged.
- Use ordered steps when the source content is procedural.
- Keep each page focused on one main idea plus supporting details.
- If the source Markdown is very long, paginate naturally rather than shrinking text aggressively.
- Replace any urge to "leave space for later" with a real information module that can stand on its own in the final screenshot.

## Output Rules

- Output valid, self-contained HTML.
- Keep the existing color tokens and typography priorities from the template.
- Use semantic structure that is easy to edit after generation.
- Preserve the original orange-blue editorial design language while still varying the page compositions.
- By default, write the generated HTML file into the current project `generated/` directory. Create that directory first if it does not exist.
- Base the output filename on the source Markdown filename when one is available, and save it as an `.html` file.
- Do not include explanations before or after the HTML unless the user asks for commentary.

## Optional Adjustments

- If the Markdown has clear section headings, map one major heading to one page group.
- If the Markdown is a short note, expand it into 2-4 pages by separating overview, steps, pitfalls, and summary.
- If the user explicitly asks to include screenshots or image areas, integrate them as intentional content modules rather than generic placeholders.
