# 《系统之美》关键概念词典 (Glossary)

> 本文档是 cangjie-skill 流水线中 **Glossary Extractor** 的产出。
> 供所有下游 skill（systems-thinking-core、systems-thinking-archetypes、systems-thinking-leverage、systems-thinking-obstacles、systems-thinking-dance）共享引用。
>
> 来源：BOOK_OVERVIEW.md + 全书文本
> 术语条目：24 条（12 条来自 BOOK_OVERVIEW + 12 条本次新增）
> 筛选标准：作者反复使用（≥3 次）、明确定义过、用法与常识不同、是核心论点的组成词

---

## 第 1 章：系统之基础

```yaml
- id: g01
  term: 系统 (System)
  type: term
  source_chapter: 第1章
  author_definition: |
    "系统并不仅仅是一些事物的简单集合，而是一个由一组相互连接的要素构成的、
    能够实现某个目标的整体。……任何一个系统都包括三种构成要件：要素、连接、功能或目标。"
  key_distinction: |
    常识中"系统"常指"一套规则或流程"（如办事系统、IT系统）。
    梅多斯强调三个要素缺一不可——缺少目标的只是集合体（如路上的一堆沙子），缺少连接的只是零件堆。
    她特别指出"整体大于部分之和"，系统的行为不能通过分解部件来理解。
  why_it_matters: |
    下游所有 skill 的起点。如果用户不区分"系统"和"一堆东西"，就无法进行结构诊断。
  tags: [term, core-concept, foundation]

- id: g02
  term: 存量 (Stock)
  type: term
  source_chapter: 第1章
  author_definition: |
    "存量是对系统中变化量的一种历史记录。"
    "存量可以在系统中起到延迟、缓存或减震器的作用。由于存量的存在，流入量和流出量可以被分离开来，相互独立。"
  key_distinction: |
    不是"库存"的商业含义。存量是对任何事情累积量的一种度量——水量、人口数、银行余额、愤怒情绪、知识储备——
    任何随时间变化而积累的事物。在工商业语境中容易被混淆为仓库存货，但梅多斯的存量概念远更抽象和通用。
  why_it_matters: |
    systems-thinking-core 中存量流量图的基础。用户需要区分"存量"和"流量"才能画系统图。
  tags: [term, core-concept, systems-thinking-core]

- id: g03
  term: 流量 (Flow)
  type: term
  source_chapter: 第1章
  author_definition: |
    "存量是对系统中变化量的一种历史记录。"（流量的定义隐含在对存量变化的描述中）
    "只要所有流入量的总和超过了流出量的总和，存量的水平就会上升。"
  key_distinction: |
    不是"数据流"或"工作流"。流量是使存量变化的速率——流入使存量增加，流出使存量减少。
    出生是人口的流入，死亡是流出。存款是账户的流入，取款是流出。流量的量纲永远包含"单位时间"。
  why_it_matters: |
    存量流量图的两个基本元素之一。不理解流量，就无法理解反馈回路如何运作。
  tags: [term, core-concept, systems-thinking-core]

- id: g04
  term: 反馈回路 (Feedback Loop)
  type: term
  source_chapter: 第1章
  author_definition: |
    "一个反馈回路就是一条闭合的因果关系链，从某一个存量出发，并根据存量当时的状况，
    经过一系列决策、规则、物理法则或者行动，影响到与存量相关的流量，又返回来改变了存量。"
  key_distinction: |
    日常用"反馈"指"意见回应"（如"请给我一些反馈"）。
    梅多斯的"反馈回路"是因果闭环——A影响B，B又反过来影响A。
    这不是直线式因果，而是循环因果。最关键的是，她强调"信息"在反馈回路中的角色——
    回路传递的是关于存量状态的信息，而非物理力量本身。
  why_it_matters: |
    反馈回路是所有系统动力学分析的原子单元。systems-thinking-core 的全部内容都围绕识别和绘制回路展开。
    用户必须从"直线因果思维"切换到"闭环因果思维"，这是系统思考的关键心智转换。
  tags: [term, core-concept, systems-thinking-core]

- id: g05
  term: 增强回路 (Reinforcing Loop)
  type: term
  source_chapter: 第1章
  author_definition: |
    "增强回路是自我强化的，随着时间的变化，增强回路会导致指数级增长或者加速崩溃。"
  key_distinction: |
    不是"正反馈=好事"。增强回路既驱动增长螺旋（复利、病毒传播、网络效应），也驱动崩溃螺旋（银行挤兑、
    生态崩溃、恐慌蔓延）。标题"脱缰的野马"精确表达了作者的态度：增强回路一旦启动就可能失控。
    标记为 R (Reinforcing)。
  why_it_matters: |
    识别增强回路是理解增长、衰退和失控的核心。systems-thinking-core 教用户区分 R 回路和 B 回路；
    systems-thinking-archetypes 中的"富者愈富"和"竞争升级"都是增强回路驱动的陷阱。
  tags: [term, core-concept, systems-thinking-core, systems-thinking-archetypes]

- id: g06
  term: 调节回路 (Balancing Loop)
  type: term
  source_chapter: 第1章
  author_definition: |
    "在系统中，调节回路是保持平衡或达到特定目标的结构，也是稳定性和抵制变革的根源。"
  key_distinction: |
    不是"负反馈=坏事"。调节回路是系统稳定的基础（体温调节、经济周期、库存管理），同时也是"变革阻力"的来源。
    当你的改革努力遇到阻力时，很可能有一个调节回路在抵抗你。
    标记为 B (Balancing)。
  why_it_matters: |
    调节回路同时是好东西（维持稳定）和坏东西（抵制变革）的根源。
    理解这一点能帮助用户避免把"阻力"归咎于人，而看到结构层面的原因。
    systems-thinking-leverage 中的杠杆点#8"调节回路"直接依赖此概念。
  tags: [term, core-concept, systems-thinking-core, systems-thinking-leverage]
```

