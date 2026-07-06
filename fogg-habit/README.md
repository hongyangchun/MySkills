# 福格习惯教练 Skill

> 基于 BJ Fogg《福格行为模型 / Tiny Habits》构建的对话式习惯教练。

## 架构

```
fogg-habit (主入口 — 意图识别 + 路由)
├── fogg-habit-core      (基础：诊断排错 + 行为设计)
├── fogg-habit-break     (救火：戒除坏习惯)
└── fogg-habit-grow      (进阶：庆祝 + 帮别人 + 身份认同)
```

| Skill | 一句话 | 触发场景 |
|-------|--------|---------|
| `fogg-habit` | 意图识别与路由分发 | 任何习惯相关需求 |
| `fogg-habit-core` | B=MAP 诊断 → 微行为设计，个人习惯完整闭环 | 坚持不下来、从头设计新习惯 |
| `fogg-habit-break` | 反向 B=MAP：拆提示 + 加难度 + 行为顶替 | 想戒掉坏习惯 |
| `fogg-habit-grow` | 庆祝焊住情绪 → 帮别人 → 身份认同 | 做完想庆祝、帮家人/团队、身份转变 |

## KSME 速查

- **B=MAP**：行为 = 动机(Motivation) × 能力(Ability) × 提示(Prompt)
- **焦点地图**：在"影响力高 × 你做得到"里挑黄金行为
- **微行为**：砍到30秒内、几乎不需动机 — "这也太简单了吧"就对了
- **锚点配方**："在我〔现有习惯〕之后，我会〔微行为〕"
- **Shine/庆祝**：做完立即制造正面情绪，情绪创造习惯

## 安装

### 方式一：让 Agent 帮忙安装（推荐）

在你的 AI Agent 中说：

> 帮我把 https://github.com/hongyangchun/MySkills 仓库中 fogg-habit/skills/ 下的 4 个目录安装到 skills 目录，创建符号链接。

<details>
<summary>方式二：手动安装</summary>

```bash
git clone https://github.com/hongyangchun/MySkills.git

# 以 WorkBuddy 为例
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit ~/.workbuddy/skills/fogg-habit
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-core ~/.workbuddy/skills/fogg-habit-core
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-break ~/.workbuddy/skills/fogg-habit-break
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-grow ~/.workbuddy/skills/fogg-habit-grow
```
</details>

## 使用方式

直接说出需求即可触发：

| 你说的话 | 路由到 |
|----------|--------|
| "我为什么坚持不下来跑步" | `fogg-habit-core`（诊断） |
| "帮我养成早起习惯" | `fogg-habit-core`（设计） |
| "帮我戒掉熬夜刷手机" | `fogg-habit-break` |
| "做完了不知道怎么奖励" | `fogg-habit-grow` |
| "怎么帮我孩子养成收拾习惯" | `fogg-habit-grow` |
| "我好像变了个人" | `fogg-habit-grow` |

也可直接指定子 skill 名称触发。

## 核心原则

1. **B=MAP**：三者同一时刻同时出现才发生
2. **别依赖动机**：优先降低难度，不是打鸡血
3. **从微小起步**：砍到30秒内
4. **情绪创造习惯**：做完立刻庆祝
5. **没有失败，只有数据**：设计问题，不是意志力问题

## 设计特点

- **引导式对话**：一次只问一两个问题
- **温度优先**：口语化、不自责
- **多模块串联**：core → break → grow 梯度递进
- **平台无关**：纯 Markdown，不依赖特定 API

## 覆盖度

覆盖 B=MAP、能力五要素、焦点地图、微行为+锚点、庆祝/Shine、戒除坏习惯、帮别人改变、行为升级路径、习惯叠加、身份认同——约 98%。

## 与其他 Skill 的关系

| Skill | 关系 | 说明 |
|-------|------|------|
| `youjie-solve` | 衔接 | 有解第七步"拟定行动"可接 fogg-habit-core 做微行为设计 |
| `systems-thinking` | 互补 | 系统思维诊断环境结构，福格在给定环境下设计行为 |

## 参考书目

- BJ Fogg, *Tiny Habits: The Small Changes That Change Everything* (2019)
- 中文版：《福格行为模型》，徐尧 译，天津科学技术出版社

## License

MIT
