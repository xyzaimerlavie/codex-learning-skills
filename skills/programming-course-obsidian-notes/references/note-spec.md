# Programming Course Note Specification

## Outcome

The note is for a future reader who may have forgotten the lesson. It must quickly answer:

- What is this feature or concept?
- Why does it exist?
- How is it written and used?
- What happens when the code runs?
- What do important functions return?
- When should it be chosen?
- How does it differ from similar constructs?
- What is easy to forget or misuse?
- Where is the shortest reliable syntax reference?

Prioritize, in order:

1. Relearning clarity over volume.
2. Practical behavior over abstract definition.
3. Small code examples over long theory.
4. Reasons and tradeoffs over memorized rules.
5. Common use over obscure features.
6. Pitfalls and lookup speed over decorative formatting.

## Inspect and Reorganize the Source

Read the whole source before drafting. Identify the actual knowledge modules, then:

- merge repeated animation or incremental-reveal slides;
- omit decoration, marketing, course navigation, and repeated summaries;
- omit source cases, exercises, project briefs, and classroom tasks unless the user explicitly asks to retain them;
- preserve rules, semantics, syntax, parameters, return values, diagrams that explain execution, comparisons, and limitations;
- add only the minimum missing context required to understand the code;
- organize the note by knowledge rather than slide order.

Never write “slide 1 says…” or reproduce the lecture as a transcript.

## Metadata

Use this stable frontmatter unless the user provides a different schema:

```yaml
---
type: code-note
course: "课程名称"
semester: unknown
lecture: "Chapter 2 / Lecture 01"
topic: "本讲主题"
language: "编程语言"
teacher: unknown
date: unknown
source: "Lecture PPT"
status: learned
tags:
  - programming
  - 编程语言
  - 本讲主题
---
```

Rules:

- Keep the field names stable across a course.
- Quote ordinary string values. `unknown` may remain unquoted.
- Use a known `YYYY-MM-DD` date only when the source supplies one.
- Adapt `source` to `Lecture PDF`, `Handout`, or another accurate label when needed.
- Keep tags few and useful: programming language, major topic, and at most one course-level tag.

## Filename

Default to:

```text
Lesson 01 - 数据存储与运算.md
Lesson 02 - 流程控制语句.md
```

Use two-digit lesson numbers. Remove filesystem-invalid characters. Follow a user-specified naming scheme over this default.

## Recommended Note Structure

Adapt the structure to the lesson; delete irrelevant sections rather than filling them with boilerplate.

```markdown
# 本讲主题

> [!summary] 这讲在干什么
> 用 1–3 句话说明核心问题和学完后的能力。

## 本讲会学到什么

- …

---

## 整体知识框架

基础概念 → 核心语法 → 执行行为 → 常见使用 → 组合关系

---

# 1. 核心模块

## 1.1 知识点

### 一句话理解

### 为什么需要它

### 基本写法

### 怎么使用与运行结果

### 参数和返回值

### 什么时候使用

> [!tip] 以后容易忘
> …

> [!danger] 常见错误
> …

---

# 易混概念对比

# ⚠️ 最容易忘的内容

# ⚡ 代码速查

# 🧠 重新学习版总结

# 🔗 知识连接
```

For a simple topic, combine subsections and keep the note shorter. For containers, functions, classes, generators, decorators, exceptions, NumPy arrays, or DataFrames, expand the sections that materially improve relearning.

## Concept Explanation Pattern

For each important construct, prefer this order:

1. One-sentence intuition.
2. Smallest useful code.
3. Output or resulting state.
4. Common operation.
5. Why it behaves that way.
6. Confusing alternatives.
7. Real use signals.
8. Quick-reference form.

Do not force every heading onto trivial functions. A short explanation can be enough for `len()` or a similarly simple tool.

## Code Examples

- Use clear, short names and small input data.
- Demonstrate one idea per example.
- Prefer examples that run independently.
- Show output with a `text` code block when the result matters.
- Explain mutations and return values separately.
- For important parameters, state what each controls, whether it is required, and the usual value.
- Do not copy a complex course case merely to demonstrate syntax.

