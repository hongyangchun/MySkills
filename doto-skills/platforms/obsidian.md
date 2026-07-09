# Obsidian 平台驱动

> 通过文件系统直接操作 Obsidian vault

---

## 初始化

1. 确定 Obsidian vault 的根目录路径（如 `~/Obsidian/MyVault/`）
2. 确认 vault 内有主笔记目录（建议 `{vault}/Zettels/`）
3. 确认 Daily Note 功能已开启，路径为 `{vault}/Daily/YYYY-MM-DD.md`（或你自定义的路径）

---

## 操作映射

以下操作使用当前 AI 工具的文件系统能力（Read / Write / Edit / Grep / Glob）：

| 操作 | 工具 | 写法 |
|------|------|------|
| **search** | Grep | 在 `{vault}` 目录下 `grep -rl "关键词" --include="*.md"` |
| **read** | Read | 读取 `{vault}/Zettels/{文件名}.md` |
| **create** | Write | 创建 `{vault}/Zettels/{Folgezettel ID} {标题}.md` |
| **append** | Edit | 在目标 `.md` 文件末尾追加内容（连接段落） |
| **update** | Edit | 修改目标 `.md` 文件 frontmatter |
| **quickCapture** | Edit | 追加到 `{vault}/Daily/{YYYY-MM-DD}.md` 末尾 |
| **linkSyntax** | `[[ ]]` | `[[{Folgezettel ID} {标题}]]` |
| **idProperty** | frontmatter | `id: {Folgezettel ID}` |
| **notesDir** | 目录 | `{vault}/Zettels/` |
| **getAllIds** | Glob | `ls {vault}/Zettels/*.md` 后解析 frontmatter 中的 `id` |

---

## 笔记模板

```markdown
---
id: {Folgezettel ID 如 3.2a}
created: {YYYY-MM-DD}
tags: [{标签}]
---

# {标题：一句话概括想法}

{用自己的话写的原子想法}

[[{Folgezettel ID} {相关笔记标题}]] — {上下文说明}

---
来源：{来源信息}
```

---

## 链接示例

```markdown
✅ [[1.1 锚定效应]] — 同属认知偏差，但强调的是初始信息的影响
✅ [[2.3a 写作中上下文恢复的成本]] — CLOG 就是为解决这个问题设计的
❌ [[1.1]] [[2.3a]] [[4.1]]  ← 链接堆砌，禁止
```

---

## 目录结构建议

```
{vault}/
├── Zettels/                    ← 主笔记（每条一个 .md 文件）
│   ├── 1.1 CLOG 核心价值.md
│   ├── 1.2 笔记系统的可持续性设计.md
│   ├── 2.1 锚定效应.md
│   └── 2.1a 锚定效应在定价中的应用.md
├── References/                 ← 参考笔记
│   └── 思考快与慢.md
├── Hub Notes/                  ← 枢纽笔记
├── Structure Notes/            ← 结构笔记
├── CLOG/                       ← 创意日志
└── Daily/                      ← 每日笔记
    ├── 2026-07-01.md
    └── 2026-07-02.md
```
