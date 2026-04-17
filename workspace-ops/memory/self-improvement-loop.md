# Self Improvement Loop

## Goal
Make OpenClaw behave closer to a built-in learning agent without modifying the core framework first.

## Mechanisms

### 1. Built-in learning loop (workspace-level)
Use heartbeat to periodically inspect recent successful work and turn repeated workflows into reusable assets.

### 2. Automatic skill generation from experience
When the same workflow appears multiple times and has stable steps, convert it into one of:
- a skill
- a cron prompt pattern
- a reusable note in workspace docs
- a template/query snippet

### 3. Skill improvement during use
When Erick corrects wording, output shape, ranking logic, or business rules, treat that as training data for the workflow.
Push the correction into:
- active cron prompt
- archived config JSON
- public GitHub showcase repo when relevant

### 4. Persistent memory / user model
Store stable preferences such as:
- Erick prefers direct, structured output
- group messages must not leak internals
- for operations reports, wording and ranking logic matter heavily
- do not send test/debug content to production groups without explicit confirmation

## Current learned lessons
- For Feishu production groups, never send debugging or preview content without explicit confirmation.
- For sentinel jobs, the runtime prompt must be checked separately from archived JSON files.
- For business reports, Erick often iterates on wording, ranking logic, and readability after seeing concrete output.
- When a report is customer/business-facing, prefer exact confirmed phrasing over approximate compliance.

## Candidate future upgrades
- Create a dedicated skill for operational report prompt hardening.
- Add a reusable validation checklist before enabling production cron jobs.
- Add a reusable "preview only, no group send" mode for sentinel debugging.
