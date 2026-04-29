# On My SDD

规范驱动开发技能套件 — 将 OpenSpec（规范层）和 Superpowers（执行纪律）整合为一个可安装的技能。

## 安装

### Claude Code

```bash
npx skills add https://github.com/9Ashwin/on-my-sdd.git --skill sdd-workflow
```

或安装完整插件：

```bash
/plugin install https://github.com/9Ashwin/on-my-sdd.git
```

### Codex

```bash
git clone https://github.com/9Ashwin/on-my-sdd.git ~/.codex/on-my-sdd
mkdir -p ~/.agents/skills
ln -s ~/.codex/on-my-sdd/skills ~/.agents/skills/on-my-sdd
```

详见 [Codex 安装指南](.codex/INSTALL.md)

## 包含内容

一个 `sdd-workflow` 技能覆盖完整 SDD 流程：

| 阶段 | 工具 | 说明 |
|------|------|------|
| **分类** | Boundedness Check | 判断请求类型：单行修复？Bug？边界清晰的功能？模糊需求？ |
| **探索** | `/opsx:explore` | 阅读代码，为陌生代码库建立上下文 |
| **设计** | `superpowers:brainstorming` | 对模糊需求进行苏格拉底式设计 — 方案对比、范围界定 |
| **规范** | `/opsx:propose` | 生成四大件：proposal.md + specs/ + design.md + tasks.md |
| **审核** | `reference/sdd-review-specs.md` | 分级审核关卡 — 验证范围、完整性、设计、可执行性 |
| **计划** | `superpowers:writing-plans` | 将 tasks.md 细化为 2-5 分钟粒度的子任务 |
| **实现** | `/opsx:apply` + TDD | 红 → 绿 → 重构 逐任务循环 |
| **归档** | `/opsx:archive` | Delta 合并规范，变更移至 archive/ |

## 目录结构

```
skills/sdd-workflow/
├── SKILL.md                         ← 路由、Boundedness Check、流程编排
└── reference/
    └── sdd-review-specs.md          ← 审核清单、红旗信号、分级关卡
```

## 快速参考

```
模糊需求（"加点协作功能"、"完善一下代码"）
    → Boundedness Check → 不清晰
    → /opsx:explore（读代码）→ 重新检查
    → superpowers:brainstorming（设计方案）
    → /opsx:propose（生成规范）
    → 审核（reference/sdd-review-specs.md）
    → writing-plans → /opsx:apply + TDD → /opsx:archive

清晰需求（"添加 DELETE /tasks/{id}"）
    → Boundedness Check → 边界清晰
    → /opsx:propose（生成规范）
    → 审核 → writing-plans → 实现 → 归档
```

## 许可证

MIT
