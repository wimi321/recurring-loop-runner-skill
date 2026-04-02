# Recurring Loop Runner

[English](./README.md) | 简体中文

Use when the user wants a prompt or command to run on a recurring interval, such as checking deploys, polling status, or repeating a slash-command.

## 这个技能是做什么的

Recurring Loop Runner 把 Claude Code 中可复用的一类工作流提取成独立 skill 仓库，方便在不同智能体环境里直接安装、复用和持续维护。

## 核心特点

- 聚焦单一能力边界，适合公开分发
- 仓库根目录就是 skill 根目录
- 内置 `agents/openai.yaml` 元数据
- 保留来源说明，便于追踪提取依据
- 提供中英文双语 README

## 擅长场景

- Schedule recurring prompts and checks
- 执行 `SKILL.md` 中定义的标准工作流
- 为智能体或操作者提供稳定、可复用的输出

## 示例请求

- Check the deploy every 15 minutes.
- Run this slash-command hourly and execute it once now.

## 工作流程

1. Parse the interval from the user request.
2. Normalize human phrasing into a valid cadence.
3. Create the recurring schedule.
4. Confirm the cadence, identifier, and expiry behavior.
5. Execute the task once immediately so the user gets instant feedback.

## 输入

- Requested cadence
- Prompt or command to repeat

## 输出

- Scheduled recurring task
- Immediate first execution
- Cancellation details

## 成功标准

- The interval is parsed correctly.
- The task is both scheduled and run once immediately.
- The user knows how to stop it later.

## 不适用场景

- One-off commands with no repeating behavior

## 安装方式

### 作为独立 skill 使用

克隆本仓库，并将仓库根目录放入兼容的 skill 目录即可。

### 从合集仓库使用

该 skill 也收录在总仓库中：

- [claude-code-skills-extract](https://github.com/wimi321/claude-code-skills-extract)

## 仓库结构

- `SKILL.md`：技能主定义
- `README.md`：英文说明
- `README.zh-CN.md`：中文说明
- `agents/openai.yaml`：面向智能体 UI 的元数据
- `references/`：来源与补充说明
- `LICENSE`：开源许可证

## 来源说明

Derived from `src/skills/bundled/loop.ts`.

## 相关项目

- 总仓库：[claude-code-skills-extract](https://github.com/wimi321/claude-code-skills-extract)
- 当前仓库：[recurring-loop-runner-skill](https://github.com/wimi321/recurring-loop-runner-skill)
