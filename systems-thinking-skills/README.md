# 系统思维 Skill 套件

基于 Donella Meadows《系统之美》（*Thinking in Systems: A Primer*）构建的系统思维引导式诊断工具。纯 Markdown，适用于任何 AI agent。

## 这是什么

一套可交互的系统思维工具箱，通过引导式提问帮助用户：

- **理清系统结构** — 识别存量与流量、反馈回路、延迟
- **诊断系统顽疾** — 匹配 8 大系统基模，找到反复出现问题的根因
- **寻找变革杠杆** — 从 12 个干预杠杆点中找到高杠杆切入点

**平台无关**：纯 Markdown 指令，不依赖任何特定工具或平台。可用于 WorkBuddy、Claude Code、Codex、Cursor、OpenCode 等任何支持 Markdown 指令文件的 AI agent。

## 架构

```
systems-thinking (主入口)
  ├── 意图识别 + 自动路由
  ├── 快速概念问答
  └── 诊断闭环指引
      │
      ├── systems-thinking-core
      │   系统结构分析
      │   存量/流量 → 反馈回路 → 延迟 → 行为模式
      │
      ├── systems-thinking-archetypes
      │   基模诊断
      │   政策阻力 | 公地悲剧 | 竞争升级 | 成功者通吃
      │   转嫁负担 | 目标侵蚀 | 规则规避 | 目标错位
      │
      └── systems-thinking-leverage
          杠杆点扫描（#12 → #1，从低到高）
          参数 → 物质流 → 缓冲器 → 延迟 → 负反馈 → 正反馈
          → 物质流路径 → 规则 → 自组织 → 目标 → 范式 → 超越范式
```

三个子模块形成**诊断闭环**：

> core（理清结构）→ archetypes（诊断顽疾）→ leverage（找切入点）→ core（验证干预效果）

## 文件结构

```
├── README.md                          ← 你在看这个
├── design/
│   └── systems-thinking-skills-design.md   ← 完整设计文档
└── skills/
    ├── systems-thinking/
    │   └── SKILL.md                   ← 主入口
    ├── systems-thinking-core/
    │   └── SKILL.md                   ← 系统基础
    ├── systems-thinking-archetypes/
    │   └── SKILL.md                   ← 基模诊断
    └── systems-thinking-leverage/
        └── SKILL.md                   ← 杠杆点分析
```

## 安装

```bash
git clone <仓库地址>
```

然后告诉你的 AI agent：

> 帮我把这个系统思维 skill 套件安装到当前环境。

agent 会根据自己所在的平台（WorkBuddy、Claude Code、Cursor 等）自动把文件放到正确位置。`skills/` 下每个目录的 `SKILL.md` 就是完整的指令文件，纯 Markdown，无需任何修改。

<details>
<summary>手动安装（可选）</summary>

如果你更愿意手动操作，核心就是把 `skills/` 下的 4 个目录放到你 agent 的指令目录中：

- **WorkBuddy / CodeBuddy** → `~/.workbuddy/skills/`
- **Claude Code** → `.claude/commands/`（文件重命名为 `.md`）
- **Cursor** → `.cursor/rules/`
- **其他 agent** → 对应的指令文件目录

文件内容是纯 Markdown，直接复制即可。
</details>

## 使用方式

安装后，在对话中自然表达即可：

| 你说的话 | 会路由到 |
|----------|----------|
| "这个问题反复出现，投入了但总反弹" | archetypes（基模诊断） |
| "帮我分析这个业务系统的结构" | core（系统基础） |
| "想从根本上改变，从哪里入手" | leverage（杠杆点分析） |
| "什么是增强回路？" | 主入口快速概念问答 |
| "帮我用系统思维分析一下" | 主入口提问澄清后路由 |

每个模块采用**引导式诊断**——不直接给答案，而是通过提问一步步引导你自己发现系统结构。

## 设计特点

- **引导式诊断**：教练式交互，通过提问引导而非灌输概念
- **可视化**：诊断过程中绘制因果回路图、存量流量图、杠杆点金字塔（使用当前环境的可用方式呈现）
- **诊断闭环**：三模块互相衔接，形成完整的分析—诊断—干预流程
- **平台无关**：纯 Markdown 指令，不依赖任何特定工具 API
- **原版案例**：保留 Meadows 书中的经典案例

## 参考书目

- Donella H. Meadows, *Thinking in Systems: A Primer* (Chelsea Green, 2008)
- 中文版：《系统之美》，邱昭良 译，浙江人民出版社

## License

MIT
