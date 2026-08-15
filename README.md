# study-resource-generator

一个用于 Claude Code 的 Obsidian-first 中文学习资料包生成 skill：把任意技术主题整理成结构化的学习路线、学习方式、学习进度和章节复习记录，并根据主题选择合适的 Demo 介质。默认使用双链、Dataview 和闪卡等 Obsidian 能力，同时保留普通 Markdown 兼容模式。

## 功能

- 为编程语言、框架、数据库、CLI 工具和纯理论主题生成学习路线。
- 按 5 步循环组织学习：理论文档、Demo、理论学习、Demo 实操、进度与复习。
- 使用可复用模板统一章节目录、Demo README、进度记录和复习记录。
- 默认使用 YAML frontmatter、Callout、Mermaid、任务列表、双链、Dataview 和 Spaced Repetition 闪卡。
- Obsidian 的 MOC 总览页仍按需生成，不会默认增加核心文件。
- 用户明确要求普通 Markdown、GitHub、Typora、VSCode 或非 Obsidian 输出时，跳过双链、Dataview 和插件专属语法。
- 中文输出，技术术语保留英文原词。

## 安装

将本仓库放入 Claude Code 的 skills 目录：

```bash
git clone https://github.com/aiktus/study-resource-generator.git .claude/skills/study-resource-generator
```

也可以将仓库目录复制到个人 skills 目录下的 `study-resource-generator/`，确保 `SKILL.md` 与 `references/` 位于同一级目录。

## 使用

在 Claude Code 中直接描述学习需求，例如：

```text
帮我制定一套 Docker 学习资料
```

```text
我想系统学习 FastAPI，目标是做一个后端项目
```

默认使用 Obsidian 增强。需要普通 Markdown 兼容输出时，明确说明：

```text
请按普通 Markdown 输出 FastAPI 学习资料，不要使用 Obsidian 双链和 Dataview
```

如果主题、学习背景或 Demo 介质无法从请求中判断，skill 会先询问必要信息。生成资料包后，说“开始学习”即可按学习方式文档开始第一章。

## 作者想说的话

使用这个 Skill 生成出来的学习文档，阅读起来更加流畅，学习过程更加舒服，也更适合沉浸式学习。你可以把任何想学的知识、已有课程资料、练习题或面试复盘交给这个 Skill，按照统一模板生成一套结构清晰、可以持续迭代的学习资料。

下面是我实际使用过的三类提示词。示例中的路径请替换成你自己的实际路径；如果 skill 已经安装到 Claude Code 的 skills 目录，也可以直接说“请使用 `study-resource-generator` skill”。

### 1. 根据面试复盘查漏补缺

```text
根据“<面试复盘文件路径>”中的内容，生成一份学习资料。

学习路线不用太完整，重点是针对面试中的遗忘点进行复习和查漏补缺，不是初次学习。生成的内容可以适当扩展，偏复杂、偏高级一些，面向 Java 高级开发者，不要按新手路线组织。

请使用 study-resource-generator skill，按照它的产出格式生成文件。
```

### 2. 根据 PDF 练习题生成学习资料

```text
根据“<软件测试与质量保证综合练习题.pdf 的路径>”中的所有试题，按照 study-resource-generator skill 的产出格式生成完整的学习资料和文件。

请覆盖 PDF 中的全部试题，并把试题涉及的知识点整理成适合复习、查漏补缺和章节练习的结构。
```

### 3. 从已有课程资料指定起点开始学习

```text
根据“<课程资料目录路径>”下的学习资料目录和内容，按照 study-resource-generator skill 的产出格式生成学习资料。

我要从 Transformer 开始学习，也就是只生成 Transformer 及之后的内容；Transformer 之前的内容我已经学完，不需要重复生成。
```

这三类场景分别对应：从经验中找短板、从题目反推知识体系、从已有课程资料中裁剪学习范围。你也可以把它们组合起来，生成更贴合自己目标的学习路线。

## 仓库结构

```text
study-resource-generator/
├── SKILL.md
└── references/
    ├── method-template.md
    ├── obsidian-template.md
    ├── roadmap-template.md
    └── tracking-templates.md
```

`obsidian-template.md` 默认读取；只有明确使用普通 Markdown / 非 Obsidian 模式时跳过。MOC 仍按需生成。

这个 skill 生成的是学习资料脚手架。逐章理论文档和 Demo 会在后续开始学习时生成，不会在首次创建资料包时一次性生成。

## 许可证

[MIT License](LICENSE)
