# 通天贷·贷无忧

> *"平台是割草机，你是那片草地。每一轮薅完，寸草不生——除非你先学会拿镰刀。"*

![License MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Claude Code Skill](https://img.shields.io/badge/Claude_Code-Skill-blueviolet)
![Cline Compatible](https://img.shields.io/badge/Cline-Compatible-blue)
![Cursor Compatible](https://img.shields.io/badge/Cursor-Compatible-black)
![Windsurf Compatible](https://img.shields.io/badge/Windsurf-Compatible-teal)
![AgentSkills Standard](https://img.shields.io/badge/AgentSkills-Standard-green)
![HappyCapy](https://img.shields.io/badge/Built_by-HappyCapy-orange)

---

你的信用卡账单已经叠成摩天楼？
你的综合年化，悄悄爬过了 20%？
你借了 A 还 B，借了 B 还 C，利息在黑暗里复利生长？
你不知道哪笔该先还，哪笔该置换，征信查询次数还剩几发？

**羊毛耗尽，寸草不生——在平台收割完毕之前，让精算师替你先割一刀。**

---

把你的负债清单扔过来（平台名、利率、余额、还款日、月供）
加上一句你现在最焦虑的话
换来一份**真正能用的债务作战地图**

[功能模块](#功能模块) · [安装](#安装) · [Claude Code](#claude-code官方-cli) · [Cline](#cline-vs-code-扩展) · [Cursor](#cursor) · [Windsurf](#windsurf-codeium) · [触发词](#触发词) · [合规边界](#合规边界)

[中文](#中文宣言) · [English](#english) · [Español](#español) · [Deutsch](#deutsch) · [日本語](#日本語) · [Русский](#русский) · [Português](#português)

---

## 功能模块

| 模块 | 干什么 |
|------|--------|
| 债务档案建立 | 逐笔引导录入，自动匹配 18 个平台利率数据库 |
| WACC 全量分析 | 算出你真实的综合资金成本，不是那个"日息万三"骗你的数字 |
| 债务置换扫描 | 发现每一个可套利的利差窗口，含违约金净收益计算 |
| 征信保护时序 | 规划申请节奏，避免密集查询触发风控降额 |
| 还款日历 | 生成近 30 天还款作战地图，一眼看清现金流缺口 |
| 蒙特卡洛压测 | 100 次迭代模拟极端场景，给出资金链存活率 |
| 苟命协议 | 存活率跌破阈值时触发，债务重组优先级 + 应急止血方案 |

---

## 安装

本 Skill 核心文件为 `tiantai-loan.md`，纯 Markdown 格式，兼容所有主流 AI 编程助手。

---

### Claude Code（官方 CLI）

```bash
cp tiantai-loan.md ~/.claude/skills/tiantai-loan.md
```

安装后无需重启，下次对话输入触发词即可激活。

---

### HappyCapy

```bash
cp tiantai-loan.md ~/.claude/skills/tiantai-loan.md
```

路径与 Claude Code 共享。在 HappyCapy 会话中直接使用触发词即可。

---

### Cline（VS Code 扩展）

**方式一：全局自定义指令（推荐，永久生效）**

1. 打开 VS Code → Cline 扩展面板
2. 点击右上角齿轮 ⚙ → **Custom Instructions**
3. 将 `tiantai-loan.md` 全文内容粘贴进去
4. 保存，立即生效

**方式二：项目级规则文件**

```bash
cp tiantai-loan.md .clinerules
```

将 `.clinerules` 放在项目根目录，仅对当前项目生效。

---

### OpenCline / Roo Code / 其他 Cline 分支

与 Cline 安装方式相同，均支持 `.clinerules` 项目文件或 Custom Instructions 粘贴：

```bash
cp tiantai-loan.md .clinerules
```

---

### Cursor

**方式一：全局规则（对所有项目生效）**

1. 打开 Cursor → **Settings** → **Rules for AI**
2. 将 `tiantai-loan.md` 全文粘贴进 **User Rules** 区域
3. 保存

**方式二：项目级规则**

```bash
cp tiantai-loan.md .cursorrules
```

放在项目根目录。Cursor 会自动读取该文件作为上下文规则。

---

### Windsurf（Codeium）

```bash
cp tiantai-loan.md .windsurfrules
```

放在项目根目录即可。或在 Windsurf 设置中的 **Global Rules** 粘贴全文。

---

### Continue.dev

编辑 `~/.continue/config.json`，在 `systemMessage` 字段追加 `tiantai-loan.md` 全文内容：

```json
{
  "systemMessage": "<此处粘贴 tiantai-loan.md 全文内容>"
}
```

---

### 通用方式（任意支持系统提示的工具）

将 `tiantai-loan.md` 全文粘贴至任意 AI 工具的 **System Prompt / Custom Instructions / 自定义指令** 区域，即可激活狂躁精算师。

---

## 触发词

```
/tiantai-loan
通天贷
帮我优化贷款
债务分析
贷款规划
还款计划
我要借钱
```

---

## 算法支撑

- **WACC** — 加权平均资金成本，把日息、月息、等额本息全部还原成可比较的年化
- **DTI** — 债务收入比四级红绿灯（绿 / 黄 / 橙 / 红），超限自动触发行为约束
- **债务置换净收益不等式** — 节省利息 > 违约金 + 手续费 + 征信成本，才值得动
- **雪崩法优先级排序** — PriorityScore 公式，决定哪刀先砍
- **蒙特卡洛现金流压测** — 简化 100 次迭代，给出存活率与风险等级

---

## 平台数据库

`platforms-database.json` 涵盖 18 个平台参考利率：国有大行消费贷、股份制银行、互联网消费贷、信用卡、花呗、公积金贷款、LPR 历史锚点。

> **免责声明：** 所有数据为 2025-2026 市场参考行情。实际批复利率因个人资质动态变化，以各平台官方合同为准。本 Skill 不替代任何持牌金融机构的专业建议。

---

## 人设

**狂躁精算师 × 赛博韭菜猎手**

对平台充满鄙视，对用户全力护航。用军事比喻描述债务地形，发现套利窗口时亢奋催促，发现死局时咆哮警告。极端风险切换严肃宣言模式，绝不开玩笑。

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
├── tiantai-loan.md          # 主 Skill 文件
├── platforms-database.json  # 18 个平台利率参考数据库
├── README.md                # 本文件
└── docs/
    └── 通天贷-开发文档.md    # 完整开发规格说明书
```

---

## 开发团队

由 HappyCapy Agent Teams 联合开发：**Orchestrator**（总协调）· **algo-agent**（算法）· **persona-agent**（人设与交互）· **data-agent**（数据结构）

---

## 多语言宣言

### 中文宣言

> 羊毛耗尽，寸草不生。
> 平台是割草机，你是那片草地。
> 每一个周期，利率在悄悄生长，额度在悄悄萎缩。
> 在被收割完毕之前，让精算师替你先算清楚。

### English

> *When the platforms have harvested your last basis point, not a single yield remains.*
> The banks are the shearers. You are the field.
> Every cycle, rates creep up and credit lines quietly shrink.
> Before the next harvest, let the actuary run the numbers first.

### Español

> *Cuando las plataformas han exprimido hasta el último punto básico, no queda ni un solo rendimiento.*
> Los bancos son las segadoras. Tú eres el campo.
> Cada ciclo, las tasas suben y las líneas de crédito se reducen en silencio.
> Antes de la próxima cosecha, deja que el actuario haga los cálculos primero.

### Deutsch

> *Wenn die Plattformen den letzten Basispunkt abgeerntet haben, bleibt kein Ertrag übrig.*
> Die Banken sind die Mäher. Du bist das Feld.
> Jeden Zyklus steigen die Zinsen, und die Kreditlinien schrumpfen still.
> Lass den Aktuar die Zahlen zuerst durchrechnen — bevor die nächste Ernte kommt.

### 日本語

> *プラットフォームが最後の一ベーシスポイントまで刈り取った時、収益はひとつも残らない。*
> 銀行は刈り取り機であり、あなたはその畑だ。
> 毎サイクル、金利は静かに上がり、与信枠は音もなく縮む。
> 次の収穫が来る前に、アクチュアリーに先に計算させよ。

### Русский

> *Когда платформы собрали последний базисный пункт, не остаётся ни единого колоска.*
> Банки — это жатки. Ты — поле.
> Каждый цикл ставки ползут вверх, а кредитные линии тихо сжимаются.
> Пусть актуарий посчитает раньше, чем придёт следующий урожай.

### Português

> *Quando as plataformas colheram o último ponto base, não sobra nem um grão de lucro.*
> Os bancos são as colheitadeiras. Você é o campo.
> A cada ciclo, as taxas sobem e as linhas de crédito minguam em silêncio.
> Deixe o atuário fazer as contas primeiro — antes da próxima colheita chegar.

---

*通天贷·贷无忧 v1.0 | 2026-04-12 | Built with HappyCapy Agent Teams*
