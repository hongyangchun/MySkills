# 笔记模板汇总

> 各平台的主笔记、参考笔记、组织笔记模板

---

## Obsidian（文件系统）

### 主笔记（Zettel）

文件命名：`{Folgezettel ID} {标题}.md`，存放在 `{vault}/Zettels/`

```markdown
---
id: {Folgezettel ID 如 3.2a}
created: {YYYY-MM-DD}
tags: [{标签}]
---

# {标题：一句完整的话概括这个想法}

{用自己的话写的原子想法。可以是 2-5 句，但只包含一个核心观点。}

[[{Folgezettel ID} {相关笔记标题}]] — {连接上下文：为什么连接}

---
来源：{原创/书名(作者,年份) p.页码/对话/观察}
```

### 临时笔记

存放于 Daily Note 中（`{vault}/Daily/YYYY-MM-DD.md`）：

```markdown
💡 {一句话想法}
```

### 参考笔记

存放在 `{vault}/References/`：

```markdown
---
author: {作者}
reading_date: {YYYY-MM-DD}
---

# {书名/文章名}

## 总体印象
{这本书/文章的整体评价，一两句话}

---

### {页码/章节} — {话题关键词}
> {原文引用}

**批注**：{为什么这段重要？你同意/不同意？和哪些已有想法相关？}
```

### 枢纽笔记

存放在 `{vault}/Hub Notes/`：

```markdown
# {主题名} — 枢纽笔记

## 起点分支
- [[{ID} {标题}]] — {一句话说明}
- [[{ID} {标题}]] — {一句话说明}

## 深入分支
- [[{ID} {标题}]] — {一句话说明}
  - [[{ID} {标题}]] — 延伸
  - [[{ID} {标题}]] — 质疑

## 相关主题
- [[Hub Note标题]]
```

### 结构笔记

存放在 `{vault}/Structure Notes/`：

```markdown
# {文章/章节标题} — 结构笔记

## 核心论点
{一句话你想论证什么}

## 论点 1：{子标题}
- [[{ID} {标题}]] — {在论证中的作用}
- [[{ID} {标题}]] — {补充视角}

## 论证缺口
- {需要补充的案例}
- {需要回应的反驳}

## 写作顺序建议
1. {先写什么，理由}
2. {再写什么}
```

### CLOG

存放在 `{vault}/CLOG/`：

```markdown
---
project: {项目名}
---

## 本次完成
- {具体做了什么}

## 待处理
- {接下来要做的}

## 下次开始建议
- {一句话，下次打开就知道从哪继续}
```

---

## Capacities（MCP）

### 主笔记（Zettel）

```
---
objectType: Zettels
id: {Folgezettel ID}
---

# {标题：一句完整的话概括这个想法}

{用自己的话写的原子想法}

@[{相关Zettel标题}]({相关Zettel对象URL}) — {连接上下文}

---
来源：{来源信息}
时间：{YYYY-MM-DD}
```

### 临时笔记

```
---
objectType: Fleeting Notes
---

# {一句话描述}

{具体内容}
```

或通过 quickCapture（`saveToDailyNote`）：

```
💡 {一句话想法}
```

### 参考笔记

```
---
objectType: Reference Notes
author: {作者}
reading_date: {YYYY-MM-DD}
---

# {书名/文章名}

## 总体印象

---

### {页码/章节} — {话题关键词}
> {原文引用}

**批注**：{为什么这段重要？}
```

### 枢纽笔记

```
---
objectType: Hub Notes
---

# {主题名} — 枢纽笔记

## 起点分支
- @[{Zettel标题}]({URL}) ({ID}) — {一句话说明}
```

### 结构笔记

```
---
objectType: Structure Notes
---

# {文章标题} — 结构笔记

## 核心论点

## 论点 1：{子标题}
- @[{Zettel标题}]({URL}) ({ID}) — {在论证中的作用}
```

### CLOG

```
---
objectType: CLOG
project: {项目名}
---

## 本次完成

## 下次开始建议
```

---

## 添加新平台

参考 `platforms/PLATFORM_TEMPLATE.md`，为你的平台编写笔记模板格式，然后发 PR 或自行扩展本节。
