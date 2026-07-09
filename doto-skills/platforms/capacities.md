# Capacities 平台驱动

> 通过 Capacities MCP 协议操作 Capacities Pro 空间

---

## 初始化

1. 确认 Capacities Pro 订阅有效
2. 配置 MCP 连接：`{ "url": "https://api.capacities.io/mcp" }` 并完成 OAuth 授权
3. 确认以下对象类型已创建：Zettels（需 `id` 属性，Text 类型）、Fleeting Notes、Reference Notes
4. 可选：Hub Notes、Structure Notes、CLOG

---

## 操作映射

以下操作使用 Capacities MCP 工具：

| 操作 | 工具 | 写法 |
|------|------|------|
| **search** | MCP `search` | `search("关键词", objectType="Zettels")` |
| **read** | MCP `getObjectContent` | `getObjectContent(objectId)` |
| **create** | MCP `createObjectViaMd` | 带 frontmatter 的 Markdown，objectType=Zettels |
| **append** | MCP `appendMdToObject` | `appendMdToObject(objectId, "追加内容")` |
| **update** | MCP `updateObjectViaMD` | 更新 frontmatter 中的属性 |
| **quickCapture** | MCP `saveToDailyNote` | `saveToDailyNote("速记内容")` |
| **linkSyntax** | `@[title](url)` | `@[{标题}]({对象URL})` |
| **idProperty** | 对象属性 | `id: {Folgezettel ID}`（需先在 Capacities 里创建此属性） |
| **notesDir** | 对象类型 | Zettels（对象类型名称） |
| **getAllIds** | MCP `search` + `getObjectContent` | 多次 search 汇总后读取各条笔记的 `id` 属性 |

---

## 笔记模板

```
---
objectType: Zettels
id: {Folgezettel ID 如 3.2a}
---

# {标题：一句话概括想法}

{用自己的话写的原子想法}

@[{相关Zettel标题}]({对象URL}) — {上下文说明}

---
来源：{来源信息}
时间：{YYYY-MM-DD}
```

---

## 链接示例

```markdown
✅ @[锚定效应](capacities://...) — 同属认知偏差，但强调的是初始信息的影响
✅ @[写作的上下文恢复成本](capacities://...) — CLOG 就是为解决这个问题设计的
❌ @[锚定效应] @[确认偏误] @[可得性启发]  ← 链接堆砌，禁止
```

---

## 对象类型体系

| 对象类型 | 角色 | 对应 Doto 概念 |
|----------|------|---------------|
| Zettels | 主笔记 | Zettel（原子化想法） |
| Fleeting Notes | 临时笔记 | Fleeting Note |
| Reference Notes | 参考笔记 | Reference Note |
| Daily Note | 收件箱 + 日记 | Daily Note / Inbox |
| Hub Notes | 枢纽笔记 | Hub Note |
| Structure Notes | 结构笔记 | Structure Note |
| CLOG | 创意日志 | CLOG |
