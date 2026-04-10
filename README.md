# OpenClaw Sentinel Jobs

Production-style showcase for building **AI-driven sentinel jobs** with **OpenClaw cron**, **natural-language task payloads**, **Microsoft Fabric queries**, and **Feishu delivery**.

This repository demonstrates a lightweight but practical enterprise automation pattern:

> **schedule + query + business rules + formatted report + channel delivery**

---

## What is inside

### Included showcase jobs
- **Negative Inventory Sentinel**  
  Daily 10:00 monitoring job that identifies the most serious negative inventory stores and pushes a concise morning report.

- **SKU Coverage Sentinel**  
  Daily 10:00 monitoring job that ranks retail stores by SKU coverage and delivers a structured store report.

### Included skill structure
- `sentinel-jobs/SKILL.md`  
  A reusable OpenClaw skill-style abstraction for documenting and designing sentinel projects.

- `sentinel-jobs/references/examples.md`  
  Notes on publication style, reuse boundaries, and example structure.

---

## Why this repo exists

Many AI demos stop at chat.

This repo focuses on a more useful operational pattern:
- run on schedule
- pull real data
- apply business rules
- generate a fixed report
- deliver it automatically to the right channel

That makes it suitable for:
- watchdog jobs
- morning reports
- exception alerts
- retail monitoring
- ops summaries
- sentiment monitoring

---

## Architecture pattern

```text
OpenClaw Cron
    -> agentTurn payload
        -> Microsoft Fabric query
            -> business rule filtering
                -> report formatting
                    -> Feishu delivery
```

This pattern works especially well for workflows that are:
- repetitive
- rule-based
- time-sensitive
- easy to verify from output

---

## Repository structure

```text
.
├── README.md
├── inventory-negative-stock-watch.json
├── inventory-sku-watch-v2.json
└── sentinel-jobs/
    ├── SKILL.md
    └── references/
        └── examples.md
```

---

## Example use cases

### 1. Negative inventory monitoring
Detect stores with serious negative quantity or negative amount issues, rank the highest-risk stores, and send a compact management report.

### 2. SKU coverage monitoring
Track store-level SKU coverage daily and generate a ranked distribution report for operational review.

### 3. Pattern reuse for other domains
The same structure can be reused for:
- delayed process alerts
- document exceptions
- marketing performance summaries
- social listening summaries
- financial anomaly watches

---

## What is redacted

This is a **public showcase**, not a production dump.

The repository intentionally excludes:
- credentials
- private routing targets
- runtime state
- internal IDs
- production environment details
- organization-specific secrets

The published JSON files are **redacted examples**, designed to show the project pattern without exposing operational details.

---

## Design principles behind these jobs

- **One sentinel, one business question**
- **Stable output format** for stakeholder readability
- **Prompt carries the business rules**
- **Schedule is explicit**
- **Delivery target is explicit**
- **Public examples are redacted by default**

---

## OpenClaw angle

These jobs are not implemented as standalone backend services.

Instead, they use OpenClaw as the runtime layer:
- cron for scheduling
- agent turns for execution
- tool calls for data access
- channel delivery for announcements

That keeps the implementation lightweight while still supporting real business workflows.

---

## Notes for adaptation

If you want to reuse this pattern in your own environment:
1. replace the delivery target
2. replace the data query
3. rewrite the business rules
4. fix the report structure
5. validate with a small audience first

---

## Author

Created and published by **Eric Hsieh** as part of ongoing OpenClaw automation practice.
