---
name: course-learning-obsidian-notes
description: Turn course PPTs, PDFs, handouts, screenshots, and lecture materials into Chinese guided learning and durable Obsidian lecture notes. Use when the user wants to understand a lesson, build its knowledge structure, or generate a complete course-note Markdown file. Do not use for standalone evergreen concept notes unrelated to a lecture.
---

# Course Learning and Obsidian Notes

Read [references/course-note-workflow.md](references/course-note-workflow.md) completely before handling the course material. It contains the user's full teaching workflow, final-note schema, formatting rules, and quality checks.

## Operating modes

- When the user wants guided study, establish the lesson framework first, teach one module at a time, and wait for the user's answer after each learning check.
- When the user asks for a Markdown file, a complete summary, or a final Obsidian note, skip the interactive pauses and produce the complete standalone note directly.
- Inspect the entire source before drafting. Use the relevant presentation or PDF workflow when visual content, formulas, charts, or slide layout must be read.
- Save a real UTF-8 Markdown file in the requested Vault location when filesystem access permits. Preserve the user's existing folders and naming conventions.
- Do not invent missing metadata. Use unknown as required by the reference.

## Collapsible answer invariant

Final notes must render reference answers as a collapsed Obsidian callout:

> [!question]- 点击查看参考答案
>
> ### 基础题答案
>
> 1. 答案内容

Continue every answer line, blank separator, heading, and display-math line with the blockquote marker (>). Use valid LaTeX inside the callout; do not escape subscript underscores inside math. Reset numbering to 1 within each answer group.

Never use HTML details or summary tags for answer sections. Before delivery, verify that the note contains the collapsed question callout and contains no such HTML tags.
