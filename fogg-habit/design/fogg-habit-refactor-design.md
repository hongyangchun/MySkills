# fogg-habit 重构设计文档

> 将当前 1 个 SKILL.md + 6 个 reference 文件的架构，重构为 1 主入口 + 3 子 skill，与 systems-thinking 和 youjie 套件保持一致。

## 一、当前状态

```
fogg-habit/
├── SKILL.md                     # 主入口：意图识别 + 5条最高原则 + 6模式路由表
└── references/
    ├── diagnose.md              # 诊断排错模式
    ├── design.md                # 行为设计模式（含行为升级路径 + 习惯叠加）
    ├── break-habit.md           # 戒除坏习惯模式
    ├── celebrate.md             # 庆祝设计模式
    ├── help-others.md           # 帮别人改变模式
    └── identity.md              # 身份认同模式
```

**问题**：
- 6 个模式只能通过主入口路由进入，不能独立触发
- 架构与其他两套（1主+3子）不一致
- 每个 reference 已经具备独立 skill 所需的完整内容，只是"身份"上是 reference 而非 SKILL.md

## 二、重构目标

### 合并逻辑

6 个 reference → 3 个子 skill，对应《福格行为模型》三个层次：

| 层次 | 子 skill | 合并来源 | 一句话 |
|------|---------|---------|--------|
| 基础 | `fogg-habit-core` | diagnose + design | 诊断 + 设计：个人习惯的完整闭环——"为什么不行"到"怎么才行" |
| 救火 | `fogg-habit-break` | break-habit | 戒除：反向 B=MAP + 顶替策略 |
| 进阶 | `fogg-habit-grow` | celebrate + help-others + identity | 庆祝焊住情绪 → 帮别人是外延 → 身份是终局 |

**为什么 diagnose 和 design 要合并？** 书的核心论点是"坚持不下来不是意志力问题，是设计问题"——诊断的终点就是重设计的起点，分开反而割裂了这个因果链。

**为什么 celebrate、help-others、identity 合并？** 三者都不是独立入口场景：庆祝是 design 流程的一步，帮别人需要先掌握基础方法论，身份认同是习惯养成到一定阶段的自然产物。合并后作为"进阶模块"，与 core 形成梯度。

### 目标架构

```
fogg-habit/
├── skills/
│   ├── fogg-habit/SKILL.md           # 主入口（精简为纯路由）
│   ├── fogg-habit-core/SKILL.md      # 诊断 + 设计（基础）
│   ├── fogg-habit-break/SKILL.md     # 戒除坏习惯（救火）
│   └── fogg-habit-grow/SKILL.md      # 庆祝 + 帮别人 + 身份（进阶）
├── references/                       # 保留，子 skill 的详细备份
│   ├── diagnose.md
│   ├── design.md
│   ├── break-habit.md
│   ├── celebrate.md
│   ├── help-others.md
│   └── identity.md
├── design/
│   └── fogg-habit-refactor-design.md # 本文档
└── README.md
```

### 三重触发

每个子 skill 都可用三种方式进入：
1. **主入口路由** — 用户说"帮我养成习惯"，`fogg-habit` 识别意图后分发到对应子 skill
2. **独立触发** — 用户直接喊"我坚持不下来跑步"，`fogg-habit-core` 直接被匹配
3. **内部串联** — core 的庆祝步骤自然引到 grow，戒除中的顶替行为设计引回 core

## 三、各子 skill 详细设计

### 3.1 `fogg-habit` — 主入口

| 项目 | 内容 |
|------|------|
| **一句话** | 福格行为模型教练：意图识别 + 路由分发 |
| **触发词** | 福格、福格行为模型、Tiny Habits、微习惯、B=MAP、行为设计、习惯教练、/fogg-habit |
| **核心职责** | 识别意图 → 路由。不承载具体引导逻辑 |

**路由规则**：

| 意图信号 | 路由目标 | 典型表达 |
|----------|----------|---------|
| 基础（诊断/设计） | `fogg-habit-core` | "坚持不下来""帮我养成""怎么开始""又断了" |
| 戒除 | `fogg-habit-break` | "帮我戒掉""忍不住""想停掉""改不掉" |
| 进阶 | `fogg-habit-grow` | "怎么庆祝""怎么帮别人""身份认同""我好像变了" |
| 模糊/学习 | 提问澄清 | "福格模型是什么""B=MAP什么意思" |

**精简内容**：
- 5 条最高原则保留（所有子 skill 共同依赖）
- B=MAP 速查保留
- 模式路由表改为 3 路（原 6 路合并为 3 路）

**与其他 skill 的关系**：

| skill | 关系 | 说明 |
|-------|------|------|
| `youjie-solve` | 衔接 | 有解第七步"拟定行动"可接 fogg-habit 做微行为设计 |
| `systems-thinking` | 互补 | 系统思维诊断"环境结构"，福格在给定环境下设计行为 |

### 3.2 `fogg-habit-core` — 基础：诊断 + 设计

