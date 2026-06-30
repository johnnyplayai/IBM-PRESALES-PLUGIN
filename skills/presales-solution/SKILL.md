---
name: presales-solution
description: >
  This skill should be used when the user wants to produce the solution narrative
  and page-level content for a presales proposal — phrases like "输出方案", "写方案叙事",
  "生成方案页面内容", "做 PPT 方案内容", "produce the solution", "draft the proposal
  narrative". Acting as a chief solution architect, it turns 01_资料整理 into density-controlled
  PPT-ready page content under 02_方案输出/: client-facing short on-screen copy (Pxx-Pxx.md),
  optional speaker/argument notes (Pxx-Pxx.讲稿.md), and internal-only strategy notes
  (Pxx-Pxx.内部.md). THIRD stage of the presales-agent pipeline; feeds 页面输出.
metadata:
  version: "0.1.0"
  stage: "3"
---

# 方案输出（流水线第 3 阶段）

承接 `01_资料整理`，以"拥有 20 年经验的首席解决方案架构师 + 顶级管理咨询商业叙事"的视角，产出供下游页面输出使用的 PPT-ready 页面内容，落位 `02_方案输出/`。本阶段决定信息密度，并把上屏短稿、讲稿论证、内部策略物理拆开，避免把报告长段直接送去出图。

## 何时使用

资料整理（presales-research）完成后，用户要把素材转成方案叙事 / PPT 页面内容时。

## 执行方式

1. 先读 `references/原始提示词.md` —— 本阶段完整操作提示词（角色与思维方式、交流目的确认、Agenda 与骨架生成、L1-L4 页面分层、信息密度确认、上屏短稿/讲稿/内部稿拆分、质量自检）。严格按其执行。
2. schema 常量、术语枚举、命名、防编造红线、主体称呼与正式名称、信息密度档位一律引用 `../../shared/00_全局约定.md`（SSOT），不在本阶段另立数字。关键 schema：L4 上屏内容是短稿，不是长论证；单条上屏短句 ≤35 字。
3. **交流目的前置**：本阶段在 Agenda 前置共识中先确认并固化 `首次交流` / `正式投标` / `定标前沟通（最后述标）`。交流目的决定内容深度、章节范围和页数，并影响信息密度建议；但三类交流目的均可选择任一信息密度，不按交流目的固定默认密度；`正式投标` 默认包含技术评审所需深度。
4. **信息密度前置（SSOT §2.2）**：本阶段在 Agenda 前置共识中单独确认并固化 `高密度（专家评审）` / `中密度（正式汇报）` / `低密度（高管沟通）`。页面输出阶段不再询问密度。
5. **三产物物理隔离（SSOT §3）**：上屏短稿写 `Pxx-Pxx.md`；长解释/支撑事实/讲者备注写 `Pxx-Pxx.讲稿.md`；战略意图/签约卡点/决策链/说服策略等内部情报只写 `Pxx-Pxx.内部.md`。页面输出只读 `Pxx-Pxx.md`，严禁读取后两者。
6. 对客上屏和内部页都必须使用 `IBM`（或用户指定供应商正式名称）与客户正式名称；客户正式名称缺失时必须停止当前阶段并要求用户提供正式名称，不得写 `【待确认：客户正式名称】`，不得用"我方/客户方/贵方/对方/客户"等泛称。
7. 咨询基调只取 `管理咨询` 或 `数字化转型` 之一，每页顶部标注。维度词/枚举词禁令见 SSOT §5。文风去 AI 味见 SSOT §10（破折号克制、禁套话、不强凑三段式）。

## 输出

`02_方案输出/` 下：Agenda、骨架.md（封面/目录/章节）、各正文页 `Pxx-Pxx.md`（上屏短稿）、按需 `Pxx-Pxx.讲稿.md`（讲稿/论证材料）与 `Pxx-Pxx.内部.md`（内部策略）。

## 下游衔接

页面输出（presales-pages）只读 `Pxx-Pxx.md` 与 `骨架.md`，严禁读取 `.讲稿.md` 与 `.内部.md`，且不再改变信息密度。
