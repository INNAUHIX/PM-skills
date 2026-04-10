# PM Skills Suite

产品经理技能套件，覆盖产品管理全生命周期。

## 包含 Skills（20个）

### 需求发现（01-需求发现）
| Skill | 描述 |
|-------|------|
| pm-identify-needs | 需求发现与定义 |
| pm-user-prioritization | 用户优先级排序 |
| pm-interview-script | 访谈脚本生成 |
| pm-interview-summary | 访谈总结 |
| pm-competitive-strategy | 竞品策略分析 |
| pm-strategy-canvas | 战略画布 |
| pm-value-proposition | 价值主张 |

### 产品规划（02-产品层）
| Skill | 描述 |
|-------|------|
| pm-demand-prioritization-engine | 需求优先级引擎 |
| pm-roadmap-planner | 路线图规划 |
| pm-user-story-mapping | 用户故事地图 |
| pm-prd-writer | PRD 编写 |
| pm-review-board | PRD 评审 |

### 执行交付（03-执行交付）
| Skill | 描述 |
|-------|------|
| pm-prototype-design | 原型设计 |
| pm-tracking-spec-writer | 埋点规范编写 |
| pm-engineering-handoff | 工程交接 |
| pm-release-launch | 发布上线 |
| pm-iteration-planning | 迭代规划 |
| pm-retrospective-review | 迭代复盘 |

### 数据与增长
| Skill | 描述 |
|-------|------|
| pm-analytics | 数据分析 |
| pm-experiment-designer | 实验设计（A/B测试） |

## 使用方法

将这些 Skill 复制到 `~/.qclaw/skills/` 目录下即可使用。

```bash
# 复制所有 skills
cp -r pm-* ~/.qclaw/skills/
```

## 目录结构

```
PM-skills/
├── .claude-plugin/          # Claude Code Commands
├── 01-需求发现/             # 需求发现阶段
├── 02-产品层/               # 产品规划阶段
├── 03-执行交付/             # 执行交付阶段
├── pm-analytics/           # 数据分析
├── pm-competitive-strategy/
├── pm-demand-prioritization-engine/
├── pm-engineering-handoff/
├── pm-experiment-designer/
├── pm-identify-needs/
├── pm-interview-script/
├── pm-interview-summary/
├── pm-iteration-planning/
├── pm-prd-writer/
├── pm-prototype-design/
├── pm-release-launch/
├── pm-retrospective-review/
├── pm-review-board/
├── pm-roadmap-planner/
├── pm-strategy-canvas/
├── pm-tracking-spec-writer/
├── pm-user-prioritization/
├── pm-user-story-mapping/
├── pm-value-proposition/
├── SKILL_WORKFLOWS.md
└── COMMAND_IO_CONTRACTS.md
```

## 与 QClaw 集成

这些 Skills 适配 QClaw Agent 系统，可在 QClaw 中直接使用。

---

MIT License
