---
name: bid-playbook
description: >
  This skill should be used when the user wants to build an INTERNAL bid playbook /
  作战手册 for a tender — phrases like "作战手册", "投标作战手册", "生成作战手册", "投标准备",
  "bid playbook", "tender war plan". Acting as a Bid Captain, it turns 01_资料整理 plus
  the RFP into an internal-only playbook under 99_投标/00_作战手册/: who delivers what, by
  when, hard gates (含 SAP 资质废标项), decision chain, win/loss strengths, gap closing.
  FIRST stage of the bidding track; its output is NEVER shown to the client.
metadata:
  version: "0.1.0"
  stage: "21"
---

# 作战手册生成（投标线第 1 步）

以"投标作战参谋（Bid Captain / 投标 PM）"视角，把 `01_资料整理/` 的结构化资料与 `00_前期输入/` 的 RFP 原文，转化为面向 IBM 投标团队（或用户指定投标主体）的**内部作战手册**，落位 `99_投标/00_作战手册/`，供团队分工执行并供技术标编制引用。

## 何时使用

进入投标阶段、用户要准备投标作战手册 / 拆解 RFP 与竞争攻防时。需先完成资料整理（presales-research）。

## 关键定位：纯内部文档

与方案输出的"对客上屏"原则**恰好相反**。签约卡点、决策链分析、竞争攻防、弱项缓解话术、甲乙方边界主张、报价策略——这些在对客文档里被禁止（只能进 `.内部.md`）的内容，在作战手册里**正是主线，必须直白写出**。任何内容不得直接交给客户。

手册要让团队任何成员拿起来就能回答：要交什么（必交材料、硬性门槛含 SAP 资质废标项、格式要求）、何时交谁负责（倒排到天、卡在谁手里）、怎么打（差异化主张排序、弱项缓解、缺口找谁补）。

## 执行方式

1. 先读 `references/原始提示词.md` —— 本阶段完整操作提示词。严格按其执行。
2. 占位符纪律、三类编造禁区、SAP 模块名单一事实源、命名与路径、停止点契约、主体称呼与正式名称一律遵循 `../../shared/00_全局约定.md`（SSOT）。冲突以 SSOT 为准。
3. 防编造红线：客户决策/预算、竞品内部信息、IBM 或投标主体商务数据无可靠来源时一律占位符，严禁编造。
4. 作战手册正文、表头和头部信息必须写 `IBM`（或用户指定投标主体正式名称）与客户正式名称；客户正式名称缺失时必须停止当前阶段并要求用户提供正式名称，不得写 `【待确认：客户正式名称】`，不得用"我方/客户方/贵方/对方/客户"替代。

## 输出

**必须用 Write 工具实际写入文件**，落位 `99_投标/00_作战手册/`，固定三份 `.md`：

- `投标作战手册-技术部分.md`
- `投标作战手册-商务部分.md`
- `投标作战手册-相关进度.md`

按需经用户确认再增补 `投标作战手册-<专项名>.md`（如竞争对策、宣讲与答辩）。

> **落盘铁律**：手册篇幅长，**严禁只把正文打印在对话里**——只在对话输出而未写文件，视为未交付。每份逐一 Write 落盘，写完一份确认文件已创建再写下一份。Phase 1 是停止点（只输出关键事实摘要 + 增补推荐，不写文件）；用户确认后才进 Phase 2 实际写这三份 md。
