# Sentinel Production Validation Checklist

Use this before enabling or modifying any production cron/sentinel job.

## 1. Business logic lock
- Confirm the metric definition is exact.
- Confirm ranking logic is exact.
- Confirm tie-break logic is exact.
- Confirm inclusion/exclusion scope is exact.
- Confirm whether the date should use natural date or business date.

## 2. Output contract lock
- Confirm the final title.
- Confirm summary wording.
- Confirm column names and ordering.
- Confirm management advice wording.
- Confirm whether output should be plain text, pseudo-table, or document/table.

## 3. Data validation
- Run the real SQL directly.
- Check latest business_day or relevant freshness field.
- Confirm the table is readable and not partially broken.
- Re-run once to detect flaky failures.

## 4. Runtime validation
- Archived JSON correct.
- Runtime cron payload correct.
- Delivery target correct.
- Timezone and schedule correct.
- If using agentTurn, verify lightContext or other isolation setting.

## 5. Safety gate
- Preview-only by default during debugging.
- Never send test content to production groups.
- Require explicit approval before first production send after changes.
- If the source query fails, do not fallback to old results.

## 6. Archive
- Commit final config.
- Push showcase or repo updates if relevant.
- Record lessons learned in memory.
