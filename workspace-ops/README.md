# Self-Improving Agent Ops

This folder captures a lightweight, workspace-level implementation of Hermes-style agent improvement patterns using OpenClaw primitives.

## Included capabilities
- heartbeat-driven learning loop
- recurring workflow to skill-candidate promotion
- sentinel production validation checklist
- preview-only versus production-send guardrails
- reusable hardening skills for scheduled reports and Feishu production sending

## Structure
- `HEARTBEAT.md` - periodic self-improvement loop trigger
- `memory/` - long-term operational learning and skill candidates
- `references/` - production validation checklist
- `skills/sentinel-report-hardening/` - reusable skill for cron/sentinel report hardening
- `skills/feishu-production-send-guard/` - reusable skill for safe Feishu production sending

## Why this matters
This shows how to approximate built-in learning, skill generation, skill refinement, and persistent user/workflow modeling on top of OpenClaw without first changing the core framework.
