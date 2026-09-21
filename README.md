# Codex Learning Skills

一组面向课程学习、概念理解、知识整理与长期复习的 Codex Skills，输出可直接放入 Obsidian 的中文 Markdown 笔记。

## Skills

### course-learning-obsidian-notes

用于完整阅读课程 PPT、PDF、讲义、课堂截图等材料，梳理一节课的知识结构，并生成系统化的 Obsidian 课堂笔记。

主要能力：

- 先建立课程主线、模块关系和学习目标，再解释具体知识；
- 讲清公式含义、符号、单位、适用条件和常见错误；
- 整理图表、流程、易混概念、题型与解题方法；
- 生成带 YAML Properties、双向链接、自测题和快速复习区的 Markdown 文件；
- 支持引导式学习和一次性生成完整课堂笔记两种工作方式。

适合：

- 学习一整节 Lecture；
- 整理课程 PPT 或讲义；
- 建立某一章的知识框架；
- 生成长期保存的课堂笔记。

### obsidian-concept-notes

用于解释一个概念、术语、理论、模型、方法或公式，并将其整理为可以独立存在、长期复用的 Obsidian 概念型永久笔记。

主要能力：

- 按“问题 → 直觉 → 定义 → 机制 → 示例 → 边界 → 应用 → 关系”建立完整理解；
- 解释为什么需要这个概念、它解决什么问题以及它如何工作；
- 讲解公式中的符号、变量关系、来源直觉、使用条件和识别信号；
- 主动补充最简单例子、标准例子、反例、易混概念和常见误解；
- 建立前置知识、上位概念、相关概念与后续知识之间的 Obsidian 双向链接；
- 生成带 YAML Properties、Mermaid、自测题、折叠答案和 30 秒回忆区的 Markdown 文件；
- 根据概念复杂度自动控制深度，避免把简单概念写成百科全书。

适合：

- 深入理解课程中出现的独立知识点；
- 为 Obsidian 建立 Evergreen Note / Permanent Note；
- 区分相似概念并修正常见误解；
- 把课堂笔记中的 `[[知识连接]]` 扩展为独立概念笔记。

## 如何选择

| 学习目标 | 推荐 Skill |
| --- | --- |
| 阅读并整理一整节课程 | `course-learning-obsidian-notes` |
| 从 PPT、PDF 或讲义生成课堂笔记 | `course-learning-obsidian-notes` |
| 深入解释一个独立概念 | `obsidian-concept-notes` |
| 创建可跨课程复用的永久笔记 | `obsidian-concept-notes` |

课堂笔记负责保存课程结构，概念笔记负责保存对单个知识点的长期理解。两者可以通过 Obsidian 双向链接相互连接。

## 安装

将需要的 Skill 文件夹复制到 Codex 的个人 Skills 目录：

```text
~/.codex/skills/course-learning-obsidian-notes
~/.codex/skills/obsidian-concept-notes
```

仓库中的源目录：

```text
skills/course-learning-obsidian-notes
skills/obsidian-concept-notes
```

重新打开 Codex 会话后即可使用。

## 使用

课程学习与课堂笔记：

```text
使用 $course-learning-obsidian-notes 阅读这份课件，并生成完整的 Obsidian 笔记。
```

独立概念永久笔记：

```text
使用 $obsidian-concept-notes 解释概念：贝叶斯定理，并生成 Obsidian 永久笔记。
```

也可以直接提出符合相应用途的请求，由 Codex 自动选择合适的 Skill。