---

## 第 2 章：系统大观园

```yaml
- id: g07
  term: 动态平衡 (Dynamic Equilibrium)
  type: term
  source_chapter: 第2章（附录系统原理概要）
  author_definition: |
    "如果所有流出量的总和与流入量的总和相等，存量的水平将保持不变，即系统将保持动态平衡。"
  key_distinction: |
    常识中的"平衡"常暗示静止、不动。但梅多斯的"动态平衡"是流动的平衡——
    流入等于流出，存量不变，但系统内部在不断流动。就像开着水龙头的浴缸，
    水面高度不变，但水在不断流入和流出。这一概念解释了很多社会现象的"不变"——
    为什么看似什么都没变，实际上很多事情在发生。
  why_it_matters: |
    systems-thinking-core 用此概念解释"为什么系统看起来没变，其实一直在变"。
    用户经常困惑于"组织架构没变但人全换了"这类现象，动态平衡提供解释框架。
  tags: [term, systems-thinking-core, system-dynamics]
```

---

## 第 3 章：系统之美——系统的 3 大特征

```yaml
- id: g08
  term: 适应力 (Resilience)
  type: term
  source_chapter: 第3章
  author_definition: |
    "如果形容一个系统，适应力指的是系统在多变的环境中保持自身的存在和运作的能力。
    与适应力相对的是脆弱性或刚性。"
    "系统之所以会有适应力，是因为系统内部结构存在很多相互影响的反馈回路，
    正是这些回路相互支撑，即使在系统遭受巨大的扰动时，仍然能够以多种不同的方式使系统恢复至原有状态。"
  key_distinction: |
    不是"弹性=恢复原状"。适应力允许系统改变形态。区别在于：弹性物体压弯后弹回原状，
    有适应力的系统可能改变形态但仍然存活。梅多斯更指出一个反常识结论：
    "一直保持恒定的系统恰恰是不具备适应力的"——看似稳定的系统反而最脆弱。
  why_it_matters: |
    所有下游 skill 的"不要追求静态稳定"的底层逻辑来源。
    systems-thinking-obstacles 专门讨论"人们为追求短期稳定而牺牲适应力"的错误。
  tags: [term, systems-thinking-core, systems-thinking-obstacles]

- id: g09
  term: 自组织 (Self-Organization)
  type: term
  source_chapter: 第3章
  author_definition: |
    "系统通常具有自组织的特性，具有塑造自身结构、生成新的结构、学习、多样化和复杂化的能力。"
  key_distinction: |
    不是"自我管理"（时间管理、自律）。自组织是结构层面的自发进化——
    系统不需要外部设计师就能产生新的结构、新的功能、新的行为模式。
    从市场自发秩序到大脑神经可塑性到开源社区涌现，都是自组织。
  why_it_matters: |
    systems-thinking-leverage 中杠杆点#4"自组织"直接基于此概念。
    自组织是撬动系统变化的强大杠杆点，因为它允许系统创造全新的结构。
  tags: [term, systems-thinking-core, systems-thinking-leverage]

- id: g10
  term: 层次性 (Hierarchy)
  type: term
  source_chapter: 第3章
  author_definition: |
    "层次自下而上地进化；上一层级的目的是服务于较低层级的目的。"
  key_distinction: |
    不是"等级制"或"组织架构图"。梅多斯的层次性是功能嵌套关系——子系统组成系统，系统嵌入更大系统。
    她特别强调"上一层的目的是为了服务低层"——这与常识中"领导指挥下属"的等级制完全相反。
    公司存在的目的是服务于员工和客户，而非反之。政府的目的是服务于公民，而非反之。
  why_it_matters: |
    重新定义"什么是为系统好"。当用户分析一个嵌套系统时，
    需要区分"系统整体目标"和"子系统目标"的冲突——这是 systems-thinking-core 的边界分析起点。
  tags: [term, systems-thinking-core, systems-thinking-obstacles]
```

