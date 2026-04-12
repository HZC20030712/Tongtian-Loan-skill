# 通天贷·借贷策略优化.skill

> *"羊毛薅尽，寸草不生！"*

![License MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
[![AgentSkills](https://img.shields.io/badge/AgentSkills-Standard-green)](https://agentskills.io)
![Openclaw](https://img.shields.io/badge/Openclaw-✓-ff6b35)
![Hermes](https://img.shields.io/badge/Hermes-✓-9b59b6)
![Claude Code](https://img.shields.io/badge/Claude_Code-✓-blueviolet)

---

你的信用卡账单已经叠成摩天楼？
你的综合年化，悄悄爬过了 20%？
你借了 A 还 B，借了 B 还 C，利息在黑暗里复利滚动？
你不知道哪笔该先还，哪笔该置换，征信查询次数还剩几发？


把你的负债清单扔过来（平台名、利率、余额、还款日、月供），
加上一句最焦虑的话，
换来一份**真正能用的债务作战地图**。

[核心主张](#核心主张) · [安装](#安装) · [功能模块](#功能模块) · [触发词](#触发词) · [合规边界](#合规边界) · [多语言宣言](#多语言宣言)

---

## 核心主张

在合法合规的框架内，通过数学统筹与时序规划，实现：

- **借最多** — 在负债率安全阈值内，最大化可用资金总量
- **利息最低** — 通过组合优化压缩综合资金成本（WACC）
- **风险最小** — 通过压力测试与征信保护，防止资金链断裂

---

## 安装

核心文件为 `tiantai-loan.md`，纯 Markdown，兼容所有主流 AI 编程助手。

### Openclaw ⭐ 推荐

```bash
cp tiantai-loan.md ~/.openclaw/skills/tiantai-loan.md
```

### Hermes ⭐ 推荐

```bash
cp tiantai-loan.md ~/.hermes/skills/tiantai-loan.md
```

### Claude Code

```bash
cp tiantai-loan.md ~/.claude/skills/tiantai-loan.md
```

### HappyCapy

```bash
cp tiantai-loan.md ~/.claude/skills/tiantai-loan.md
```

路径与 Claude Code 共享，直接使用触发词激活。

### Cline（VS Code）/ OpenCline / Roo Code

**方式一：全局生效（推荐）**
打开 Cline 面板 → 齿轮 ⚙ → Custom Instructions → 粘贴 `tiantai-loan.md` 全文

**方式二：项目级**
```bash
cp tiantai-loan.md .clinerules
```

## 功能模块

| 模块 | 说明 |
|------|------|
| 债务档案建立 | 逐笔引导录入，自动匹配 18 个平台利率数据库 |
| WACC 全量分析 | 算出真实综合资金成本，不是"日息万三"糊弄你的数字 |
| 债务置换扫描 | 发现可套利的利差窗口，含违约金净收益完整计算 |
| 征信保护时序 | 规划申请节奏，避免密集查询触发风控降额 |
| 还款日历 | 生成近 30 天还款作战地图，一眼看清现金流缺口 |
| 蒙特卡洛压测 | 100 次迭代模拟极端场景，给出资金链存活率 |
| 苟命协议 | 存活率跌破阈值时触发，债务重组优先级 + 应急止血方案 |

---

## 触发词

```
/tiantai-loan
通天贷
帮我优化贷款
债务分析
贷款规划
还款计划
我借钱了
```

---

## 算法支撑

- **WACC** — 加权平均资金成本，将日息、月息、等额本息统一还原为可比年化
- **DTI** — 债务收入比四级红绿灯（绿 / 黄 / 橙 / 红），超限触发约束
- **债务置换净收益不等式** — 节省利息 > 违约金 + 手续费 + 征信成本，才值得动
- **雪崩法优先级排序** — PriorityScore 公式，决定哪刀先砍
- **蒙特卡洛压测** — 100 次迭代，输出存活率与风险等级

---

## 平台数据库

`platforms-database.json` 涵盖 18 个平台参考利率，包括国有大行消费贷、股份制银行、互联网消费贷、信用卡、花呗、公积金贷款及 LPR 历史锚点。

> **免责声明：** 所有数据为 2025-2026 市场参考行情，实际批复利率因个人资质动态变化，以各平台官方合同为准。本 Skill 不替代任何持牌金融机构的专业建议。

---

## 合规边界

本 Skill **绝不**：
- 代替用户提交任何贷款申请
- 推荐非法渠道（征信修复、黑户洗白、校园贷、套现等）
- 存储用户身份证号、银行卡号等敏感信息
- 提供超出数学计算与信息整合范围的金融建议

---

## 文件结构

```
tiantai-loan-skill/
├── tiantai-loan.md          # 主 Skill 文件（安装本体）
├── platforms-database.json  # 18 个平台利率参考数据库
├── README.md                # 本文件
└── docs/
    └── 通天贷-开发文档.md    # 完整开发规格说明书
```

---

*通天贷·贷无忧 v1.0 · 2026-04-12 · Built with HappyCapy Agent Teams*
