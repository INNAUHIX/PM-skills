---
name: analyze
description: 从数据问题到实验验证的数据驱动链路
skills:
  - pm-analytics
  - pm-experiment-designer
  - pm-analytics
---

# /analyze — 数据分析流程

从数据问题出发，分析根因 → 设计实验验证 → 分析结果并行动。

## 使用场景

当你有数据问题需要分析，或想验证某个产品假设时使用：
- `DAU 为什么跌了`
- `帮我分析一下这组数据`
- `设计一个 A/B 测试验证 XX 假设`

## Skill 链路

1. **pm-analytics** — 从数据现象定位根因，生成假设推断
2. **pm-experiment-designer** — 设计 A/B 测试方案验证假设
3. **pm-analytics** — 分析实验结果，制定行动建议

## 示例

```
/analyze DAU 最近一周下降了 15%
/analyze 注册转化率从 30% 跌到 20%
/analyze 设计 A/B 测试验证新注册流程是否提升转化
```

## 输出

- 数据分析报告（指标树 + 漏斗/留存/分群分析）
- 假设推断列表（含关系类型和可信度）
- A/B 测试方案（含样本量、周期、决策规则）
- 行动建议 + 实验设计