# Doto Skills — Zettelkasten Writing System

> 基于 Bob Doto《A System for Writing》(2024) 的 Zettelkasten（卡片笔记法）AI 辅助技能套件。
> 支持 Obsidian、Capacities，可自行扩展其他平台。

## 这是什么

Doto Skills 是一套 AI 辅助的 Zettelkasten 方法论实践系统。它把 Bob Doto 书中的捕捉→连接→写作完整工作流，转化为 AI agent 可以直接执行的技能指令。

**平台无关** —— 方法论核心不变，平台操作通过 `platforms/` 目录下的驱动文件适配。目前支持：

| 平台 | 方式 | 说明 |
|------|------|------|
| **Obsidian** | filesystem | 直接读写 vault 中的 `.md` 文件 |
| **Capacities** | MCP | 通过 Capacities MCP 协议操作 Pro 空间 |
| **你的工具** | 自定义 | 复制 `platforms/PLATFORM_TEMPLATE.md`，10 分钟适配 |

## 架构

```
doto/                         主入口（平台检测 + 路由）
├── platforms/                    平台驱动（每个平台一个文件）
│   ├── PLATFORM_TEMPLATE.md      新增平台模板
│   ├── obsidian.md                Obsidian 操作映射
│   └── capacities.md              Capacities MCP 操作映射
├── skills/
│   ├── doto-create/              笔记创建流水线（临时/参考/主笔记）
│   ├── doto-connect/             连接思想（6 种连接类型 + Hub/Structure Note）
│   ├── doto-write/               渐进式写作（8 步工作流 + CLOG 管理）
│   └── doto-audit/               质检与体检（双模式）
└── references/
    ├── book-summary.md           全书摘要
    ├── note-templates.md         各平台笔记模板
    ├── checklists.md             检查清单汇总
    └── glossary.md               中英术语表
```

## 核心方法论

### Doto 六要素
每条主笔记（Zettel）必须包含：
1. **标题** — 一句完整的话概括想法
2. **单一想法** — 原子化，一条笔记只说一件事
3. **带上下文的链接** — 禁止"链接堆砌"
4. **引用来源** — 想法从哪来
5. **使用记录** — 在哪篇文章里用过
6. **Folgezettel ID** — 唯一字母数字标识（如 `3.2a`）

### 三阶段工作流
```
捕捉（临时/参考/主笔记）→ 连接（上下文链接 + Hub/Structure）→ 写作（渐进发布 + 管理）
```

## 安装

### WorkBuddy / CodeBuddy

```bash
git clone https://github.com/hongyangchun/doto-skills.git ~/.workbuddy/skills/doto
```

在 WorkBuddy 中说 `doto` 触发。首次使用会自动检测平台（Obsidian / Capacities / 其他）。

### 其他 AI 工具

将 `doto/` 目录复制到对应工具的 skills 目录即可。

## 添加新平台

1. 复制 `platforms/PLATFORM_TEMPLATE.md`
2. 填入你的笔记工具的 10 个操作映射（search / read / create / append 等）
3. 在 `references/note-templates.md` 尾部添加该平台的笔记模板
4. 发 PR 或自行使用

## 与其他 ZK 文献的关系

| 来源 | 特点 |
|------|------|
| Sönke Ahrens *How to Take Smart Notes* | 偏理论，介绍 ZK 的"为什么" |
| **Bob Doto *A System for Writing*** | **偏实操，回答"怎么做"，本套件来源** |

Doto 的独特贡献：六要素精确清单、批注前置、受控混乱哲学、CLOG 写作管理。

## 许可证

MIT
