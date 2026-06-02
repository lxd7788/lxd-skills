---
name: concept-to-knowledge-cards
description: Convert a single AI, technology, tool, trend, or abstract concept into knowledge card content for ordinary AI-interested readers. Use when the user wants a concept turned into reviewed knowledge points first, then into Xiaohongshu/WeChat/short-video style knowledge cards; includes a required two-stage workflow with human review before final card generation.
---

# Concept To Knowledge Cards

Use this skill to turn one concept into knowledge card content. The user only needs to provide the concept. Assume the audience is ordinary people who are interested in AI, including people already using or working around AI but without deep technical expertise.

## Core Rule

Use a two-stage workflow:

1. First produce a knowledge-point draft for review.
2. Wait for the user to confirm, delete, add, or revise the knowledge points.
3. Only after confirmation, generate final knowledge card content.

Do not generate final cards directly when the user only gives a concept. Do not add new facts, cases, claims, or conclusions during the card stage unless they were present in the confirmed knowledge points.

## Stage 1: Knowledge-Point Draft

For a concept-only request, output a review-friendly draft with these 8 modules:

1. Concept in one sentence
   - Explain the concept in plain language.
   - Avoid leading with formal technical definitions.

2. Why it appeared
   - Explain the problem, need, or change behind the concept.

3. What problem it solves
   - Connect the concept to a real pain point for ordinary AI-interested users.

4. Core knowledge points
   - Provide 3 to 5 important points.
   - Keep them accurate and suitable for later cards.

5. How to understand it
   - Use a simple analogy, relationship explanation, or intuitive description.
   - Avoid analogies that distort the concept.

6. Where ordinary people can use it
   - Give concrete scenes instead of abstract industry labels.

7. Common misunderstandings
   - Identify 1 to 2 likely misunderstandings or overstatements.

8. Boundaries and limits
   - Explain what the concept cannot solve, when it may fail, or what should not be exaggerated.

End Stage 1 by asking the user to review, delete, add, or confirm the knowledge points. Keep the ask short.

## Stage 2: Knowledge Cards

Start Stage 2 only when the user confirms the Stage 1 content or provides revised knowledge points and asks for cards.

Generate 5 to 7 cards by default. Use 5 cards for simple concepts, 6 cards for regular concepts, and 7 cards for complex concepts. Do not force every Stage 1 module into a separate card.

Follow this reading order:

1. Cover card: grab attention.
2. Pain-point card: establish relevance.
3. One-sentence explanation card: create basic understanding.
4. Understanding card: make the abstract concrete.
5. Value card: show what changes or where it can be used.
6. Misunderstanding card: correct a likely misconception.
7. Boundary summary card: explain limits and close with a memorable summary.

Use flexible card types within those positions:

- Understanding card: choose analogy, relationship diagram, or workflow.
- Value card: choose before/after comparison, usage scenes, or case.
- Add workflow when the concept has clear steps.
- Add relationship diagram when the concept involves multiple objects.
- Add before/after comparison when the new-vs-old difference is clear.
- Add usage scenes when the concept has broad applications.
- Add misunderstanding when the concept is easily hyped or confused.

## Card Definitions

### Cover Card

Purpose: make the reader stop within 3 seconds and want to continue.

The cover card should create at least one of:

- Relevance: this has something to do with me.
- Curiosity: I have heard this, but may not really understand it.
- Reading desire: the following cards can help me understand quickly.

Do not use the cover to explain the whole concept, show a workflow, list many scenes, or pack in technical terms.

Useful cover patterns:

- Question: "Why does AI answer confidently but still get it wrong?"
- Misunderstanding: "You may have misunderstood RAG."
- Contrast: "It is not a smarter AI. It is AI that checks first."
- Relevance: "This AI concept is getting closer to ordinary work."
- Light urgency: "Without this concept, many AI tools feel harder to use."

Use light urgency sparingly. Avoid clickbait.

### Pain-Point Card

Purpose: make the reader feel "this is related to me."

Only describe the problem. Do not explain the mechanism yet.

### One-Sentence Explanation Card

Purpose: give a first plain-language understanding.

Use one short human explanation. It does not need to be a complete technical definition.

### Understanding Card

Purpose: make the abstract concrete.

Choose the best format for the concept:

- Analogy for broad abstract concepts.
- Relationship diagram for concepts involving multiple roles or objects.
- Workflow for concepts with clear steps.

### Value Card

Purpose: show what the concept changes or where it matters.

Choose before/after comparison, usage scenes, or one concrete case.

### Misunderstanding Card

Purpose: create judgment value and avoid shallow hype.

Correct 1 to 2 key misunderstandings using "many people think... actually..." when appropriate.

### Boundary Summary Card

Purpose: explain limits and leave a memorable final sentence.

Include what the concept is not, what it cannot guarantee, and one final sentence the reader can repeat.

## Output Format

For Stage 1, use:

```text
## 概念知识点整理稿

概念：

### 1. 一句话解释

### 2. 它为什么会出现

### 3. 它解决什么问题

### 4. 核心知识点

### 5. 可以怎么理解

### 6. 普通人能用在哪

### 7. 常见误解

### 8. 边界和限制

请审查这些知识点。你可以删除、补充、修改；确认后我再生成知识卡片。
```

For Stage 2, begin with one sentence naming the selected card count and types, then output cards:

```text
## 知识卡片 1：封面卡

封面类型：

卡片系列标签：

卡片主标题：

卡片副标题：

视觉主概念：

适合放大的关键词：

---

## 知识卡片 X：【卡片类型】

卡片标题：

卡片核心文案：

画面表现建议：

适合放大的关键词：
```

End Stage 2 with a brief image-readiness check:

```text
## 成图前检查

- 每张是否只讲一个重点：
- 是否有文字过长：
- 是否有未经确认的新知识：
- 是否适合普通 AI 兴趣用户理解：
- 是否适合做成 3:4 竖版图文：
```

## Writing Constraints

- Use short sentences.
- Keep each card focused on one point.
- Keep cover text minimal and attention-grabbing.
- Prefer plain language over technical terms.
- Translate necessary terms into human language.
- Use analogies, concrete scenes, and before/after changes when useful.
- Explain value and limits.
- Avoid turning cards into article screenshots.
- Use visual suggestions that can directly guide Xiaohongshu, WeChat image posts, or short-video storyboards.

