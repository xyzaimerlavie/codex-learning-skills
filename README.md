# Codex Learning Skills

一组面向课程学习、知识整理与长期复习的 Codex Skills。

## Skills

### course-learning-obsidian-notes

完整阅读课程 PPT、PDF、讲义或课堂截图，帮助建立知识结构，并生成可直接放入 Obsidian 的中文学习笔记。

主要能力：

- 先建立课程主线与模块关系，再解释具体知识。
- 讲清公式含义、符号、单位、适用条件和常见错误。
- 整理图表、流程、易混概念、题型与解题方法。
- 生成带 YAML Properties、双向链接、自测题和快速复习区的 Markdown 文件。
- 使用 Obsidian 原生可折叠 Callout 显示参考答案。

## 安装

将需要的 Skill 文件夹复制到 Codex 的个人 Skills 目录。例如：

```text
~/.codex/skills/course-learning-obsidian-notes
```

当前 Skill 的源目录：

```text
skills/course-learning-obsidian-notes
```

重新打开 Codex 会话后即可使用。

## 使用

可以直接提出课程学习或课程笔记请求，也可以显式调用：

```text
使用 $course-learning-obsidian-notes 阅读这份课件，并生成完整的 Obsidian 笔记。
```

## 答案折叠格式

该 Skill 使用 Obsidian Callout，保证参考答案默认折叠并正常渲染：

```markdown
> [!question]- 点击查看参考答案
>
> ### 基础题答案
>
> 1. 答案内容
```
