---
name: plan
description: 从需求到路线图到 Sprint 规划的完整链路
skills:
  - demand-prioritization-engine
  - pm-roadmap-planner
  - user-story-mapping
  - iteration-planning
---

# /plan — 产品规划流程

从需求池出发，多模型评分 → 排路线图 → 切 MVP → 拆 Sprint。

## 运行模式

- `full`：优先级 -> 路线图 -> 故事地图 -> Sprint
- `lite`：只做优先级和路线图
- `delivery`：从已存在的 Epic / 路线图直接进入故事地图和 Sprint

### 模式选择建议

| 当前场景 | 推荐模式 | 原因 |
|---------|---------|------|
| 季度目标 / 需求池排期 | `full` | 需要完整规划链路 |
| 只想先做路线图 | `lite` | 不必提前拆故事 |
| 已有 Epic，要落到执行 | `delivery` | 直接进入切片和 Sprint |
| 单个功能，边界很小 | `/story-map` 优先 | `plan` 可能偏重 |

## 使用场景

当你有需求池或季度目标，需要制定执行计划时使用：
- `帮我规划 Q2 的工作`
- `这些需求怎么安排`
- `制定一个版本计划`
- `这些 Epic 已经定了，帮我拆到执行`

## Skill 链路

1. **demand-prioritization-engine** — 对需求进行多模型优先级评分
2. **pm-roadmap-planner** — 将优先级转化为季度路线图和里程碑
3. **user-story-mapping** — 将 Epic 拆成用户任务流、用户故事和 MVP 切片
4. **iteration-planning** — 将 MVP 故事拆解为 Sprint 任务

## 跳步规则

- `lite` 模式跳过 `user-story-mapping` 和 `iteration-planning`
- `delivery` 模式跳过 `demand-prioritization-engine`
- 如果用户只有单个 Epic，优先建议 `/story-map`

## 状态机位置

- 完成优先级和路线图后，状态从 `validated` 进入 `planned`
- 完成故事地图和 Sprint 后，状态进入 `ready-to-build`

## 示例

```
/plan Q2 提升用户留存
/plan 新增 20 个功能需求
/plan 会员体系重构计划
/plan lite Q3 路线图
/plan delivery 会员体系 Epic 落地
```

## 输出

- 多模型优先级评分表
- 季度路线图（含里程碑和成功指标）
- 用户故事地图和 MVP 切片
- Sprint 任务拆解
- 建议下一步命令
