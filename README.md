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
