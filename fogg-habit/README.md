# 福格习惯教练 Skill

> 基于 BJ Fogg《福格行为模型 / Tiny Habits》构建的对话式习惯教练。
> 完整覆盖全书个人习惯+群体行为设计方法论。

## 架构

```
fogg-habit (主入口 — 意图识别 + 路由)
├── fogg-habit-core      (基础：诊断排错 + 行为设计 + ABC三步骤 + 珍珠习惯)
├── fogg-habit-break     (救火：三阶段渐进戒除)
├── fogg-habit-grow      (进阶：庆祝 + 帮别人 + 身份认同 + 庆祝闪电战)
└── fogg-habit-social    (扩展：群体行为设计 + 头目/忍者 + 四分区模型)
```

| Skill | 一句话 | 触发场景 |
|-------|--------|---------|
| `fogg-habit` | 意图识别与路由分发 | 任何习惯相关需求 |
| `fogg-habit-core` | B=MAP 诊断 → 微行为设计（ABC），个人习惯完整闭环 | 坚持不下来、从头设计新习惯 |
| `fogg-habit-break` | 三阶段渐进：先建新→终止旧→替换旧 | 想戒掉坏习惯 |
| `fogg-habit-grow` | 庆祝焊住情绪 → 帮别人 → 身份认同 + 庆祝闪电战 | 做完想庆祝、帮家人、身份转变、习惯瓶颈 |
| `fogg-habit-social` | 群体行为设计 7 步 + 头目/忍者 + 四分区模型 | 帮团队/组织/家庭一起改变 |

## 速查

- **B=MAP**：行为 = 动机(Motivation) × 能力(Ability) × 提示(Prompt)
- **焦点地图**：在"影响力高 × 你做得到"里挑黄金行为
- **微行为**：砍到30秒内、几乎不需动机 — "这也太简单了吧"就对了
- **ABC 三步骤**：Anchor（锚点）→ Behavior（微行为）→ Celebration（即时庆祝）
- **Shine/庆祝**：做完立即制造正面情绪，情绪创造习惯
- **珍珠习惯**：把讨厌的事变成做好事的提示
- **顺便习惯**：利用碎片时间培养微习惯
- **庆祝闪电战**：3分钟密集庆祝，快速重建正向情绪

## 安装

### 方式一：让 Agent 帮忙安装（推荐）

在你的 AI Agent 中说：

> 帮我把 https://github.com/hongyangchun/MySkills 仓库中 fogg-habit/skills/ 下的 5 个目录安装到 skills 目录，创建符号链接。

<details>
<summary>方式二：手动安装</summary>

```bash
git clone https://github.com/hongyangchun/MySkills.git

# 以 WorkBuddy 为例
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit ~/.workbuddy/skills/fogg-habit
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-core ~/.workbuddy/skills/fogg-habit-core
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-break ~/.workbuddy/skills/fogg-habit-break
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-grow ~/.workbuddy/skills/fogg-habit-grow
ln -s /path/to/MySkills/fogg-habit/skills/fogg-habit-social ~/.workbuddy/skills/fogg-habit-social
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
| "帮团队养成站会不超时的习惯" | `fogg-habit-social` |

也可直接指定子 skill 名称触发。

## 核心原则

1. **B=MAP**：三者同一时刻同时出现才发生
2. **别依赖动机**：优先降低难度，不是打鸡血
3. **从微小起步**：砍到30秒内
4. **情绪创造习惯**：做完立刻庆祝
5. **没有失败，只有数据**：设计问题，不是意志力问题
6. **福格原则 1**：帮助人们做他们已经想做的事
7. **福格原则 2**：帮助人们感受成功

## 设计特点

- **引导式对话**：一次只问一两个问题
- **温度优先**：口语化、不自责
- **多模块串联**：core → break → grow → social 梯度递进
- **平台无关**：纯 Markdown，不依赖特定 API
- **test-prompts 质量基线**：每个 skill 配备压力测试（darwin 兼容格式）

## 覆盖度

覆盖全书核心内容：B=MAP、能力五要素、焦点地图、ABC 三步骤、微行为+锚点、庆祝/Shine、珍珠习惯、顺便习惯、庆祝闪电战、行为升级路径、习惯生长与繁殖、改变的五大技巧、三阶段渐进戒除、动机向量分析、自动化度光谱、福格两原则、群体行为设计七步流程、头目/忍者角色、四分区模型、强力区反馈框架、全套庆祝工具箱——约 95%+。

## 文档导航

| 文档 | 说明 |
|------|------|
| `BOOK_OVERVIEW.md` | 整书骨架理解、核心命题、批判分析 |
| `INDEX.md` | 技能总览、功能矩阵、引用关系图 |
| `references/` | 各模块的详细设计参考文档 |
| `references/toolkit-celebrations.md` | 100 种庆祝方式分类清单 |

## 参考书目

- BJ Fogg, *Tiny Habits: The Small Changes That Change Everything* (2019)
- 中文版：《福格行为模型》，徐尧 译，天津科学技术出版社

## License

MIT