---

## 第 4 章：系统之奇——系统的 6 大障碍

```yaml
- id: g11
  term: 有限理性 (Bounded Rationality)
  type: term
  source_chapter: 第4章
  author_definition: |
    "系统中每个角色的有限理性可能无法产生促进系统整体福利的决策。"
  key_distinction: |
    不是"人们不理性"。每个人都在做理性的决策，但基于自己可获得的不完整信息。
    局部理性的总和=全局灾难。这不是道德问题，是信息结构问题。
    渔民理性地多捕鱼→渔业崩溃。企业理性地降价→价格战。这是结构造就的行为，而非参与者的品德问题。
  why_it_matters: |
    这是所有系统基模的根本原因。systems-thinking-archetypes 必须以此为核心解释——
    "不是谁在害你，是结构在害所有人"。避免用户陷入"找坏人"的认知陷阱。
  tags: [term, systems-thinking-archetypes, systems-thinking-obstacles]

- id: g12
  term: 范式 (Paradigm)
  type: term
  source_chapter: 第6章（杠杆点#2）
  author_definition: |
    "社会范式：决定系统之所以为系统的心智模式"（杠杆点#2）
  key_distinction: |
    不是库恩科学革命中的"范式"。梅多斯的范式是任何系统的底层信念集合——
    关于"世界如何运作"的根深蒂固假设。比如："增长是好的""竞争带来效率""人可以征服自然"。
    这些假设很少被明确说出，但决定了系统的规则和目标。
  why_it_matters: |
    杠杆点#2（第二高）——改变范式是书中最强大的干预之一（仅次"超越范式"）。
    systems-thinking-leverage 在引导用户时，范式改变是最可能触及但最需要勇气的一步。
  tags: [term, systems-thinking-leverage]

- id: g13
  term: 时间延迟 (Time Delay)
  type: term
  source_chapter: 第4章（附录系统原理概要）
  author_definition: |
    "调节回路上的时间延迟很可能会导致系统的振荡。"
    "改变一个延迟的长短，可能会导致系统行为的巨大变化。"
    "当在反馈回路中存在较长的时间延迟时，具备一定的预见性是必不可少的。"
  key_distinction: |
    常识把"延迟"仅视为"慢"或"效率问题"。但在系统动力学中，时间延迟是行为的生成器——
    它直接导致振荡、超调和欠调。就像淋浴时转动热水龙头，管道长度（延迟）决定了你被烫还是被冻。
    延迟太长→过冲（overshoot）。延迟太短→震荡。没有延迟的系统几乎不存在。
  why_it_matters: |
    杠杆点#9"时间延迟"直接基于此概念。延迟的解释能力极强——
    供应链的牛鞭效应、房地产市场的周期、政策效果的滞后，都可追溯到时间延迟。
    用户诊断系统时，识别延迟是找到干预点的关键一步。
  tags: [term, systems-thinking-core, systems-thinking-leverage, system-dynamics]

- id: g14
  term: 非线性 (Nonlinearity)
  type: term
  source_chapter: 第4章
  author_definition: |
    "系统中的很多关系都是非线性的。"
    "这个世界是非线性的。如果为了管理的方便，非要用数学或机械式方法使其线性化，
    即使可行，也是不明智的。"
  key_distinction: |
    常识默认"多努力=多收获"的线性关系。梅多斯强调这个世界在本质上是非线性的——
    投入翻倍不一定产出翻倍，临界点前后系统行为完全不同（如温度到100℃水突然沸腾）。
    用线性思维理解非线性世界，是绝大多数"出乎意料"的根本原因。
  why_it_matters: |
    这是 systems-thinking-obstacles 的底层逻辑——六种认知障碍本质上都是
    "用线性直觉面对非线性现实"的不同表现。也解释了为什么杠杆点不是"使大劲=大效果"。
  tags: [term, systems-thinking-obstacles, systems-thinking-leverage]

- id: g15
  term: 模型 / 心智模式 (Model / Mental Model)
  type: term
  source_chapter: 第4章
  author_definition: |
    "我们认为自己所知道的关于这个世界的任何东西都只是一个模型。
    每一种语言、每一个字，都是一个模型；所有的地图、统计数据、图书、数据库、
    方程式和计算机程序，也都是模型；包括我们头脑中认知和描述世界的方式，即心智模式，也是模型。
    所有这些都不是真实的世界，永远也不可能是。"
  key_distinction: |
    常识中"模型"=数学模型或计算机模拟。梅多斯的"模型"极为宽泛——
    语言、地图、心智模式都是模型，都是对现实的简化。
    模型的精髓不在"正确与否"，而在"不能完整描绘世界"。地图≠领土。
    她特别将"心智模式"纳入模型范畴，打通了外部工具和内部认知。
  why_it_matters: |
    这是全书最重要的元认知概念。所有 skill 都在默认一个前提：
    用户描述的问题是他们的"心智模型"——不是现实本身。生存法则#2"把你的心智模式展现在阳光下"
    和杠杆点#2"范式"都基于此。systems-thinking-obstacles 的核心主题就是"你的模型不是现实"。
  tags: [term, systems-thinking-core, systems-thinking-obstacles, systems-thinking-dance]
```

