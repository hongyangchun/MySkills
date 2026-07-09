---
name: doto
description: >-
  Bob Doto《A System for Writing》Zettelkasten 笔记与写作系统主入口。
  基于 Doto 六要素、受控混乱哲学、Folgezettel ID 系统，引导用户完成捕捉→连接→写作的完整工作流。
  支持 Obsidian (filesystem) 和 Capacities (MCP)，可自行添加其他平台。
  触发词：doto、zettelkasten、卡片笔记、ZK笔记、笔记系统、写作系统、card note、slip box、a system for writing、Bob Doto
---

# Doto 写作系统

> 基于 Bob Doto《A System for Writing》(2024) 的 Zettelkasten（卡片笔记法）完整实践系统。

## 最高原则

1. **可持续性第一**：A Zettelkasten succeeds or fails based on sustainability
2. **主笔记六要素**：标题、单一想法、链接、引用来源、使用记录、唯一 ID
3. **用自己的话写**：不是复制原文，是消化后用自己的完整句子表达
4. **连接带上下文**：禁止"链接堆砌"（link dumping），每条连接必须说明为什么
5. **受控混乱**：自下而上涌现，分区标题后补，不预设层级
6. **渐进式写作**：笔记集群 → 短内容 → 博客 → 长文 → 书

---

## 平台检测（首次使用）

> "你用的笔记工具是什么？"

- **Obsidian** → 加载 `platforms/obsidian.md` 驱动
- **Capacities** → 加载 `platforms/capacities.md` 驱动
- **其他** → 参考 `platforms/PLATFORM_TEMPLATE.md` 自行创建

检测到平台后，按对应平台的初始化步骤引导用户。

---

## 三阶段概览

```
捕捉（临时/参考/主笔记）→ 连接（上下文链接+Hub+Structure）→ 写作（渐进发布+管理）
        ↑                                                    │
        └──────────── 反馈生成新想法 ←────────────────────────┘
```

---

## 意图识别与路由

| 意图信号 | 路由目标 | 典型表达 |
|----------|----------|---------|
| 记笔记/捕捉想法 | `doto-create` | "我有个想法""帮我记一下""我在读这本书""这个观点值得记" |
| 建立连接 | `doto-connect` | "这些笔记怎么连起来""找找关联""该不该建 Hub Note""这些有关系吗" |
| 写作产出 | `doto-write` | "我想写一篇""把笔记变成文章""追踪写作进度""开始写博客" |
| 质检/体检 | `doto-audit` | "帮我看看笔记合不合格""这条写得好不好""检查一下现有笔记" |
| 模糊/入门 | 提问澄清 | "什么是 ZK""doto 方法论""怎么开始""这套系统怎么用" |

### 路由规则

1. 用户带着具体操作意图 → 直接路由到对应子 skill
2. 用户表达模糊需求 → 问："你想记笔记（捕捉）、建立连接、开始写作，还是检查笔记质量？"
3. 纯粹想了解方法论 → 主入口直接回答下方速查内容
4. 首次使用 → 先做平台检测，再路由

---

## 速查：主笔记六要素

| 要素 | 说明 | 必须 |
|------|------|------|
| 1. 标题 | 一句完整的话概括想法 | ✅ |
| 2. 单一想法 | 原子化，一条笔记只说一件事 | ✅ |
| 3. 带上下文的链接 | 每条链接附说明，禁止裸链接 | ✅ 至少 1 个 |
| 4. 引用/来源 | 想法从哪来，原创/阅读/对话都标 | ✅ |
| 5. 使用记录 | 在哪篇文章里用过，可依赖 tool 的 backlinks | 推荐 |
| 6. Folgezettel ID | 唯一字母数字标识（如 `3.2a`）| ✅ |

各平台的具体实现方式见 `platforms/` 目录。

---

## 速查：Folgezettel ID 系统

```
{主题号}.{分支号}{字母延伸}

示例树:
1   (主题，标题后补)
1.1  锚定效应
  1.1a  锚定效应在定价中的应用
  1.1b  锚定效应的神经机制
1.2  确认偏误
```

- 新主题 → `{下一个可用数字}.1`
- 延伸某条 → 该 ID 后加字母
- 同主题独立想法 → 该主题下一个数字
- ID 越长（如 `7.16a1b2`），思想线越成熟

---

## 后续步骤建议

- **刚入门** → 进入 `doto-create`，先记几条主笔记，不用急着连接
- **有一定笔记了** → 进入 `doto-connect`，给新笔记建立有上下文的连接
- **笔记积累起来了** → 进入 `doto-audit` 体检模式，看看哪些合格哪些需要优化
- **想写作了** → 进入 `doto-write`，从笔记集群开始渐进式发布

---

*参考文档：`references/book-summary.md`（全书摘要）、`references/note-templates.md`（模板）、`references/checklists.md`（检查清单）、`references/glossary.md`（术语表）*

*平台支持：`platforms/obsidian.md`、`platforms/capacities.md`、`platforms/PLATFORM_TEMPLATE.md`*
