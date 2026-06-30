---
name: presales-pages
description: >
  This skill should be used when the user wants to turn proposal pages into
  image-generation prompts for Lovart / GPT-Image 2 — phrases like "页面输出", "出图提示词",
  "生成 Lovart 提示词", "把方案页转成出图", "make the slide image prompts", "Lovart prompts".
  Acting as a page-output controller, it reads the density-controlled client-facing short
  on-screen copy from 02_方案输出 plus the IBM layout spec, and emits concise Lovart prompts
  per slide under 03_页面输出/. FOURTH stage of the
  presales-agent pipeline.
metadata:
  version: "0.1.0"
  stage: "4"
---

# 页面输出（流水线第 4 阶段）

面向 **Lovart（底层 GPT-Image 2）** 的 PPT 页面输出控制器。读取上游已经按密度定稿的上屏短稿与版式定义，把每一页转化为可直接粘贴进 Lovart 出图的精简单页提示词，落位 `03_页面输出/`。本 skill 只做视觉转译，不再决定信息密度，也不把讲稿长段搬回画面。

## 何时使用

方案输出（presales-solution）完成后，用户要把方案页转成 Lovart / GPT-Image 出图提示词时。

## 执行方式

1. 先读 `references/原始提示词.md` —— 本阶段完整控制器提示词（读取范围、上屏短稿转译规则、文件拆分、自检）。严格按其执行。
2. 出图模板与五层结构来自 `../../shared/输出格式-Lovart-GPTImage2.md`（唯一输出格式文件）。品牌视觉值、对象坐标、尺寸、字号字重对齐来自 `../../shared/页面版式定义-IBM.md`（版式权威源，内容画布须容纳至多 5 个短内容块）。
3. schema 常量、术语枚举、防编造红线、主体称呼与正式名称引用 `../../shared/00_全局约定.md`（SSOT）。信息密度已由 Solution 阶段固化，页面输出不得再询问或改档。
4. **只读对客上屏产物**：读 `02_方案输出/Pxx-Pxx.md` 与 `骨架.md`，严禁读取 `.讲稿.md` 与 `.内部.md`。严禁把字段名、维度词/枚举词搬进画面文字（SSOT §5）。
5. 若上游文本仍含"我方/客户方/贵方/对方/客户"等泛称，页面输出时必须按 SSOT §2.4 转写为 `IBM`（或用户指定供应商正式名称）与客户正式名称；客户正式名称缺失时必须停止当前阶段并要求用户提供正式名称，不得写 `【待确认：客户正式名称】`。
6. 并行生成：每页独立任务，不用脚本拼接（输出需要逐页思考）。

## 输出

`03_页面输出/` 下每页一个可独立复制给 Lovart 的精简单页提示词。
