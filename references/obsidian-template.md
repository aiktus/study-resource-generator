# Obsidian 专属约定（第二档）

默认读取本文，并把下面的规则作为独立小节注入主题的学习方式文档。只有用户明确要求普通 Markdown、GitHub、Typora、VSCode 或非 Obsidian 输出时，才跳过、不要复制或不要执行这些规则。

## 注入内容

本主题学习资料按 Obsidian 增强，以下语法仅在 Obsidian 中生效：

- **双链**：学习路线知识点、理论文档跨章引用（如 `参见 [[3.Self-Attention详解]]`）、Demo README 的「对应理论文档」映射表，一律用 `[[ ]]` 链接；重命名文件后检查断链。
- **frontmatter**：每个理论 `.md` 头部带 `status`、`stage`、`importance`、`review` 属性，第 5 步更新进度时同步刷新；字段定义见 `references/tracking-templates.md`。
- **Dataview**：`3.学习进度.md` 顶部维护自动汇总查询（未学 / 待复习清单），手工记录追加在查询块之后，两者并存。例如：
  ````markdown
  ```dataview
  TABLE status, stage, importance, review AS "上次复习"
  FROM "<主题>"
  WHERE status != null
  SORT review ASC
  ```
  ````
- **闪卡（编程类）**：`本章节面试常考内容.md` 中每道题额外用 `问题::答案` 单行格式或 `- 问题::答案` 列表项标记，供 Spaced Repetition 插件生成间隔复习卡片；不安装插件时只是普通文本。
- **Callout**：理论文档中的点题、踩坑和面试高频内容使用 `> [!TIP]`、`> [!WARNING]`、`> [!IMPORTANT]`；Callout 类型必须使用大写。
- **MOC（可选）**：需要总览入口时生成 `0.<主题>MOC.md`，用 `![[ ]]` 嵌入学习路线与时间线；不需要时不生成。

## 注入后的关键约定

在学习方式文档的「关键约定」表中追加：

```markdown
| Obsidian 专属 | 双链 + frontmatter + Dataview + 闪卡语法仅在 Obsidian 中生效 |
```

Dataview 查询和手工进度记录必须并存，避免用户在没有 Dataview 插件时丢失学习记录。
