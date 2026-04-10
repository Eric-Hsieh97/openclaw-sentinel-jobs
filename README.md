# OpenClaw Sentinel Jobs Showcase

A lightweight showcase of production-style OpenClaw sentinel jobs built around cron scheduling, natural-language task payloads, Fabric SQL querying, and Feishu delivery.

## Included examples

- `inventory-negative-stock-watch.json`  
  Daily negative inventory sentinel for retail stores only.
- `inventory-sku-watch-v2.json`  
  Daily SKU coverage sentinel for retail stores.

## What these examples demonstrate

- Using OpenClaw cron jobs as the runtime container
- Driving workflows with natural-language `agentTurn` payloads
- Querying Microsoft Fabric from within OpenClaw
- Sending scheduled business reports to Feishu groups
- Building reusable "sentinel" style monitoring projects without writing a full standalone service

## Architecture pattern

1. **Scheduler**: OpenClaw cron triggers the job on a fixed schedule
2. **Executor**: OpenClaw agent receives the payload as an isolated run
3. **Data layer**: Agent queries Microsoft Fabric
4. **Logic layer**: Prompt enforces business rules, scope, exclusions, and output format
5. **Delivery**: Final formatted report is announced to Feishu

## Notes

- Sensitive identifiers have been redacted
- These are showcase configs, not direct production drop-ins
- Real deployments still require valid channel configuration, credentials, data access, and environment-specific tuning

## Why publish this

This repo is intended to show a practical pattern for AI-driven operational monitoring:
**schedule + data query + rule logic + formatted output + delivery**.

