---
name: xiaohongshu-longform
description: Judge whether a draft or idea fits one of six Xiaohongshu long-form content types, then reorganize and rewrite it into a platform-native Xiaohongshu long post. Use when the user asks to evaluate, adapt, polish, rewrite, structure, or turn content into Xiaohongshu long-form notes, especially AI technology, tool tutorials, comparison posts, beginner guides, prompt/template posts, or trend-explainer posts.
---

# Xiaohongshu Longform

## Goal

Transform a user's raw idea, outline, draft, transcript, or article into a Xiaohongshu long-form note that is:

- written in Chinese unless the user asks otherwise
- written for a specific reader group
- focused on one concrete problem
- easy to scan
- actionable enough to follow
- structured for saves and shares
- grounded in experience rather than abstract commentary
- natural and human-written, not visibly generated from a rigid AI template

Do not rewrite as a WeChat-style essay, newsletter, general opinion piece, or mechanical "AI content framework" article.

## Workflow

1. Identify the intended reader, problem, and promised outcome.
2. Judge whether the content fits one of the six Xiaohongshu long-form types.
3. If it does not fit, explain why and suggest the nearest viable type or angle.
4. If it fits, rewrite it using Xiaohongshu-native long-form structure.
5. Output a ready-to-post draft plus a short optimization checklist.

## Six Long-Form Types

Use exactly one primary type unless the user's content naturally needs a hybrid.

| Type | Use When | Structure Focus |
| --- | --- | --- |
| Beginner explainer | The reader does not understand a concept, tool, or category | Analogy, concept translation, use cases, first steps |
| Tool tutorial | The reader wants to learn how to use a tool or workflow | Steps, settings, examples, completion standard |
| Comparison and choice | The reader is choosing between tools, methods, or paths | Recommendation, table, scenario-based choice |
| Pitfall guide | The reader is likely to make common mistakes | Wrong move, why it fails, better move |
| Template or prompt pack | The reader wants reusable assets | Scenario, template, example, customization notes |
| Trend translation | A news item or release needs translation for ordinary users | What happened, why it matters, what to do, what not to panic about |

## Fit Test

Before rewriting, state the classification result in Chinese with these fields:

- content judgment: fits / partly fits / does not fit
- best matching type
- reason
- recommended angle

Use these criteria:

- Has a clear target reader?
- Solves one concrete problem?
- Can produce a checklist, steps, table, template, or route map?
- Can the useful point appear in the first 10 seconds?
- Is the content more useful as a method than as an opinion?
- Does it reduce confusion, save time, prevent mistakes, or help a decision?

If fewer than three criteria are present, do not force a rewrite. Recommend a sharper angle first.

## Rewrite Rules

### Title

Generate 3-5 Chinese title options. Prefer:

- clear reader group
- clear problem
- clear benefit
- searchable keywords

Avoid abstract titles such as "AI era opportunities" or "Some thoughts on Claude".

### Opening

Start fast, but do not mechanically use the Chinese phrase that means "first, the conclusion" as a section title. That phrase is now overused and makes the draft feel AI-generated.

Prefer a natural opening that does one of these:

- names the reader's real misunderstanding
- points out a common wrong use case
- gives a sharp practical takeaway in plain language
- says who should keep reading and why

Do not force every post to open with the exact audience-filter template. Use an audience filter only when it sounds natural.

Good opening pattern:

```text
Many people use Codex by first asking it to write code.
But after trying it in real workflows, the bigger value is not code generation itself.
The real difference is whether it can enter your whole workflow.
```

When writing the final post, translate this pattern into natural Chinese. Do not output this English example unless the user asks for English.

### Body

Use modular sections, but avoid repeating a fixed AI-looking outline.

Do not require fixed section names such as:

- first, the conclusion
- why this problem happens
- core method
- exact steps
- common mistakes
- action checklist

Instead, create section headings that fit the actual content. Good headings should sound like edited human notes. For example, for a Codex article:

- Do not keep it only inside the codebase
- Long-running threads are the hidden workflow layer
- Interrupt when it drifts; queue the next step when it is still running
- Turn repeated workflows into Skills
- Long tasks need verification criteria

When writing the final post, translate headings into natural Chinese and make them sound native to Xiaohongshu.

Keep paragraphs short. Use numbered lists, tables, templates, and examples. Make every section useful even when skimmed.

### Anti-AI Writing Rules

Actively remove "AI smell" from the final draft:

- Do not overuse Chinese transition words equivalent to "firstly / secondly / finally".
- Do not make every section the same length or same rhythm.
- Do not over-explain obvious transitions.
- Do not stack generic phrases equivalent to "in today's era", "it cannot be ignored", or "it has great significance".
- Do not use a perfectly symmetrical framework if the source content does not need it.
- Do not end every section with a summary sentence.
- Do not use a one-sentence-summary block unless it genuinely adds punch.
- Vary sentence length and paragraph shape.
- Preserve concrete details from the source.
- Write like a sharp creator summarizing real experience, not like a report.

### Tone

Write like an experienced practitioner, not a dictionary. Prefer natural Chinese expressions equivalent to:

- "After trying it, I found..."
- "Beginners most often get stuck here..."
- "I do not recommend starting with..."
- "If you are just starting, do this first..."
- "The useful part is not X, but Y..."

Do not turn the post into a diary. Use experience to package method.

### Collectable Structure

Every rewrite must include at least one save-worthy unit:

- checklist
- step-by-step process
- prompt/template
- comparison table
- pitfall list
- 3/5/7-day route map

For AI technology content, prefer practical structures such as tool selection tables, prompt templates, workflow steps, and beginner practice scenarios.

## Output Format

Return in Chinese and in this order:

1. Content judgment
   - classification result
   - best matching type
   - why it fits or does not fit
   - recommended angle
2. Title options
   - 3-5 Xiaohongshu title options
3. Xiaohongshu long-form draft
   - ready-to-post Chinese draft
   - natural opening, not a rigid template
   - modular body with content-specific headings
   - save-worthy checklist/template/table
4. Pre-publish checklist
   - 5-8 concise checks or suggestions

Use natural Chinese labels for these sections in the final answer.

## Quality Bar

Before finalizing, check the draft against these questions:

- Who is this for?
- What specific problem does it solve?
- Is the value visible early without using a stiff "first, the conclusion" block?
- Can readers scan it?
- Can readers follow it immediately?
- Does it save time, prevent mistakes, or help decisions?
- Does it contain a collectable structure?
- Does it sound like a human creator with judgment, rather than a generic AI rewrite?
- Would readers want to share it with someone similar?

Revise if the draft feels too polished, too symmetrical, or too generic.
