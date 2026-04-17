# Production Checklist

## Business logic
- Confirm the metric definition.
- Confirm ranking and tie-break rules.
- Confirm inclusion and exclusion scope.
- Confirm date logic.

## Output contract
- Confirm title.
- Confirm summary wording.
- Confirm columns and ordering.
- Confirm management advice wording.
- Confirm desired format: text, pseudo-table, or document.

## Data validation
- Run the real SQL directly.
- Check freshness fields.
- Re-run once to detect flaky failures.
- Confirm there is no partial table/read failure.

## Runtime validation
- Archived JSON correct.
- Live cron payload correct.
- Delivery target correct.
- Schedule and timezone correct.
- Isolation settings correct.

## Safety gate
- Preview-only during debugging.
- Explicit approval before production send.
- No fallback to historical output when current query fails.

## Archive
- Commit final config.
- Push branch/repo updates when needed.
- Record the lesson in memory.
