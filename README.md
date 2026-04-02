# Recurring Loop Runner

[![Repo](https://img.shields.io/badge/github-recurring-loop-runner-skill-181717?logo=github)](https://github.com/wimi321/recurring-loop-runner-skill)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)
[![Collection](https://img.shields.io/badge/collection-claude--code--skills--extract-blue)](https://github.com/wimi321/claude-code-skills-extract)

Use when the user wants a prompt or command to run on a recurring interval, such as checking deploys, polling status, or repeating a slash-command.

English | [简体中文](./README.zh-CN.md)

## Why This Skill Exists

Recurring Loop Runner packages a reusable Claude Code workflow as a standalone public skill repository. It is designed for agent teams that want a well-documented, installable, and maintainable capability rather than an internal prompt fragment.

## Highlights

- Focused, reusable workflow with a clear trigger boundary
- Standalone skill root that works well in agent workspaces
- Agent metadata in `agents/openai.yaml`
- Public provenance back to the extracted Claude Code source
- Bilingual documentation for English and Chinese readers

## What It Is Good At

- Schedule recurring prompts and checks
- Running the workflow described in `SKILL.md` with explicit boundaries
- Producing repeatable outputs for operators and agent runtimes

## Example Requests

- Check the deploy every 15 minutes.
- Run this slash-command hourly and execute it once now.

## Workflow

1. Parse the interval from the user request.
2. Normalize human phrasing into a valid cadence.
3. Create the recurring schedule.
4. Confirm the cadence, identifier, and expiry behavior.
5. Execute the task once immediately so the user gets instant feedback.

## Inputs

- Requested cadence
- Prompt or command to repeat

## Outputs

- Scheduled recurring task
- Immediate first execution
- Cancellation details

## Success Criteria

- The interval is parsed correctly.
- The task is both scheduled and run once immediately.
- The user knows how to stop it later.

## Non-Goals

- One-off commands with no repeating behavior

## Installation

### Use as a standalone skill

Clone this repository and place the repository root in a compatible skill directory.

### Use from a larger collection

This skill is also included in the parent collection:

- [claude-code-skills-extract](https://github.com/wimi321/claude-code-skills-extract)

## Repository Layout

- `SKILL.md`: canonical skill instructions
- `README.md`: English project overview
- `README.zh-CN.md`: Simplified Chinese project overview
- `agents/openai.yaml`: UI-facing metadata for agent runtimes
- `references/`: provenance and support notes
- `LICENSE`: repository license

## Provenance

Derived from `src/skills/bundled/loop.ts`.

## Related Projects

- Parent collection: [claude-code-skills-extract](https://github.com/wimi321/claude-code-skills-extract)
- GitHub repository: [recurring-loop-runner-skill](https://github.com/wimi321/recurring-loop-runner-skill)
