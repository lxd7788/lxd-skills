---
name: football-match-comic
description: Turn football match reports, live blogs, scorelines, and user-provided match notes into fact-checked manga comic scripts, storyboards, and image prompts. Use for World Cup serial documentary comics, Champions League and domestic match recaps, derby or knockout drama, penalty shootouts, pre-match team departures, tournament chapters, non-uniform black-and-white Japanese football manga pages, key-moment extraction, captions, source-backed story outlines, and social-media slide comics.
---

# Football Match Comic

Create fact-checked football manga scripts from real football events. Support both single-match recaps and tournament-scale documentary comic series.

## Reference Router

Load only the reference needed for the task:

- Use `references/world-cup-comic-production-rules-v1.md` for tournament serials, World Cup documentary comics, social-media slide comics, 3:4 vertical pages, black-and-white Japanese manga style, visual bible rules, episode structure, and identity-text rules.
- Also use `references/world-cup-comic-production-rules-v1.md` for any single-match task that targets the social-media slide-comic style, staged fact/material research, identity anchors, or black-and-white non-uniform manga pages.
- Use `references/panel-template.md` when a reusable output skeleton is helpful for match cards, key nodes, page plans, manga page layouts, and prompt skeletons.

Keep `SKILL.md` as the execution entry point; keep detailed production rules in references.

## Modes

### Single Match Recap

Use for one completed or live match. Produce a compact match card, verified timeline, key beats, page plan, script, and prompts.

### Tournament Serial Event

Use when the user provides a tournament event point, such as "World Cup teams begin departing," "group stage upsets," "a host city prepares," "a star exits," or "final penalty shootout." Treat the event as one episode in a larger documentary comic. Follow `references/world-cup-comic-production-rules-v1.md`.

## Core Workflow

Default to staged execution unless the user explicitly asks for a fast one-pass output. Do not jump from fact research directly to storyboard and prompts when the user has not opted out of the supplement checkpoint.

1. Identify the mode: single match recap or tournament serial event.
2. Use a dual-source research strategy: official sources establish facts; broader internet sources surface visual, emotional, and public-discussion material. Do not let non-authoritative sources override official facts.
3. Verify real-world facts before scripting. Browse current sources for recent, live, just-finished, or high-stakes events. Prefer official competition pages, federation/club reports, reputable live blogs, stat providers, press conferences, and verified public posts for facts.
4. Stop after the fact package and ask whether the user has supplemental keywords, angles, screenshots, clips, player moments, fan reactions, or media hooks for a second search. Wait for the user's answer before building the material pool, unless the user explicitly requested a fast one-pass result.
5. Search broader sources for comic material when useful, including any user-supplied keywords: live photos, broadcasts, highlights, interviews, tactical analysis, media headlines, fan reactions, team social posts, and public discussion. Use these as material leads, not final fact authority.
6. Separate confirmed facts from interpretation, public reaction, and manga expression. Mark uncertain details as assumptions or omit them.
7. Build a material pool, then select only elements that strengthen clarity, rhythm, or emotion. Do not add stadium, media, fan, tactical, or symbolic elements merely to make a page feel busy.
8. Extract the key beats. Prioritize goals, disallowed goals, red cards, VAR decisions, tactical swings, substitutions, saves, woodwork, stoppage time, extra time, penalties, qualification consequences, departures, arrivals, public ceremonies, and emotional turning points.
9. Turn facts and selected material into a story outline with a beginning, escalation, turning point, decisive moment, and aftertaste. Avoid news-feed summaries.
10. Choose page count before writing panels. Do not force too many beats into one page.
11. Write in Chinese by default unless the user requests another language.
12. Keep captions short and image-friendly. Preserve identity anchors: teams, key people, minute, score, and result when they matter.
13. If generating images, use generic kits and visual proxies instead of official crests, protected tournament logos, sponsors, or watermarks unless the user provides licensed assets or asks only for text.

## Output Shape

For staged execution, first produce only:

- Event point: the user's keyword, match, or episode topic.
- Fact sources: official or authoritative sources used to verify the event.
- Fact package: teams/people, date, venue, score/result when relevant, timeline, and consequences.
- User supplement checkpoint: ask for optional keywords or material angles before the second search unless the user requested a fast one-pass output.

After the user answers the supplement checkpoint, continue with:

- Material sources: broader internet sources used for visual, emotional, tactical, or public-discussion material.
- Material pool: core event elements, environment, reactions, match-mechanism elements, symbols, and usable close-ups.
- Selected materials: explain which non-core elements are worth using and why.
- Story outline: the distilled dramatic arc.
- Page-count judgment: explain why the event needs 1 page, 2-3 pages, 4-5 pages, or a split episode.
- Page plan: each page title, dramatic purpose, and covered beats.
- Comic script: page number, panel role, scene, action, caption/dialogue, visual emphasis, and reading order.
- Image prompt: one prompt per manga page by default. Include cover prompts only for chapter covers, major events, social cover requests, or final collections.
- Boundary note: state what is factual and what is manga expression.

Use `references/panel-template.md` for a reusable structure.

## Tone Selection

