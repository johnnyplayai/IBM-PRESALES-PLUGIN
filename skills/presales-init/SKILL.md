---
name: presales-init
description: >
  This skill should be used when the user wants to start or scaffold a new B2B
  presales / management-consulting / SAP digital-transformation project — phrases
  like "初始化售前项目", "建项目骨架", "新建方案项目目录", "set up a presales project",
  "create the project skeleton". It builds a standardized, idempotent working-directory
  structure (前期输入 / 资料整理 / 方案输出 / 页面输出 / 投标 / 技术标) and explains the
  downstream execution order. It is the FIRST stage of the presales-agent pipeline.
metadata:
  version: "0.1.0"
  stage: "1"
---

# 售前项目初始化（流水线第 1 阶段）

为 B2B 售前、管理咨询、SAP 数字化转型方案项目创建标准化、幂等、可复用的工作目录骨架，并向用户说明后续各阶段的执行顺序与输入输出关系。任务不是分析业务，而是一次性建好稳定的目录结构。

## 何时使用

用户要开启新项目、搭建工作目录、或为已有项目查漏补缺目录结构时。这是整条流水线的起点。

## 执行方式

1. 先读 `references/原始提示词.md` —— 这是本阶段完整的操作系统提示词（角色、幂等执行规则、目录骨架定义、向用户的说明话术）。严格按其执行。
2. 全程遵循插件共享的单一事实源 `../../shared/00_全局约定.md`：目录命名两位数字前缀、用字统一「模板」、页码三位补零、日期 `YYYY-MM-DD`、路径相对项目根。冲突一律以 SSOT 为准。
3. 幂等：已存在的目录/文件不覆盖，只补缺。

## 输出

在项目根下建立标准目录骨架（含技术标独立目录），并输出一份后续阶段执行顺序说明给用户。

## 下游衔接

骨架建好后，依次进入：资料整理（presales-research）→ 方案输出（presales-solution）→ 页面输出（presales-pages）；投标线另起：作战手册（bid-playbook）→ 技术标（bid-tech-proposal）。