Example:

```python
numbers = [1, 2, 3]
result = numbers.append(4)

print(numbers)
print(result)
```

Output:

```text
[1, 2, 3, 4]
None
```

Explain that `append()` mutates the list and returns `None`.

## Comparisons

Proactively compare constructs that are commonly confused, for example:

- `list` vs `tuple`
- `append()` vs `extend()`
- `remove()` vs `pop()`
- `sort()` vs `sorted()`
- `==` vs `is`
- `for` vs `while`
- `break` vs `continue`
- `return` vs `print`
- `dict.get()` vs `dict[key]`

Compare only differences that affect use. A compact table is preferred when several fields repeat.

## Source Corrections and Supplements

Do not silently reproduce a technical mistake. State the accurate behavior in the main note. If the correction or prerequisite goes beyond the source, mark it:

```markdown
> [!info] 补充理解
> 以下内容并非 PPT 原文，而是理解当前知识所需的补充。
```

If the source lacks enough context to determine behavior, do not invent it:

```markdown
> [!question] 上下文不足
> 当前材料缺少部分代码，因此这里只解释能够确定的内容。
```

## Quick Reference

The quick-reference section should contain the most reusable syntax in one or a few cohesive code blocks. It should let the reader recover a forgotten spelling or call pattern within seconds. Do not duplicate every earlier example.

## Relearning Summary

Answer these questions briefly:

### 这东西是干什么的？

### 最基本怎么写？

### 最常用的几个操作是什么？

### 我什么时候会用到它？

### 最容易和什么搞混？

### 最容易忘什么？

### 如果只重新看 30 秒，要看什么？

## Course Index Note

For a multi-lesson course index such as `0Python.md`, include:

- a short course summary;
- an ordered learning path;
- one Wiki link per lesson with 2–4 concise topic bullets;
- a small dependency table when it clarifies progression;
- the named Base view embed when a Base exists;
- a brief note on how to use the collection for first learning and later lookup.

Example embed:

```markdown
![[Python核心语法.base#Python 核心语法]]
```

Do not include the index note in a Base intended only for lesson notes.

## Base File

Use a stable `type: code-note` property to scope the view. A minimal course Base can follow this pattern:

```yaml
filters:
  and:
    - 'file.ext == "md"'
    - 'file.inFolder("Study/Code/Python")'
    - 'type == "code-note"'
    - 'course == "Python核心语法"'
properties:
  file.name:
    displayName: "笔记"
  lecture:
    displayName: "章节"
  topic:
    displayName: "主题"
  language:
    displayName: "语言"
  status:
    displayName: "状态"
views:
  - type: table
    name: "Python 核心语法"
    order:
      - file.name
      - lecture
      - topic
      - language
      - status
```

Replace folder, course, and view names with verified values. If a `.base` file already exists, inspect and preserve its unrelated configuration before editing.

## Optional Self-Tests

Do not add exercises or self-tests by default. When the user explicitly requests them, keep them short and use this exact answer container:

```markdown
> [!question]- 点击查看参考答案
>
> ### 基础题答案
>
> 1. 答案内容
```

Every line inside the callout, including blank lines and display-math lines, must begin with `>`. Never use `<details>` or `<summary>`.

## Final Validation

Check all of the following:

- The source was inspected completely.
- Each source lesson produced exactly one Markdown note.
- YAML parses and uses stable fields.
- Unknown metadata was not invented.
- Filenames use the requested scheme and two-digit numbering.
- The note is organized by knowledge, not slide pages.
- Source cases, exercises, projects, and exam content are absent unless requested.
- Necessary code examples are small, correct, and show important results.
- Important parameters and return values are stated.
- Similar constructs are compared where useful.
- Pitfalls and quick-reference code are easy to find.
- Code fences are paired; heading levels and callouts render correctly.
- Cross-links use the final filenames and have no obsolete targets.
- The index lists each lesson once.
- The Base excludes the index note and returns every lesson when queried.
