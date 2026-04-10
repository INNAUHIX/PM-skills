# PM Skills Suite

产品管理技能包，覆盖产品管理全生命周期。

## 包含 Skills（20个）

### 需求发现
| Skill | 描述 |
|-------|------|
| 识别假设 | 需求发现与定义 |
| 优先级排序 | 用户优先级排序 |
| 访谈提纲 | 访谈提纲生成 |
| 访谈要点 | 访谈要点 |

### 产品规划
| Skill | 描述 |
|-------|------|
| 竞品分析 | 竞品策略分析 |
| 策略画布 | 战略画布 |
| 价值主张 | 价值主张 |
| 需求优先级 | 需求优先级评分引擎 |
| 路线图规划 | 路线图规划 |

### 执行交付
| Skill | 描述 |
|-------|------|
| PRD编写 | PRD 编写 |
| PRD评审 | PRD 评审 |
| 原型制作 | 原型设计 |
| 埋点规范 | 埋点规范编写 |
| 工程交接 | 工程交接 |
| 发布流程 | 发布上线 |
| 迭代规划 | 迭代规划 |
| 复盘 | 迭代复盘 |
| 用户故事地图 | 用户故事地图 |
| 数据分析 | 数据分析 |
| A-B测试 | A-B测试（A/B测试） |

## 目录结构

```
PM-skills/
├── 需求发现/                   # 需求发现阶段
├── 产品规划/                   # 产品规划阶段
├── 执行交付/                   # 执行交付阶段
└── README.md                   # 本文件
```

## 使用方法

### OpenClaw / QClaw

将技能包复制到 `~/.qclaw/skills/` 目录下即可使用。

```powershell
# 复制所有 skills
Copy-Item -Path "需求发现","产品规划","执行交付" -Destination "$HOME\.qclaw\skills\" -Recurse
```

### Claude Desktop / Claude Code

将技能包复制到 `~/.claude/skills/` 目录下即可使用。

```powershell
# 复制所有 skills
Copy-Item -Path "需求发现","产品规划","执行交付" -Destination "$HOME\.claude\skills\" -Recurse
```

### Coze

1. 打开 [Coze](https://www.coze.com)
2. 创建或进入一个 Bot
3. 进入"技能"页面
4. 点击"添加技能"，选择"导入技能"
5. 将本仓库的每个 Skill 目录（包含 SKILL.md）逐个导入

### Cursor

1. 打开 Cursor 设置
2. 进入"Skills"或"GPTs"页面
3. 点击"Add Skill"
4. 选择"Import from folder"
5. 选择对应的 Skill 目录（包含 SKILL.md）

---

MIT License
