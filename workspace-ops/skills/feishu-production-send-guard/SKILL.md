---
name: feishu-production-send-guard
description: Protect Feishu production chats from accidental debug, preview, or unapproved sends. Use when preparing, previewing, validating, or sending content to Feishu groups or DMs, especially for cron jobs, scheduled reports, business announcements, or any workflow where preview-only versus production send must be clearly separated.
---

# Feishu Production Send Guard

Use this skill whenever Feishu output could accidentally reach a production audience.

## Core rule
Default to preview-only unless Erick explicitly confirms:
1. the target
2. the exact content
3. permission to send

## Preview-only mode
Preview-only means:
- return content in the current DM/chat only
- do not send to production groups
- do not treat a manual validation run as approval to send
- do not use user-identity send tools until content and target are explicitly confirmed

## Production send mode
Production send is allowed only after explicit confirmation of:
- target group or recipient
- exact final wording/content
- send approval

## Non-negotiable rules
- Never send debug output to a production Feishu group.
- Never assume a manual cron run is safe to deliver to production.
- Never send "almost final" content to test in a live production group.
- If there is ambiguity, stay in preview-only mode.

## When working on cron or sentinel jobs
- validate SQL directly first
- validate archived JSON and runtime config separately
- show preview in DM first
- only after confirmation should production delivery be considered

## References
- `references/send-checklist.md`
- `references/modes.md`
- `references/common-failures.md`
