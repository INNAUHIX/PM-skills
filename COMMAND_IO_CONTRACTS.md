# PM Skill Commands 输入输出契约

这份文档用于减少主链路中的信息丢失和重复劳动。

---

## 1. `discover -> write-prd`

### `discover` 应输出

```markdown
## 可交给 write-prd 的输入
- 功能目标
- 目标用户
- 已验证假设
- 高风险未验证假设
- 成功指标
- In Scope / Out of Scope
- 问题定义与当前现象
- 初步解法与担心的副作用
```

### `write-prd` 应优先消费

- 已验证假设，不重复做需求抽象
- 高风险未验证假设，写入风险和待确认项
- 成功指标，写入 PRD 目标章节

---

## 2. `story-map -> write-prd`

### `story-map` 应输出

```markdown
## 可交给 write-prd 的输入
- Epic 名称
- MVP 故事清单
- 用户主任务流
- 版本边界
- 推荐先写 PRD 的故事
```

### `write-prd` 应优先消费

- 只针对单个故事或单个切片写 PRD
- 把任务流转成功能流程和异常流程

---

## 3. `write-prd -> launch`

### `write-prd` 应输出

```markdown
## 可交给 launch 的输入
- 交付范围
- 验收标准
- 依赖项
- 关键埋点和监控指标
- 关键风险
```

### `launch` 应优先消费

- 不重新写 PRD
- 直接围绕交付范围、风险和发布窗口产出交接包与发布计划

---

## 4. `write-prd -> analyze`

### `write-prd` 应输出

```markdown
## 可交给 analyze 的输入
- 关键验证假设
- 主指标
- 守护指标
- 关键埋点
- 灰度观察重点
```

### `analyze` 应优先消费

- 不重新定义目标
- 直接围绕验证假设和指标变化设计分析或实验

---

## 5. 推荐状态机

为了让用户知道“当前在哪一步”，主链路建议统一用以下状态：

1. `idea`
2. `validated`
3. `planned`
4. `specified`
5. `ready-to-build`
6. `ready-to-launch`
7. `launched`
8. `reviewed`
