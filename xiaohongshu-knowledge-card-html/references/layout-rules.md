# Layout Rules

## Palette

- `--ink: #1a1a2e`
- `--paper: #faf8f3`
- `--accent: #e85d26`
- `--accent2: #2d6a8f`
- `--accent3: #f2c94c`
- `--border: #e0dbd0`

## Typography

- Prefer `Noto Serif SC` for major headings.
- Prefer `Noto Sans SC` for body copy.
- Keep heading rhythm editorial and high contrast.

## Page Structure

- Use `540px x 720px` preview pages to represent `1080px x 1440px`.
- Apply generous outer padding and visible separation between pages.
- Add a `part-tag` at the top of every page.
- Place a `page-footer` at the lower-right corner.
- Keep the overall palette and editorial card language consistent across all pages, but vary the internal module composition by page role.

## Density

- Do not leave large empty blank areas.
- Keep 2-4 compact content modules per page when possible.
- Favor concise lines and clear hierarchy over long paragraphs.

## Visual Modules

- Do not force a screenshot or demo placeholder onto every page.
- Reserve screenshot-ready space on page 2 and page 4 only by default.
- Keep each screenshot-ready area integrated into the layout rather than floating as an isolated empty block.
- When a visual area is genuinely useful, make it content-led: use process diagrams, metric panels, comparison grids, or a clearly requested image slot.
- Prefer fully designed information blocks over large generic empty regions.

## Emphasis

- Use `<code>` for paths, commands, menu names, and short UI steps.
- Use orange for key takeaways and blue for structural guidance.
- Use yellow sparingly for warnings, pitfalls, or important reminders.

## Suggested Page Patterns

1. Overview page: title, summary cards, key takeaway, no screenshot slot.
2. Steps or method page: process timeline plus one screenshot-ready module.
3. Pitfalls or comparison page: warning card, checklist, or two-column comparison, no screenshot slot.
4. Summary or action page: condensed takeaways plus one screenshot-ready module.

## Screenshot Slot Rules

- Use `div.visual-placeholder` only on page 2 and page 4 unless the user explicitly asks for more.
- Size the slot to roughly 25%-35% of the page height so the page still feels content-led.
- Label the slot according to context, for example `操作截图`, `前后对比`, or `效果演示`, instead of always using the same English text.
