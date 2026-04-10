# PM Skill Suite 工作流总览

> 包含 20 个 PM Skill，覆盖产品管理全生命周期。
> 另有 10 条 Commands（技能链），串联多个 Skill 形成端到端工作流。

---

## 一、Skill 协同地图

```
【需求发现阶段】━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── identify-needs          ← 入口：将模糊想法转化为假设
│   ├── -> user-prioritization     假设验证优先级
│   │       └── -> interview-script     针对高风险假设设计访谈
│   │               └── -> interview-summary   从访谈提炼洞察
│   │                       └── -> identify-needs (循环: 新假设)
│   │
│   └── -> demand-prioritization-engine   高价值假设纳入需求池
│
【产品规划阶段】━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── competitive-strategy    ← 入口：竞争格局与定位分析
│   ├── -> strategy-canvas        竞争维度与 ERRC 行动
│   │       └── -> value-proposition     差异化价值主张
│   │
│   └── -> identify-needs         发现新机会假设
│
├── demand-prioritization-engine   ← 入口：需求池优先级评分
│   └── -> pm-roadmap-planner          路线图 + 里程碑
│           └── -> user-story-mapping       用户任务流 / MVP 切片
│                   ├── -> prd-writer            编写单个 PRD
│                   └── -> iteration-planning    Sprint 任务拆解
│
└── value-proposition       ← 独立：产品定位与卖点提炼
    └── -> prd-writer

【执行交付阶段】━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
│
├── prd-writer             ← 核心：PRD 编写
│   ├── -> pm-review-board        PRD 评审
│   │       └── -> prd-writer (修改循环)
│   │
│   ├── -> pm-prototype-design   原型制作
│   ├── -> tracking-spec-writer  埋点规范
│   └── -> engineering-handoff   工程交接
│           └── -> release-launch      发布流程
│                   └── -> retrospective-review   上线复盘
│                           ├── -> identify-needs
│                           └── -> pm-roadmap-planner
│
├── pm-analytics           ← 数据驱动入口
│   ├── -> pm-experiment-designer   A/B 实验设计
│   │       └── -> pm-analytics (分析循环)
│   │
│   └── -> retrospective-review     结果复盘
│
└── tracking-spec-writer   ← 埋点入口
    └── -> pm-analytics         数据分析依赖埋点规范
```

---

## 二、Commands（技能链）

### 1. /discover — 需求发现流程
**链路**：identify-needs -> user-prioritization -> interview-script -> interview-summary

用户输入模糊想法 -> 结构化假设清单 -> 假设优先级 -> 访谈提纲 -> 洞察清单 + 新假设

支持 `full / stage / lite` 模式，以及 `ideation / prioritize / interview-prep / summarize` 子模式
支持“问题型需求补充输入”，用于已有现象、数据和初步解法的优化类需求

**触发词**：`/discover [产品方向]`
**示例**：`/discover 做一个 AI 写作助手`

---

### 2. /competitive — 竞品分析流程
**链路**：competitive-strategy -> strategy-canvas -> value-proposition

用户输入竞品名单/市场 -> 竞争格局分析 -> 竞争维度曲线 + ERRC 行动 -> 差异化价值主张

**触发词**：`/competitive [市场/竞品]`
**示例**：`/competitive 在线文档工具市场`

---

### 3. /plan — 产品规划流程
**链路**：demand-prioritization-engine -> pm-roadmap-planner -> user-story-mapping -> iteration-planning

用户输入需求池/季度目标 -> 多模型优先级评分 -> 路线图与里程碑 -> 用户任务流与 MVP 切片 -> Sprint 任务拆解

支持 `full / lite / delivery` 三种模式

**触发词**：`/plan [季度目标]`
**示例**：`/plan Q2 提升用户留存`

---

### 4. /write-prd — PRD 全流程
**链路**：identify-needs -> prd-writer -> pm-review-board -> pm-prototype-design -> tracking-spec-writer -> pm-review-board

用户输入模糊需求 -> 完整 PRD 文档 -> 多角度评审 -> HTML 可交互原型 -> 埋点规范 -> 综合复评

支持 `from-idea / from-discovery / from-story-map` 三种入口模式
支持 `full / lite` 两种运行模式
如果需求效果需要数据验证，推荐后续进入 `/analyze`

**触发词**：`/write-prd [功能描述]`
**示例**：`/write-prd 做一个用户分享功能`

---

### 5. /launch — 发布全流程
**链路**：engineering-handoff -> release-launch -> retrospective-review

已确认交付范围 -> 工程交接包 -> 灰度策略 + 发布检查 + 回滚方案 -> 上线复盘 + 行动项

支持 `full / lite` 两种模式

**触发词**：`/launch [版本号/功能名]`
**示例**：`/launch v2.5.0`

---

### 6. /analyze — 数据分析流程
**链路**：pm-analytics -> pm-experiment-designer -> pm-analytics

用户输入数据问题/上传数据 -> 数据体检 + 假设推断 -> A/B 测试方案 + 止损规则 -> 实验结果分析 + 行动建议

**触发词**：`/analyze [指标问题]`
**示例**：`/analyze DAU 最近一周下降了 15%`

---

### 7. /interview — 访谈全流程
**链路**：identify-needs -> interview-script -> interview-summary

用户输入访谈目标 -> 明确关键假设 -> 结构化访谈提纲 -> 洞察提炼

**子命令**：
- `/interview prep [目标]` — 只准备访谈提纲
- `/interview summarize [记录]` — 只总结访谈

**触发词**：`/interview [目标]`
**示例**：`/interview 验证 AI 写作助手是否解决用户痛点`

---

### 8. /roadmap — 快速路线图
**链路**：demand-prioritization-engine -> pm-roadmap-planner

用户输入需求/目标 -> 快速优先级评分 -> 路线图（简化版）

**触发词**：`/roadmap [目标]`
**示例**：`/roadmap Q3 提升付费转化率`

---

### 9. /tracking-spec — 埋点规范专项
**链路**：tracking-spec-writer

用户输入功能清单/业务指标 -> 事件设计 + 参数定义 + 上报时机 + 验收标准

**触发词**：`/tracking-spec [功能/指标]`
**示例**：`/tracking-spec 新注册流程转化漏斗`

---

### 10. /story-map — 用户故事地图专项
**链路**：user-story-mapping

用户输入路线图/Epic/目标用户任务 -> 用户任务流 -> 故事拆解 -> MVP 切片 -> PRD 候选清单

**触发词**：`/story-map [Epic/目标]`
**示例**：`/story-map 用户分享能力`

---

## 三、Skill × Command 映射表

| Skill | 属于 Commands |
|-------|--------------|
| identify-needs | discover, write-prd, interview |
| user-prioritization | discover |
| interview-script | discover, interview |
| interview-summary | discover, interview |
| competitive-strategy | competitive |
| strategy-canvas | competitive |
| value-proposition | competitive |
| demand-prioritization-engine | plan, roadmap |
| pm-roadmap-planner | plan, roadmap |
| user-story-mapping | plan, story-map |
| iteration-planning | plan |
| prd-writer | write-prd |
| pm-review-board | write-prd |
| pm-prototype-design | write-prd |
| tracking-spec-writer | write-prd, tracking-spec |
| engineering-handoff | launch |
| release-launch | launch |
| retrospective-review | launch |
| pm-analytics | analyze |
| pm-experiment-designer | analyze |
