---
name: sentinel-report-hardening
description: Harden scheduled sentinel or cron-based business reports before production rollout. Use when creating, revising, validating, or debugging recurring reports that query business data and send formatted output to Feishu or other chat channels, especially when ranking logic, wording, runtime prompt drift, preview-vs-production safety, or cron delivery correctness matter.
---

# Sentinel Report Hardening

Use this skill when a scheduled business report is close to production or already running and needs to be made safer, clearer, and more repeatable.

## Core workflow

1. Lock the business logic.
2. Lock the output contract.
3. Validate the source data directly.
4. Validate runtime configuration separately from archived JSON.
5. Use preview-only verification during debugging.
6. Require explicit confirmation before any production send.
7. Archive the final prompt/config after confirmation.

## Non-negotiable rules

- Never send debugging or preview content to a production group.
- Treat manual runs as preview-only unless the user explicitly approves production sending.
- Do not assume archived config equals runtime config.
- If the source query fails, do not reuse historical output.
- If wording matters to the user, preserve the exact confirmed phrasing.

## What to validate every time

Read this checklist before enabling or modifying a production report:
- `references/production-checklist.md`

## Common failure modes

- The SQL logic is correct, but the runtime cron payload is stale.
- Archived JSON is updated, but the live job still uses an older prompt.
- The ranking logic is changed, but the summary sentence still reflects the old metric.
- Preview content is accidentally delivered to a production group.
- The data table is readable sometimes but flaky due to freshness or file issues.

## Prompt hardening pattern

When hardening a sentinel prompt, make sure the prompt explicitly states:
- the exact business metric
- the ranking order and tie-break rule
- the exact output structure
- preview/debug safety expectations when relevant
- what to do if the query fails
- whether to use natural date or business date

## Runtime verification pattern

For a production cron/sentinel job, verify all of the following separately:
- archived config file
- live cron payload
- delivery target
- timezone and schedule
- isolation/light-context settings
- actual preview result from the live runtime

## References

- `references/production-checklist.md`
- `references/preview-mode.md`
- `references/skill-promotion.md`