---

## 第 5 章：系统之危与机——系统的 8 大陷阱与对策

```yaml
- id: g16
  term: 基模 (Archetype)
  type: term
  source_chapter: 第5章
  author_definition: |
    "我们把产生常见问题行为模式的系统结构称为'基模'（archetypes），
    诸如公地悲剧、目标侵蚀和竞争升级等。"
  key_distinction: |
    不是心理学中的"原型"或荣格的分析心理学概念。
    梅多斯的基模是系统结构的"陷阱模板"——只要结构相似，无论领域（生态、经济、组织、个人），
    就会产生相似的问题行为模式。每个基模都包含：症状描述→结构成因→破解对策。
  why_it_matters: |
    systems-thinking-archetypes 的全部内容就是"识别并破解 8 个基模"。
    用户需要理解：不是自己倒霉或别人坏，而是系统结构注定了这个结果。
  tags: [term, systems-thinking-archetypes]

- id: g17
  term: 杠杆点 (Leverage Point)
  type: term
  source_chapter: 第6章
  author_definition: |
    "在系统中的某处施加一个小的变化，就能导致系统行为发生显著的转变。"
    "杠杆点就是权柄。"
  key_distinction: |
    常识认为杠杆点在参数层面——调预算、改价格、换人。
    梅多斯指出真正的杠杆点在"高处"——改变信息流规则、自组织结构、系统目标、社会范式。
    她特别警告："人们通常凭直觉判断到哪里去寻找杠杆点，但多半是往错误的方向推动系统的变化。"
    你在底层费力（调数字），真正的杠杆在高处（改规则、改目标、改范式）。
  why_it_matters: |
    systems-thinking-leverage 基于 12 层杠杆点框架。最重要的洞察是：
    用户以为自己想改变的（数字）和最需要改变的（范式）通常不在同一层。
  tags: [term, systems-thinking-leverage]

- id: g18
  term: 信息流 (Information Flow)
  type: term
  source_chapter: 第6章（杠杆点#6）
  author_definition: |
    "信息流：谁能获得信息的结构"（杠杆点#6）
    "系统中的很多相互连接是通过信息流进行运作的。"
  key_distinction: |
    不是 IT 领域的"数据流"。梅多斯的信息流是关于"谁有权知道什么"的结构问题——
    信息的缺失或扭曲是大多数系统问题的根源。她举例说，在电表装在户外之前，居民从不关心节电；
    电表装进厨房后，节电行为立即改变。不是技术问题，是信息可达性的结构问题。
  why_it_matters: |
    杠杆点#6"信息流"是书中"投入最少、回报最大"的干预之一——
    有时只需让正确的人获得正确的信息，系统行为就会改变，不需要命令、法律或激励。
    为 systems-thinking-leverage 提供了最实用的低门槛干预方案。
  tags: [term, systems-thinking-leverage, systems-thinking-core]

- id: g19
  term: 缓冲器 (Buffer)
  type: term
  source_chapter: 第6章（杠杆点#11）
  author_definition: |
    "缓冲器：比流量力量更大、更稳定的存量"（杠杆点#11）
    "存量可以在系统中起到延迟、缓存或减震器的作用。"
  key_distinction: |
    不是 IT 技术中的"缓冲/缓存"。梅多斯的缓冲器是任何大的、稳定的存量，可以吸收冲击和波动——
    储蓄缓冲经济危机、水库缓冲旱涝、库存缓冲供应链波动、冗余缓冲系统失效。
    缓冲器的核心悖论：它能让系统更稳定，但追求效率的思维会不断压缩缓冲器（零库存、零储蓄），
    使系统变得脆弱。
  why_it_matters: |
    杠杆点#11。在效率崇拜的文化中，这个反直觉概念尤其重要——
    缓冲器被削减得越多，系统反而越脆弱。systems-thinking-leverage 需要对比：
    改变缓冲器大小（杠杆点#11）vs 改变存量-流量结构（杠杆点#10）的影响层级差异。
  tags: [term, systems-thinking-leverage, systems-thinking-core]
```

