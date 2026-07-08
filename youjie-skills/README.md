# 有解 Skill 套件

> 基于奉湘宁、顾淑伟《有解：高效解决问题的关键7步》（人民邮电出版社，2022）

## 概述

将《有解》的 KSME 问题解决体系转化为一套可交互的引导式诊断 skill，帮助用户完整解决问题、转换心智模式、前置情绪管理。

## 架构

```
youjie (主入口 — 意图识别 + 路由)
├── youjie-prepare      (解决问题的准备：角色转换 + 情绪管理)
├── youjie-solve        (KSME 七步法完整引导)
└── youjie-mindset      (思维转换 · 理念 · 能力)
```

| Skill | 核心功能 | 触发场景 |
|-------|---------|---------|
| `youjie` | 意图识别与路由分发 | 用户面临问题、想解决问题、了解KSME |
| `youjie-prepare` | 角色转换 + 情绪管理 | 焦虑、无力、准备开始解决问题 |
| `youjie-solve` | KSME七步法完整引导 | 需要从头到尾系统解决具体问题 |
| `youjie-mindset` | 7思维转换 + 7理念 + 4能力 | 调整心智模式、提升核心能力 |

## KSME 七步法

```
A阶段（定向）              B阶段（分析）              C阶段（行动）
┌─────────────┐         ┌─────────────┐         ┌─────────────┐
│ ① 确定问题   │         │ ③ 明确现状   │         │ ⑥ 制定方案   │
│ ② 梳理关系人 │───────→ │ ④ 明确目标   │───────→ │ ⑦ 拟定行动   │
│             │         │ ⑤ 明确差距   │         │             │
└─────────────┘         └─────────────┘         └─────────────┘
```

**KSME = K(知识) + S(技能) + M(动机) + E(环境)**

## 安装

### 方式一：让 Agent 帮忙安装（推荐）

在你的 AI Agent 中说：

> 帮我把 https://github.com/hongyangchun/MySkills 仓库中 youjie-skills/skills/ 下的 4 个目录安装到 skills 目录，创建符号链接。

<details>
<summary>方式二：手动安装</summary>

```bash
# 克隆仓库
git clone https://github.com/hongyangchun/MySkills.git

# 创建符号链接（以 WorkBuddy 为例）
ln -s /path/to/MySkills/youjie-skills/skills/youjie ~/.workbuddy/skills/youjie
ln -s /path/to/MySkills/youjie-skills/skills/youjie-prepare ~/.workbuddy/skills/youjie-prepare
ln -s /path/to/MySkills/youjie-skills/skills/youjie-solve ~/.workbuddy/skills/youjie-solve
ln -s /path/to/MySkills/youjie-skills/skills/youjie-mindset ~/.workbuddy/skills/youjie-mindset
```

其他 Agent（Claude Code / Cursor / OpenCode 等）将 SKILL.md 复制到对应的 skills/commands 目录即可。
</details>

## 平台兼容性

本套件平台无关化设计，适用于：
- WorkBuddy / CodeBuddy
- Claude Code
- Cursor
- OpenCode
- 其他支持 SKILL.md 或类似机制的 AI Agent

不依赖特定平台的 API，使用中性描述（"进入对应模块"而非"调用 Skill tool"）。

## 与其他 Skill 的关系

| Skill | 关系 | 说明 |
|-------|------|------|
| `systems-thinking` | 互补 | 系统思维分析"为什么"，有解决定"怎么做" |
| `fogg-habit` | 互补 | 有解第七步"行动计划"可与福格行为模型衔接 |
| 广角思维框架 | 互补 | 其他框架做广度覆盖，有解做深度专精 |

## 文件结构

```
youjie-skills/
├── design/
│   └── youjie-skills-design.md    # 详细设计文档
├── skills/
│   ├── youjie/SKILL.md            # 主入口
│   ├── youjie-prepare/SKILL.md    # 解决问题的准备
│   ├── youjie-solve/SKILL.md      # KSME七步法引导
│   └── youjie-mindset/SKILL.md    # 思维·理念·能力
└── README.md
```

## 书籍信息

- **书名**：有解：高效解决问题的关键7步
- **作者**：奉湘宁、顾淑伟
- **出版社**：人民邮电出版社
- **出版年**：2022年5月
- **ISBN**：9787115587770
