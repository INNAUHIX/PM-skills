---
name: discover
description: 支持分阶段运行的需求发现流程：从模糊想法到可验证假设
skills:
  - identify-needs
  - user-prioritization
  - interview-script
  - interview-summary
---

# /discover — 需求发现流程

从模糊想法出发，识别假设 → 排优先级 → 设计访谈 → 提炼洞察 → 生成新假设。

## 运行模式

默认支持三种模式，避免用户必须一次跑完整条链：

- `full`：完整跑完发现链路
- `stage`：只跑当前最需要的一段
- `lite`：输出最小可执行行动包

### 模式选择建议

| 当前场景 | 推荐模式 | 原因 |
|---------|---------|------|
| 单一功能优化，方向明确 | `lite` | 先快速整理假设和下一步 |
| 新产品/新市场探索 | `full` | 需要完整走发现链路 |
| 已知卡在某一段 | `stage` | 只处理当前阻塞步骤 |
| 企业复杂流程、角色多 | `full` | 需要补足多角色假设和访谈对象 |

### 推荐子模式

- `/discover ideation [想法]`：只做假设识别
- `/discover prioritize [假设清单]`：只做假设优先级
- `/discover interview-prep [高优先级假设]`：只出访谈提纲
- `/discover summarize [访谈记录]`：只做访谈总结

## 使用场景

当你有产品想法但不知道从哪下手时，使用此 Command：
- `想做一个 XX 产品`
- `帮我分析一下 XX 市场`
- `用户有这个需求，怎么验证`
- `我现在只想先整理假设`
- `我还没有访谈记录，只想先出访谈提纲`

## Skill 链路

1. **identify-needs** — 将模糊想法转化为结构化假设清单
2. **user-prioritization** — 对假设按风险/验证成本排优先级
3. **interview-script** — 针对高优先级假设设计访谈问题
4. **interview-summary** — 从访谈记录提炼洞察和新的假设

## 阶段规则

- 如果用户没有访谈记录，不强行进入 `interview-summary`
- 如果用户已提供假设清单，跳过 `identify-needs`
- 如果用户已完成优先级排序，跳过 `user-prioritization`

## 标准输入包

```markdown
# Discovery 输入包

## 当前阶段
- ideation / prioritize / interview-prep / summarize / full / lite

## 产品方向
- [一句话描述]

## 已知信息
- 目标用户：
- 业务目标：
- 当前证据：
- 已有假设：
- 是否已有访谈记录：

## 问题型需求补充
- 当前现象：
- 现有数据：
- 初步解法：
- 担心的副作用：
```

## 标准输出包

```markdown
# Discovery 输出包

## 当前结论
- 假设清单：
- 优先级结果：
- 洞察：

## 可直接给下游使用
- 给 `/write-prd`：已验证假设、范围边界、成功指标
- 给 `/interview`：高优先级假设、访谈目标、样本建议
- 给问题型需求：问题定义、核心假设、验证指标、待观察副作用

## 建议下一步
- 推荐命令：
- 推荐原因：
- 当前状态：`idea / validated`
```

## 状态机位置

- 进入前通常处于 `idea`
- 完成假设优先级后进入 `validated`
- 如果只完成访谈提纲但未验证，仍停留在 `idea`

## 示例

```
/discover 做一个 AI 写作助手，帮助用户提升内容产出效率
/discover 我们想进入 B2B 项目管理市场
/discover 验证用户是否愿意为 XX 功能付费
/discover ideation 做一个用户分享功能
/discover interview-prep 验证用户是否愿意主动分享内容
```

## 输出

- 假设清单（含验证等级）
- 优先级排序结果
- 访谈提纲（针对高优先级假设）
- 洞察清单 + 待验证假设
- 建议下一步命令
