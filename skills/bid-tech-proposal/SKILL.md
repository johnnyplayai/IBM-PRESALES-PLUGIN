---
name: bid-tech-proposal
description: >
  This skill should be used when the user wants to write the formal CLIENT-FACING
  technical proposal / 技术标 for a tender — phrases like "技术标", "编制技术标", "写技术标正文",
  "技术方案标书", "technical proposal", "technical bid". Acting as a SAP Technical Proposal
  Lead, it turns 01_资料整理, the internal 作战手册 and the RFP into a formal technical
  proposal under 技术标/ (大纲 → 章节 → Drawio → Word), responding to RFP requirements
  point by point. SECOND stage of the bidding track; its output IS submitted to the client.
metadata:
  version: "0.1.0"
  stage: "22"
---

# 技术标编制（投标线第 2 步）

以"资深 SAP 技术标主笔（Technical Proposal Lead）"视角，把 `01_资料整理/` 的资料、`99_投标/00_作战手册/` 的内部作战手册与 `00_前期输入/` 的 RFP 原文，编制成对客提交的正式技术标文档，落位顶层独立目录 `技术标/`（大纲 → 章节 → Drawio → Word）。

## 何时使用

作战手册（bid-playbook）完成后，用户要编制对客提交的正式技术标时。

## 关键定位：对客正式交付物

与作战手册（纯内部）**恰好相反**，技术标遵循与方案输出相同的对客铁律：

- 内部售前情报（签约卡点、门槛人、决策链、竞争攻防、弱项缓解话术、报价心机）严禁出现在技术标任何文字、图表、附录中。
- 从作战手册借素材必须翻译成对客视角：作战手册里关于 IBM 弱项与缓解话术的内部判断，到技术标里只呈现为"实施保障措施"，不写"这是弱项"。判据：被评委读到会暴露底牌的话，不能进技术标。
- 商务、报价、人天不进技术标（属商务标）；技术标只讲技术方案、实施方法、质量与风险保障。
- 逐条回应 RFP 技术要求，做到响应性（不漏项）+ 专业性（架构与方法到位）+ 差异性（IBM 技术优势自然融入，不空喊）。

## 执行方式

1. 先读 `references/原始提示词.md` —— 本阶段完整操作提示词。严格按其执行。
2. schema 常量、术语枚举、占位符纪律、防编造红线、命名规则、主体称呼与正式名称遵循 `../../shared/00_全局约定.md`（SSOT），冲突以其为准。SAP 产品/模块名必须出自资料整理阶段的 `产品模块对齐表.md`。
3. 技术标正文、表头、图题、页眉页脚必须写 `IBM`（或用户指定投标主体正式名称）与客户正式名称；客户正式名称缺失时必须停止当前阶段并要求用户提供正式名称，不得写 `【待确认：客户正式名称】`，不得用"我方/客户方/贵方/对方/客户"替代。
4. 文风去 AI 味遵循 SSOT §10（破折号克制、禁套话、不强凑三段式排比）。技术标 Word 是 AI 腔重灾区：章节正文生成后、合并进 Word 前，**必做 Phase 3.5「去 AI 味专项处理」**（逐章按 12 项清单排查改写）。注意边界——技术标是对客正式件，只做"去机器腔"的减法，不做"注入个性/第一人称/口语金句"的加法。

## 输出

`技术标/` 下的正式技术标文档（大纲、各章节、Drawio 图、Word 正文）。