Ask only if tone is genuinely important and absent. Otherwise infer:

- News comic: balanced, factual, editorial.
- Hot-blooded manga: exaggerated motion, heroic framing, emotional close-ups.
- Black-and-white Japanese football manga: traditional shonen sports manga, monochrome ink linework, screentone shadows, dense hatching, strong perspective football action panels, speed lines, sharp speech bubbles, crowd reaction cutaways, tactical pressure, breakthroughs, shots, and key duels. Avoid color, photorealism, cute/chibi proportions, official logos, and supernatural effects unless requested.
- Comedy four-panel: ironic captions, reaction shots, one punchline.
- Epic knockout recap: cinematic lighting, larger stakes, trophy or bracket consequences.
- Tragic exit: restrained color, empty space, missed chance, defeated body language.

## Cover Design

For serial social-media slide comics, do not add a cover to every episode by default. Start directly with manga page 1 unless the user asks for a cover.

- Use covers for chapter openings, major finals, special episodes, publication packages, and collected editions.
- Cover format: vertical first, usually 3:4 or 9:16. Mention that a 16:9 variant can be made for WeChat article headers if needed.
- The cover should not use multi-panel manga storytelling. Use one strong poster composition with a clear subject, bold title, and minimal supporting text.
- Make the cover readable as a thumbnail: large title, strong player silhouettes or duel pose, clear team color contrast, and one central symbolic object such as a ball, penalty spot, crossbar, stadium lights, trophy silhouette, or scoreboard fragment.
- Keep cover text short: title plus optional subtitle. Avoid long match summaries, dense facts, minute lists, and tiny captions.
- Use generic kits and symbolic design instead of official crests, tournament logos, or sponsor marks.
- The cover should promise the emotional hook of the comic, while the manga pages deliver the sequence of events.

## Manga Page Layout

For Japanese sports manga recaps, avoid standard four-panel, six-panel, or evenly spaced grid layouts unless the user explicitly asks for a grid. Use non-uniform manga page composition:

- Each generated image should be a complete manga page with multiple panels, not a single illustration of one scene. When using 2-3 images, each image is page 1/page 2/page 3 of the comic.
- Default social slide ratio is 3:4 vertical unless the user requests another format.
- Give the decisive action a large hero panel with a splash-page or double-page-spread feeling, even when the output is a single page.
- Intercut narrow reaction panels, foot/ball close-ups, goalkeeper-eye close-ups, scoreboard slivers, and crowd cutaways.
- Keep reading order clear with panel placement, motion direction, caption position, and visual rhythm.
- Let speed lines, speech bubbles, impact lettering, and sound effects participate in the composition, but keep text sparse and legible.
- Use large areas of white space or open pitch to express distance, pressure, isolation, and one-on-one duels.
- Vary panel shapes: tall vertical pressure panels, thin horizontal time-slice panels, diagonal action panels, small silent inserts, and one oversized main panel.
- Do not stack every panel as horizontal strips. Include vertical close-up panels or diagonal action panels when the page needs energy.
- Do not cram every beat onto one page. If a page would need more than 5-7 readable panels or too many captions, split the story.

## Text and Identity Rules

- Keep text minimal, but preserve identity anchors when needed: team names, key people, minute, score, and result.
- Prefer 5-8 information points per page at most.
- Keep each text block short; use labels, scoreboard fragments, jersey-name captions, title cards, or short speech bubbles.
- Use Chinese text by default.
- For generated images, ask for only the exact text items that should appear. If text accuracy matters, ask the model to leave clean caption spaces and add final text in post-production.
- Avoid jersey numbers unless they are confirmed and explicitly requested.

## Fact Safety

- Never invent scorers, minutes, cards, penalty takers, or VAR calls.
- If sources conflict, mention the conflict and use the more authoritative source.
- For ongoing matches, state the timestamp of the information and avoid final language.
- Do not claim a team advanced, won a group, or was eliminated unless standings consequences are confirmed.
- Avoid using exact official logos in image prompts. Use visual proxies such as "red shirts with white sleeves" or "deep navy shirts with a central stripe".

## Prompting Guidelines

When creating image prompts:

- Specify whether the prompt is for a social cover, chapter cover, or manga page.
- For cover prompts, specify platform-oriented vertical composition, title, subtitle, focal subject, thumbnail readability, and no multi-panel storytelling.
- For manga page prompts, specify page count, page-by-page beats, non-uniform panel layout, reading order, border style, and text constraints.
- Include only the exact text that should appear in the image.
- Use kit colors, player roles, body language, and stadium atmosphere to identify teams.
- Ask for clean, legible Chinese captions and no extra text. When final text must be accurate, ask for clean caption boxes and plan to overlay text later.
- For the default style, use "black-and-white Japanese football documentary manga", "non-uniform panel layout", "high contrast ink linework", "screentone shadows", and "speed lines".
- Add layout constraints when needed, such as: "Do not stack all panels as horizontal strips", "use one wide top panel", "use one diagonal action panel", and "use two stacked vertical close-up panels".

For image generation, prefer invoking the `imagegen` skill/tool after the script is stable.