| 项目 | 内容 |
|------|------|
| **一句话** | B=MAP 诊断排错 → 微行为设计，个人习惯的完整闭环 |
| **触发词** | 坚持不下来、断掉、帮我养成、怎么开始、Tiny Habit、行为设计、习惯断了 |
| **来源** | `references/diagnose.md` + `references/design.md` 合并 |
| **核心流程** | 阶段一诊断：还原现场 → 查提示 → 查能力（五要素）→ 最后查动机 → 给结论。阶段二重设计：厘清愿望 → 行为群 → 焦点地图 → 微行为（砍到30秒）→ 锚点（"在我XX之后，我就XX"）→ 庆祝 → 升级 → 叠加 |
| **串联** | 阶段一的诊断结论如果指向设计问题，内部自动进入阶段二；庆祝步骤可引向 `fogg-habit-grow` |

**结构设计**（约 2000 字）：

```
# B=MAP 诊断 + 行为设计

## 阶段一：诊断 — 为什么没坚持下来
 [从 diagnose.md 精简，保留核心流程]

## 阶段二：重设计 — 从愿望到习惯
 [从 design.md 精简，保留核心流程]

## 两阶段衔接
 所有"坚持不下来"的根因最终都落到重设计。
 "不是你的错，是设计问题"贯穿全程。
```

### 3.3 `fogg-habit-break` — 戒除坏习惯

| 项目 | 内容 |
|------|------|
| **一句话** | 反向 B=MAP：拆提示、加难度、用新行为顶替 |
| **触发词** | 戒掉、改掉、忍不住、改不掉的、想停掉、坏习惯、刷手机停不下来 |
| **来源** | `references/break-habit.md` 直接转换 |
| **核心流程** | 1 把"一团坏习惯"拆成具体行为 → 2 对每个行为反向操作 B=MAP → 3 设计顶替行为 → 4 逐个击破 |
| **串联** | 顶替行为的设计可引回 `fogg-habit-core` |

**改动点**：添加 frontmatter，跨引用改为模块名。

### 3.4 `fogg-habit-grow` — 进阶：庆祝 + 帮别人 + 身份

| 项目 | 内容 |
|------|------|
| **一句话** | 从"做到"到"成为"——庆祝焊住情绪、帮别人是外延、身份是终局 |
| **触发词** | 庆祝、怎么奖励、Shine、帮别人、身份认同、我好像变了、怎么让它扎根 |
| **来源** | `references/celebrate.md` + `references/help-others.md` + `references/identity.md` 合并 |
| **核心流程** | 模块一庆祝：Shine 方法 → 建立庆祝菜单 → 场景匹配。模块二帮别人：调整心态 → 让对方觉得是自己想做的 → 设计微小成功。模块三身份：识别身份信号 → 命名新身份 → 用身份锚定行为 |
| **串联** | 通常由 core 引过来（庆祝步骤），也可独立进入 |

**结构设计**（约 1500 字）：

```
# 进阶：庆祝 · 帮别人 · 身份

## 模块一：庆祝 — 情绪焊住习惯
 [从 celebrate.md 精简]

## 模块二：帮别人改变
 [从 help-others.md 精简]

## 模块三：身份认同 — 从"做"到"是"
 [从 identity.md 精简]

## 进阶路线
 core(基础) → break(救火) → grow(进阶)
 庆祝是习惯的"焊点"，帮别人是能力的"外延"，身份是终局"锚点"
```

## 四、改动总结

| 项目 | 当前 | 重构后 |
|------|------|--------|
| SKILL.md 数量 | 1 | 4（1主+3子） |
| 独立触发 | 不支持 | 每个子 skill 都能独立触发 |
| 主入口大小 | ~2KB | ~1KB（精简为纯路由） |
| reference 文件 | 6个，内容完整 | 保留不动，作为子 skill 的详细备份 |
| 符号链接 | 1个 | 4个 |
| 架构一致性 | 独有 | 与 systems-thinking、youjie 统一（均为 1+3） |

## 五、权衡与风险

### 优点
- 三套 skills 架构完全统一，用户心智模型一致
- 子 skill 粒度适中——3 个比 6 个好记，不碎片化
- diagnose 和 design 合并后，诊断→重设计无缝衔接，符合原书逻辑
- celebrate/help/identity 合并为 grow，不稀释边界清晰的 core 和 break

### 风险
- reference 和 SKILL.md 之间可能出现内容不同步（但 reference 不改，SKILL.md 是精简升级版）
- 3 个子 skill 的维护成本比 1 个高（但比 6 个低很多）

### 建议
- reference 文件不动，SKILL.md 头部注明"详细版本见 `references/xxx.md`"
- 5 条最高原则保留在主入口，各子 skill 只需简要引用
- grow 的三模块间用 `---` 分隔，各自独立可跳读

## 六、实施计划

1. 创建 3 个子 skill 的目录和 SKILL.md（从 reference 文件合并/转换）
2. 精简主入口 SKILL.md（去掉模式引导细节，路由从 6 路改 3 路）
3. 更新各子 skill 中的跨引用（"读 xxx.md" → "进入 fogg-habit-xxx"）
4. 更新原有 1 个符号链接 + 新建 3 个，共 4 个符号链接
5. 更新 README.md
6. 推送到 GitHub
