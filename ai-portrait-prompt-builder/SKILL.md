---
name: ai-portrait-prompt-builder
description: Convert user-provided portrait, fashion, editorial, beauty, lifestyle, or AI photo reference images into reusable AI portrait generation prompts. Use when the user wants Codex to analyze reference images and produce unified visual requirements, shot-by-shot camera prompts, negative prompts, style systems, AI 写真提示词, 人像生成提示词, 统一视觉要求, 镜头内容, or a batch prompt plan for AI portrait/photo generation.
---

# AI Portrait Prompt Builder

Use this skill to turn reference images and simple user preferences into structured AI portrait/photo prompts. The user may not know photography vocabulary; infer it from the images and explain only when helpful.

## Inputs To Gather

Proceed with available context. Ask only if the missing answer changes the output materially.

- Reference images: analyze visible style, not hidden intent.
- Subject handling: preserve the user's face if requested; otherwise treat references as style-only.
- Use case: avatar, portrait set, social post, cover, commercial profile, couple/family photo, etc.
- Count and ratio: default to 10 shots, 2 variants each, ratio 2:3 for portrait sets.
  - Shots 1-5 should be reference-led: derive them closely from the visible images, preserving the core scene, styling, lighting, and composition logic.
  - Shots 6-10 should be photographer-led: act as a professional portrait/fashion photographer and freely extend the set under the same subject, scene, styling, task, lighting, and color conditions.
- Preference notes: "高级", "温柔", "不要网红感", "更电影", "更干净", etc.

## Image Analysis Checklist

Extract only what is visually supported or reasonably implied:

- Visual theme: editorial, cinematic, studio portrait, lifestyle, new Chinese, Korean, French, vintage, clean commercial, etc.
- Scene and props: indoor/outdoor, wall/fabric/window/furniture/florals, modern or period details.
- Wardrobe and styling: silhouette, material, color, accessories, hair, makeup.
- Lighting: soft/hard, direction, window light, fill, rim light, contrast, shadow pattern.
- Color and texture: palette, warmth, saturation, grain, skin finish, background texture.
- Composition: close-up, bust, half-body, full-body, negative space, foreground occlusion, side profile, gaze.
- Constraints: what must remain clean, readable, unbranded, uncluttered, or not copied exactly.

## Output Structure

Return prompts in Chinese unless the user asks otherwise.

Use this structure:

```text
一、统一视觉要求
以上传照片中的人物为原型，在完全保留人物原生面部特征、五官特点的基础上生成一张；不沿用原图服饰/发型/背景，一切以当前为准：

[场景与背景]
[人物与服装]
[妆发与配饰]
[摄影质感]
[光线与色彩]
[清晰度与皮肤]
[画面限制]

二、镜头内容
镜头1：...
镜头2：...
镜头3：...
镜头4：...
镜头5：...
镜头6：...
镜头7：...
镜头8：...
镜头9：...
镜头10：...

每一个镜头分别生成2张，10个镜头为20张。
比例 2:3。

三、负面要求
不要文字、不要品牌logo、不要脸部变形、不要过度磨皮、不要塑料皮肤、不要现代杂物、不要杂乱背景、不要遮挡双眼与鼻梁、不要过曝、不要死黑、不要明显AI感。
```

## Writing Rules

- Separate the stable visual system from shot-specific content.
- Keep the "统一视觉要求" reusable across all shots.
- Make each shot change one or two meaningful variables: distance, angle, gaze, pose, prop interaction, foreground, negative space, light/shadow.
- Protect identity and facial readability: eyes, nose bridge, mouth, face outline, and key features should stay clear unless the user explicitly requests abstract or obscured images.
- Avoid overfitting to a reference image if the user wants original AI portraits; describe transferable visual qualities instead of copying exact copyrighted composition or brand-specific styling.
- Prefer concrete visual language over camera jargon, but include useful terms such as 中近景, 半身中景, 侧颜, 远景留白, 浅景深, 大面积柔光, 轮廓光, 前景虚化.
- Include "无品牌无文字" when jewelry, clothing, products, or props appear.
- For batch sets, ensure visual continuity: same subject, same styling logic, same color temperature, same environment.
- For the default 10-shot output, split the work into two groups:
  - Shots 1-5: infer concrete shots from the reference images. They should feel like natural extensions of what is already visible.
  - Shots 6-10: write as a professional photographer's creative expansion. Keep the same subject, environment, wardrobe logic, props, task purpose, color temperature, and lighting motivation, but introduce more ambitious composition, posing, foreground depth, shadow play, negative space, editorial details, or emotional beats.
- Photographer-led shots must still be practical and generatable. Do not introduce a new location, incompatible wardrobe, unrelated props, different season, different lighting style, or a different character unless the user explicitly asks.
- If the user requests a different count, preserve the two-stage logic when possible: first half reference-led, second half photographer-led.

## Shot Pattern Suggestions

Use or adapt these patterns:

- Clean cover shot: 中近景/肩上构图, face dominant, controlled expression, clean background.
- Side profile: 侧颜 or 三分之二角度, gaze away, facial structure readable.
- Interaction shot: hands touching prop, fabric, flower, cup, chair, book, etc.
- Detail shot: fabric, jewelry, hand, collar, makeup texture, with face partially present or implied.
- Negative-space shot: subject near one side, large clean background area.
- Foreground depth shot: flowers, curtain, glass, leaves, or fabric as soft foreground, never covering eyes/nose unless requested.
- Light/shadow shot: window shadow or rim light on background/props, not destroying face readability.
- Closing shot: softer, quieter, emotionally restrained, useful as final image or cover alternate.

## If The User Provides Only A Style Sentence

Build a complete prompt from the sentence, but mark uncertain choices as tasteful defaults. Example defaults:

- portrait ratio: 2:3
- set size: 10 shots x 2 variants, with shots 1-5 reference-led and shots 6-10 photographer-led
- skin: realistic texture, not over-smoothed
- lighting: large soft key light or natural window light
- background: clean, low-information, no logos or text

## If The User Wants Direct Generation

If image generation is requested, use the available image generation workflow/tool after writing or confirming the prompt. Do not generate images when the user only asks for prompt text.