---

## 第 6 章：系统之杠杆点——系统的 12 大变革方式

```yaml
- id: g20
  term: 振荡 (Oscillation)
  type: term
  source_chapter: 第6章（附录系统原理概要）
  author_definition: |
    "调节回路上的时间延迟很可能会导致系统的振荡。"
  key_distinction: |
    常识中"振荡"可能被视为"波动/不稳定"。但在系统动力学中，振荡是一种特定的行为模式——
    系统存量围绕目标值上下摆动，由调节回路中的时间延迟造成。
    振荡不等于系统失灵——很多健康系统（捕食者-猎物、经济周期）天然会振荡。
    区别在于：健康的振荡是有限度的，失控的振荡（如银行挤兑）会导致崩溃。
  why_it_matters: |
    systems-thinking-core 中"系统行为模式识别"的关键概念——
    帮用户判断振荡是正常现象还是危险信号。systems-thinking-obstacles 中
    "因为延迟产生的振荡被误读为危机"是一个常见认知陷阱。
  tags: [term, systems-thinking-core, systems-thinking-obstacles, system-dynamics]

- id: g21
  term: 系统边界 (System Boundary)
  type: term
  source_chapter: 第4章
  author_definition: |
    "世界是普遍联系的，不存在孤立的系统；如何确定系统的边界，取决于你的分析目的。"
  key_distinction: |
    不是物理边界或组织边界。梅多斯强调边界是"画"出来的——它取决于分析目的，而非客观存在。
    一个人、一家公司、一个行业都不是天然孤立的系统，边界是我们为了理解而人为设定的。
    画错边界是最常见的认知错误之一：经济学家只看市场不看环境，企业只看利润不看员工。
  why_it_matters: |
    这是 systems-thinking-core 的第一步——定义分析范围。
    边界画错则整个分析偏掉。systems-thinking-obstacles 将"恰当地划定边界"列为六大障碍之一。
  tags: [term, systems-thinking-core, systems-thinking-obstacles]

- id: g22
  term: 限制因素 (Limiting Factor)
  type: term
  source_chapter: 第4章
  author_definition: |
    "在任何给定的时间，对于系统来说，最重要的一项输入是限制最大的那个因素。"
    "任何有着多重输入和输出的物质实体，都受到多重限制因素的制约。"
    "任何成长都存在限制。"
  key_distinction: |
    不是"问题"或"缺点"。梅多斯的限制因素是一个精确的系统概念——
    当多个条件都必需时，最短缺的那个决定了系统能走多远（李比希最小因子定律）。
    限制因素会随系统的成长而变化——今天最缺钱，明天可能最缺人，后天可能最缺时间。
    关键洞察：解决当前限制因素，下一个限制因素自动浮现。
  why_it_matters: |
    用户经常困惑"为什么解决了A，问题变成了B"。限制因素解释了这种"问题转移"。
    systems-thinking-core 用它解释系统成长的阶段性特征。
    systems-thinking-archetypes 中的"转嫁负担"和"目标侵蚀"都与限制因素的误判有关。
  tags: [term, systems-thinking-core, systems-thinking-obstacles]

- id: g23
  term: 主导地位转换 (Shifting Dominance / Loop Dominance)
  type: term
  source_chapter: 第6章（附录系统原理概要）
  author_definition: |
    "当不同调节回路的相对优势发生改变时，系统通常会出现一些复杂的行为，
    由一个回路主导的某种行为模式变为另外一种。"
  key_distinction: |
    这不是"谁权力大"的问题，是纯结构性的概念——
    一个系统中有多个回路，但某一时刻只有其中一个"主导"系统行为。
    当主导权切换时，系统看起来会"突然改变行为模式"，即便没有任何新事件发生。
    比如人口系统：出生率高于死亡率时增强回路主导（增长），两者相等时调节回路主导（稳定）。
    这个转换是内生的、自动的、非线性的。
  why_it_matters: |
    系统动力学的核心概念，解释系统行为的"阶段转换"（phase transition）。
    systems-thinking-core 用它解释"为什么系统会突然从增长模式切换到停滞模式"。
    systems-thinking-leverage 用它评估"哪个回路是当前的主导者，哪个是我们想推动的"。
  tags: [term, systems-thinking-core, system-dynamics]

- id: g24
  term: 与系统共舞 (Dancing with Systems)
  type: term
  source_chapter: 第7章
  author_definition: |
    "未来是不可预测的，但它可以被想象，并在人们的脑海中栩栩如生、呼之欲出；
    系统不可以被控制，但它们可以被设计和重构。"
  key_distinction: |
    这不是"放任自流"或"随波逐流"。梅多斯的"共舞"是一种有意识的参与姿态——
    放弃控制的幻觉（你控制不了系统），但保持主动的设计和调整（你可以影响系统）。
    15 大生存法则构成了"共舞"的具体操作手册：
    从"跟上系统的节拍"到"把你的心智模式展现在阳光下"，从"追求整体利益"到"不要降低善的标准"。
    这不是被动，而是一种比"控制"更高级的介入方式。
  why_it_matters: |
    全书世界观升华的关键术语。下游 skill 的最高指导原则——
    systems-thinking-dance 技能的命名来源和全部内容。
    它告诫所有 skill 的用户：你不可能"解决"系统问题，只能学会与系统相处。
  tags: [term, systems-thinking-dance, philosophy]
```

