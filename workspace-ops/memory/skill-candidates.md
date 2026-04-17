# Skill Candidates

Track repeated workflows that may deserve promotion into skills, templates, or reusable job patterns.

## Promotion rule
Promote a workflow candidate when all of the following are true:
1. It appeared at least 2 times in recent work.
2. It has 3 or more stable steps.
3. Erick corrected wording, logic, or output shape at least once.
4. Reuse would reduce future error rate or setup time.

## Candidate template
- Name:
- Trigger:
- Repeated evidence:
- Stable steps:
- Reusable artifact type: skill / cron prompt template / checklist / note
- Current status: observing / ready / promoted

## Active candidates

### 1. sentinel-report-hardening
- Trigger: When a cron/sentinel report is being designed, revised, or prepared for production sending.
- Repeated evidence: Negative inventory sentinel iteration, SKU sentinel wording and scope adjustments.
- Stable steps:
  1. Lock business metric and ranking logic.
  2. Validate archived JSON and runtime cron prompt separately.
  3. Run preview-only verification before any production send.
  4. Confirm delivery target and production wording.
  5. Archive final prompt and push showcase updates if needed.
- Reusable artifact type: skill + checklist
- Current status: ready

### 2. feishu-production-send-guard
- Trigger: When working on Feishu group reports, previews, or scheduled pushes.
- Repeated evidence: Need to distinguish preview versus confirmed production send.
- Stable steps:
  1. Mark output mode as preview-only or production-approved.
  2. Never send to production groups during debugging.
  3. Require explicit confirmation before production send.
  4. Keep preview delivery in DM or local output only.
- Reusable artifact type: checklist / policy note
- Current status: ready
