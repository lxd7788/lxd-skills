---
name: football-match-comic
description: Turn football match reports, live blogs, scorelines, and user-provided match notes into verified comic scripts and image-generation prompts. Use for World Cup, Champions League, domestic cup, derby, knockout, penalty shootout, or any soccer/football match when the user wants a manga/comic recap, match storyboards, non-uniform Japanese sports manga pages, key-moment extraction, captions, or sports-comic image prompts.
---

# Football Match Comic

Create fact-checked football match comic scripts from recent or historical match information.

## Core Workflow

1. Verify match facts before scripting when the user asks about a recent, live, or just-finished match. Browse current sources for score, venue, timeline, scorers, cards, substitutions, VAR, penalties, injuries, and standings implications. Prefer official competition pages, federation/club reports, reputable live blogs, and stat providers.
2. Separate confirmed facts from inferred drama. Mark uncertain items as assumptions or omit them from the comic.
3. Extract 4-8 key beats. Prioritize goals, disallowed goals, red cards, VAR decisions, tactical swings, substitutions that changed the match, goalkeeper saves, woodwork, stoppage-time events, extra time, penalties, and qualification consequences.
4. Choose a page plan before choosing panels:
   - 1 page for 3-5 key beats or one clean dramatic arc.
   - 2 pages for 6-8 key beats, a first-half/second-half turn, or a match with multiple tactical swings.
   - 3 pages for chaotic knockout matches, extra time, penalty shootouts, or finals where too many decisive moments would crowd one page.
   - Do not force every key beat into one image. Split pages when captions, score context, and action would become cramped.
5. Write the comic in Chinese by default unless the user requests another language.
6. Keep captions short and image-friendly. Avoid tiny text, long paragraphs inside panels, and overloaded scoreboards.
7. If generating an image, use generic kits and colors rather than official crests or protected tournament logos unless the user provides licensed assets or asks only for a text script.

## Output Shape

For each match, produce:

- Match card: teams, final score, competition stage, venue, date, and outcome.
- Key nodes: minute-by-minute list of the decisive events.
- Page plan: 1-3 pages, each with a title, dramatic purpose, and the beats it covers.
- Comic script: page number, panel role, scene, action, caption/dialogue, visual emphasis, and reading order.
- Image prompt: one prompt per page by default. Use separate panel prompts only when the user explicitly asks for individual images.
- Source notes: links or names of sources used for facts.

Use `references/panel-template.md` when a reusable structure is helpful.

## Tone Selection

Ask only if tone is genuinely important and absent. Otherwise infer:

- News comic: balanced, factual, editorial.
- Hot-blooded manga: exaggerated motion, heroic framing, emotional close-ups.
- Black-and-white Japanese football manga: traditional shonen sports manga, monochrome ink linework, screentone shadows, dense hatching, strong perspective football action panels, speed lines, sharp speech bubbles, crowd reaction cutaways, tactical pressure, breakthroughs, shots, and key duels. Avoid color, photorealism, cute/chibi proportions, official logos, and supernatural effects unless requested.
- Comedy four-panel: ironic captions, reaction shots, one punchline.
- Epic knockout recap: cinematic lighting, larger stakes, trophy or bracket consequences.
- Tragic exit: restrained color, empty space, missed chance, defeated body language.

## Manga Page Layout

For Japanese sports manga recaps, avoid standard four-panel, six-panel, or evenly spaced grid layouts unless the user explicitly asks for a grid. Use non-uniform manga page composition:

- Each generated image should be a complete manga page with multiple panels, not a single illustration of one scene. When using 2-3 images, each image is page 1/page 2/page 3 of the comic.
- Give the decisive action a large hero panel with a splash-page or double-page-spread feeling, even when the output is a single page.
- Intercut narrow reaction panels, foot/ball close-ups, goalkeeper-eye close-ups, scoreboard slivers, and crowd cutaways.
- Keep reading order clear with panel placement, motion direction, caption position, and visual rhythm.
- Let speed lines, speech bubbles, impact lettering, and sound effects participate in the composition, but keep text sparse and legible.
- Use large areas of white space or open pitch to express distance, pressure, isolation, and one-on-one duels.
- Vary panel shapes: tall vertical pressure panels, thin horizontal time-slice panels, diagonal action panels, small silent inserts, and one oversized main panel.
- Do not cram every beat onto one page. If a page would need more than 5-6 readable panels or more than 4 short captions, split the story across 2-3 pages.

## Fact Safety

- Never invent scorers, minutes, cards, penalty takers, or VAR calls.
- If sources conflict, mention the conflict and use the more authoritative source.
- For ongoing matches, state the timestamp of the information and avoid final language.
- Do not claim a team advanced, won a group, or was eliminated unless standings consequences are confirmed.
- Avoid using exact official logos in image prompts. Use visual proxies such as "red shirts with white sleeves" or "deep navy shirts with a central stripe".

## Prompting Guidelines

When creating image prompts:

- Specify page count, page-by-page beats, non-uniform panel layout, reading order, border style, and text constraints.
- Include only the exact text that should appear in the image.
- Use kit colors, player roles, body language, and stadium atmosphere to identify teams.
- Ask for clean, legible Chinese captions and no extra text.
- Use "sports newspaper comic", "modern manga", or "dynamic editorial comic" for a reliable style.

For image generation, prefer invoking the `imagegen` skill/tool after the script is stable.