---

## 自检记录

| # | 检查项 | 状态 |
|---|--------|------|
| 1 | BOOK_OVERVIEW 原有的 12 条术语均已纳入（g01-g06, g08-g12, g16-g17）| 通过 |
| 2 | 新增 12 条术语均满足：出现 ≥3 次、作者明确定义、用法与常识不同 | 通过 |
| 3 | 系统动力学特有术语已覆盖：动态平衡、主导地位转换、时间延迟、振荡 | 通过 |
| 4 | 容易被误解的术语已覆盖：模型、层次性、信息流、缓冲器 | 通过 |
| 5 | 第7章关键术语已覆盖："与系统共舞" | 通过 |
| 6 | author_definition 尽可能使用书中原文 | 通过 |
| 7 | key_distinction 说明与常识用法的差异 | 通过 |
| 8 | why_it_matters 连接到下游 skill | 通过 |
| 9 | tags 标注了适用的 skill 名称 | 通过 |
| 10 | 总计 24 条（12 继承 + 12 新增），在 20-32 范围内 | 通过 |

## 术语覆盖矩阵

| 术语 | 对应章节 | 对应下游 Skill |
|------|---------|----------------|
| g01 系统 | 第1章 | 全部 |
| g02 存量 | 第1章 | core |
| g03 流量 | 第1章 | core |
| g04 反馈回路 | 第1章 | core |
| g05 增强回路 | 第1章 | core, archetypes |
| g06 调节回路 | 第1章 | core, leverage |
| g07 动态平衡 | 第2章 | core |
| g08 适应力 | 第3章 | core, obstacles |
| g09 自组织 | 第3章 | core, leverage |
| g10 层次性 | 第3章 | core, obstacles |
| g11 有限理性 | 第4章 | archetypes, obstacles |
| g12 范式 | 第6章 | leverage |
| g13 时间延迟 | 第4章 | core, leverage |
| g14 非线性 | 第4章 | obstacles, leverage |
| g15 模型/心智模式 | 第4章 | core, obstacles, dance |
| g16 基模 | 第5章 | archetypes |
| g17 杠杆点 | 第6章 | leverage |
| g18 信息流 | 第6章 | leverage, core |
| g19 缓冲器 | 第6章 | leverage, core |
| g20 振荡 | 第6章 | core, obstacles |
| g21 系统边界 | 第4章 | core, obstacles |
| g22 限制因素 | 第4章 | core, obstacles |
| g23 主导地位转换 | 第6章 | core |
| g24 与系统共舞 | 第7章 | dance |
