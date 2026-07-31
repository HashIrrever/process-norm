# Process Norm

Specification-led coding, review, and debugging for Codex.

面向 Codex 的规范驱动开发、评审与调试流程。

## English

Process Norm keeps implementation decisions anchored to two project-level contracts:

- `design.md` for frontend presentation, interaction, responsive behavior, accessibility, and UI states.
- `feature.md` for product behavior, rules, data contracts, errors, and acceptance criteria.

Before coding, review, refactoring, or debugging, the skill requires both documents to be read and mapped to the task. It distinguishes implementation defects, design drift, regressions, specification ambiguity, intended features, and change requests so that documented features are not accidentally "fixed" as bugs. Large modules must include architectural comments explaining responsibilities, boundaries, data flow, invariants, and failure behavior.

The `assets/` directory contains starter templates for both required documents.

## 中文

Process Norm 用两份项目级规范约束开发过程：

- `design.md`：定义前端展示、交互、响应式行为、无障碍和各种界面状态。
- `feature.md`：定义产品功能、业务规则、数据契约、错误处理和验收标准。

在 Coding、Review、Refactoring 或 Debugging 前，skill 会要求完整读取两份规范并建立任务映射。它会区分实现缺陷、设计偏移、回归、规范歧义、既有功能和变更请求，避免把已经明确记录的 feature 当成 bug 修复。大型模块还必须包含职责、边界、数据流、不变量和异常行为等架构级注释。

`assets/` 目录提供了两份规范的起始模板。

## Installation / 安装

Clone the repository into your personal Codex skills directory:

    git clone https://github.com/HashIrrever/process-norm.git ~/.codex/skills/process-norm

Start a new Codex task and invoke `$process-norm`.

将仓库克隆到个人 Codex skills 目录，然后在新任务中调用 `$process-norm`。

## Repository contents / 仓库内容

- `SKILL.md` — workflow and enforcement rules / 工作流与强制规则
- `agents/openai.yaml` — Codex UI metadata / Codex 界面元数据
- `assets/design.md` — frontend design template / 前端展示设计模板
- `assets/feature.md` — functional specification template / 功能特性设计模板

## License

MIT