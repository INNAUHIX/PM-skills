---
name: interview
description: 访谈全流程：准备脚本 -> 执行访谈 -> 提炼洞察
skills:
  - identify-needs
  - interview-script
  - interview-summary
---

# /interview — 访谈全流程

从访谈目标出发，明确假设 → 设计提纲 → 提炼洞察。

## 使用场景

当你需要开展用户访谈时使用：
- `帮我准备一个用户访谈`
- `我想了解用户对 XX 的看法`
- `帮我总结一下访谈记录`

## Skill 链路

1. **identify-needs** — 明确访谈目标和关键假设
2. **interview-script** — 设计结构化访谈提纲
3. **interview-summary** — 从访谈记录提炼洞察

## 子命令

- `prep` — 只准备访谈提纲（identify-needs + interview-script）
- `summarize` — 只总结访谈记录（interview-summary）

## 示例

```
/interview 验证 AI 写作助手是否解决用户痛点
/interview prep 了解企业用户采购决策流程
/interview summarize [上传访谈记录]
```

## 输出

- 访谈目标和关键假设
- 结构化访谈提纲（含开场、核心问题、结尾）
- 洞察清单 + 待验证假设