# MySkills

个人 WorkBuddy 技能仓库。基于经典书籍蒸馏的可交互 AI skill 套件。

## 技能目录

### 🧠 系统思维工具箱 — systems-thinking-skills (v2.0)

基于 Donella Meadows《系统之美》蒸馏的 6 个可执行 skill，按 cangjie-skill RIA++ 标准构建。

| Skill | 用途 | 来源章节 |
|-------|------|---------|
| `systems-thinking` | 主入口路由 | 全书 |
| `systems-thinking-core` | 系统结构分析（存量/流量/反馈回路） | 第1-3章 |
| `systems-thinking-archetypes` | 8大系统陷阱诊断与破解 | 第5章 |
| `systems-thinking-leverage` | 12层杠杆点扫描与干预选择 | 第6章 |
| `systems-thinking-obstacles` | 6大认知障碍诊断 | 第4章 |
| `systems-thinking-dance` | 15大生存法则 — 与系统共处 | 第7章 |

触发词：`系统思维`、`系统思考`、`反馈回路`、`系统陷阱`、`杠杆点`、`与系统共舞`

### 🎯 福格习惯教练 — fogg-habit (v2.0)

基于 BJ Fogg《福格行为模型》(Tiny Habits) 的对话式习惯教练。

| Skill | 用途 |
|-------|------|
| `fogg-habit` | 主入口路由 |
| `fogg-habit-core` | 习惯诊断与设计（B=MAP） |
| `fogg-habit-break` | 戒除坏习惯（三阶段渐进） |
| `fogg-habit-grow` | 习惯进阶（庆祝/帮别人/身份） |
| `fogg-habit-social` | 群体行为设计 |

触发词：`福格`、`Tiny Habits`、`习惯`、`戒掉`、`庆祝`

### 🔧 问题解决工具箱 — youjie-skills

基于顾淑伟《有解》KSME 问题解决7步法。

| Skill | 用途 |
|-------|------|
| `youjie` | 主入口路由 |
| `youjie-mindset` | 心智模式转换（7大转移） |
| `youjie-prepare` | 情绪准备与角色转换 |
| `youjie-solve` | 七步法完整引导 |

触发词：`有解`、`KSME`、`问题解决`、`七步法`

## 安装

将 `skills/` 目录复制到 `~/.workbuddy/skills/`。

每个 skill 包含：
- `SKILL.md` — RIA++ 六段式（R/原文 → I/自述 → A1/案例 → A2/触发 → E/执行 → B/边界）
- `test-prompts.json` — 压力测试（正面/诱饵/边界用例）

## 构建方法

所有 skill 均通过 [cangjie-skill](https://github.com/hongyangchun/MySkills) 四阶段流水线构建：
1. 阶段 0 — Adler 整书理解 (BOOK_OVERVIEW.md)
2. 阶段 1 — 5 个 agent 并行提取 (candidates/)
3. 阶段 2 — RIA++ 六段式构造
4. 阶段 3 — Zettelkasten 链接 (INDEX.md)
5. 阶段 4 — 压力测试 (test-prompts.json)
