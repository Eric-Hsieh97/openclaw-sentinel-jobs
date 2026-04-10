# Sentinel Job Examples

## Included examples

- `../inventory-negative-stock-watch.json`
- `../inventory-sku-watch-v2.json`

These JSON files show the practical OpenClaw cron-job shape used by sentinel projects.

## What is intentionally redacted

The showcase examples do not include:

- real Feishu group targets
- credentials or tokens
- runtime state
- job ids
- timestamps

## Recommended publication style

When publishing sentinel projects publicly:

1. Keep the business problem visible
2. Keep the job structure visible
3. Keep the prompt engineering visible
4. Remove production routing details
5. Remove all private identifiers and secrets

## Suggested repo structure

```text
repo/
  SKILL.md
  references/
    examples.md
  inventory-negative-stock-watch.json
  inventory-sku-watch-v2.json
```

## Notes on reuse

These examples are best treated as:

- architecture patterns
- prompt templates
- cron configuration references

They are not intended to be direct one-click production deployments.
