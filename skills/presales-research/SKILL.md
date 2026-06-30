---
name: presales-research
description: >
  This skill should be used when the user wants to organize raw presales source
  material into a structured library — phrases like "整理资料", "把素材整理成结构化",
  "整理售前素材库", "处理 00_前期输入", "organize the source material", "build the
  material library". It turns emails, meeting notes, client documents and RFPs in
  00_前期输入/ into structured topic folders under 01_资料整理/, and produces the
  产品模块对齐表 (the SAP product/module SSOT). It is the SECOND stage of the
  presales-agent pipeline, feeding 方案输出 and 投标.
metadata:
  version: "0.1.0"
  stage: "2"
---

# 资料整理（流水线第 2 阶段）

把 `00_前期输入/` 里的原始素材（邮件、会议纪要、客户文档、RFP 等）整理成结构化售前素材库，落位到 `01_资料整理/` 的六个主题子目录，并产出下游赖以引用的 `产品模块对齐表.md`（SAP 产品/模块名单一事实源）。产品/行业/公司无关——任何 B2B 售前或咨询项目都适用，具体术语由项目自行注入素材。

## 何时使用

用户已有原始素材、要整理成结构化素材库供方案/投标使用时。需先完成初始化（presales-init）建好目录。

## 执行方式

1. 先读 `references/原始提示词.md` —— 本阶段完整操作提示词（输入/输出定义、六类主题结构、产品模块对齐表生成规则、`Processed_Files.md` 索引维护、自检清单）。严格按其执行。
2. 全程遵循 `../../shared/00_全局约定.md`（SSOT）：占位符纪律（`【待补】`/`【待确认】`）、三类编造禁区、SAP 模块名单一事实源、命名与路径规则、主体称呼与正式名称。冲突以 SSOT 为准。
3. 防编造红线：无本地源、联网也无公开源的客户决策/竞品内部/事实纪要/IBM 或供应商商务数据，一律用占位符，严禁编造或"行业经验假设"兜底。
4. 资料正文必须使用 `IBM`（或用户指定供应商正式名称）与客户正式名称；客户正式名称缺失时必须停止当前阶段并要求用户提供正式名称，不得写 `【待确认：客户正式名称】`，不得用"我方/客户方/贵方/对方/客户"替代。

## 输出

`01_资料整理/` 下六个主题子目录的内容 md（不生成 index.md）+ `产品模块对齐表.md`，并更新 `00_前期输入/Processed_Files.md`。

## 下游衔接

方案输出（presales-solution）与投标线（bid-playbook / bid-tech-proposal）都读取本阶段产物。
