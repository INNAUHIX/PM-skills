---
name: write-prd
description: 支持模糊需求、discovery 输出和 story map 输出三种入口的 PRD 链路
skills:
  - identify-needs
  - prd-writer
  - pm-review-board
  - pm-prototype-design
  - tracking-spec-writer
  - pm-review-board
---

# /write-prd — PRD 全流程

从模糊需求或上游结构化输入出发，编写 PRD → 多角度评审 → 原型验证 → 埋点补全 → 评审通过。

## 入口模式

- `from-idea`：从模糊需求开始，包含 `identify-needs`
- `from-discovery`：直接消费 discovery 输出，跳过重复抽象
- `from-story-map`：直接消费 story map 输出，聚焦单个 MVP 切片

## 运行模式

- `full`：完整 PRD + 原型 + 埋点 + 双轮评审
- `lite`：轻量 PRD + 关键验收标准 + 核心埋点

### 模式选择建议

| 当前场景 | 推荐模式 | 原因 |
|---------|---------|------|
| 单页面/单入口小功能 | `lite` | 降低文档和评审成本 |
| 多角色/多状态/多依赖需求 | `full` | 需要完整交付链 |
| 已有故事地图切片 | `from-story-map` + `lite/full` | 按切片写，不写总 PRD |
| 企业复杂系统 | `full` | 原型、埋点、风险都不能省 |

## 跳步规则

- 如果用户已经提供“已验证假设 + 目标 + 成功指标”，跳过 `identify-needs`
- 如果用户已经提供 PRD 草稿，只做评审、原型和埋点补全
- 如果用户只想做原型或埋点，不强制重写整份 PRD
- `lite` 模式下不强制输出完整原型，可降级为关键页面草图或交互说明
- `lite` 模式下埋点只要求关键事件，不要求完整埋点文档

## 使用场景

当你有功能需求，需要写一份完整、可评审的 PRD 时使用：
- `帮我写一个 PRD`
- `这个功能怎么写需求文档`
- `做一个 XX 功能的需求文档`
- `根据 discovery 结果写 PRD`
- `根据故事地图写某个 MVP 的 PRD`
- `这个功能不复杂，先给我一个轻量 PRD`

## Skill 链路

1. **identify-needs** — 将需求方向转化为结构化假设（仅 `from-idea` 使用）
2. **prd-writer** — 生成完整 PRD（含功能、流程、异常、数据字典）
3. **pm-review-board** — 第一轮评审：检查 PRD 完整性、边界、验收口径
4. **pm-prototype-design** — 将 PRD 转化为可交互 HTML 原型
5. **tracking-spec-writer** — 为关键流程补充埋点规范
6. **pm-review-board** — 第二轮评审：结合 PRD、原型、埋点评审交付完整性

## 复杂系统分片规则

复杂系统默认不要写成一份总 PRD，优先按以下方式拆分：

1. 按用户角色拆：
   - 管理端
   - 执行端
   - 审计/运营端
2. 按流程阶段拆：
   - 配置
   - 执行
   - 结果与异常
3. 按能力域拆：
   - 核心主流程
   - 权限与规则
   - 通知、日志、报表

优先顺序：
- 先写主流程 PRD
- 再写关键例外流程
- 最后写外围增强能力

## 标准输入包

```markdown
# PRD 输入包

## 入口模式
- from-idea / from-discovery / from-story-map

## 功能目标
- [一句话描述]

## 必备信息
- 目标用户：
- 业务目标：
- 成功指标：
- In Scope：
- Out of Scope：

## 可选上游输入
- 已验证假设：
- 故事地图中的故事：
- 已有 PRD 草稿：
```

## 标准输出包

```markdown
# PRD 输出包

## 核心交付物
- PRD：
- 原型：
- 埋点规范：

## 评审结果
- 第一轮 PRD 评审结论：
- 第二轮交付评审结论：

## 可直接给下游使用
- 给 `/launch`：交付范围、依赖、验收标准
- 给 `/tracking-spec`：核心事件、关键指标、漏斗节点
- 给 `/analyze`：上线前后的关键指标、守护指标、验证假设
- 当前状态：`specified / ready-to-build`
```

## 后续联动建议

如果这份 PRD 满足以下任一条件，默认建议下一步优先进入 `/analyze`，而不是直接准备发布：

- 功能目标依赖数据验证是否成立
- 方案存在明显效果不确定性
- 成功标准主要靠指标变化判断
- 需要灰度观察或实验验证

这类需求的推荐路径是：

```text
/write-prd -> /analyze -> /launch
```

## 状态机位置

- 进入前通常处于 `validated` 或 `planned`
- PRD 评审通过后进入 `specified`
- 原型和埋点补齐后进入 `ready-to-build`

## 示例

```
/write-prd 做一个用户分享功能
/write-prd 会员积分体系重构
/write-prd 新增 AI 写作助手
/write-prd from-discovery 用户分享功能
/write-prd from-story-map 用户分享 MVP
/write-prd lite 草稿自动保存功能
```

## 输出

- 完整 PRD 文档（可评审版）
- HTML 可交互原型
- 埋点规范文档
- 评审意见汇总
- 待确认项清单
- 建议下一步命令
