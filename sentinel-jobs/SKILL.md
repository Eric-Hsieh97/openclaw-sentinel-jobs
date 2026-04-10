---
name: sentinel-jobs
description: Build, document, and adapt OpenClaw sentinel-style monitoring jobs that run on cron schedules, query business data, format a fixed report, and deliver results to chat channels such as Feishu. Use when creating or showcasing AI-driven watchdog, alerting, daily report, inventory watch, SKU watch, sentiment monitoring, or other schedule + query + rules + delivery automations.
---

# Sentinel Jobs

## Overview

Use this skill to package OpenClaw cron-driven monitoring projects as reusable sentinel patterns. The core pattern is: scheduled run, data query, rule filtering, formatted report, then channel delivery.

## Core Pattern

A sentinel job in OpenClaw usually has these parts:

1. **Scheduler**
   Use an OpenClaw cron job with a fixed `cron` expression and explicit time zone.

2. **Executor**
   Set `payload.kind` to `agentTurn` and describe the task in natural language.

3. **Data Layer**
   Query the upstream system, often Microsoft Fabric, inside the prompt.

4. **Rule Layer**
   Encode business scope, exclusions, ranking logic, and output constraints directly in the prompt.

5. **Delivery Layer**
   Send the formatted result to the target channel, such as a Feishu group.

## When This Pattern Works Best

Use this pattern when the workflow is:

- repetitive
- scheduled
- rule-based
- output-oriented
- easy to verify from a final report

Good examples:

- negative inventory watch
- SKU coverage watch
- social media sentiment summary
- daily operations digest
- exception alerting
- fixed-format business reporting

## Build Workflow

### 1. Define the business question

Write the monitoring goal in one sentence.

Examples:

- Which retail stores have the most serious negative inventory today?
- Which stores have the highest and lowest SKU coverage today?
- What social media notes need attention today?

### 2. Lock the scope

Define what must be included and excluded before building the job.

Typical scope items:

- valid business entities
- excluded store types
- excluded channels
- ranking rules
- top-N vs full list output

### 3. Fix the output shape

Decide the exact report structure before tuning the SQL.

Typical output sections:

- title
- date
- summary
- ranked list or full list
- short management suggestion

### 4. Encode the job prompt

Put the operating rules directly into the `payload.message` text.

The prompt should specify:

- project name
- data source
- exclusions
- ranking logic
- exact output structure
- whether silent skip is allowed
- an example SQL query when helpful

### 5. Configure delivery

Set the delivery channel explicitly. In multi-channel environments, do not rely on ambiguous defaults.

## Design Rules

- Prefer one sentinel job per business question.
- Keep output structure stable so stakeholders learn how to read it.
- Put fragile business rules in the prompt, not only in verbal memory.
- Redact delivery targets, credentials, and internal identifiers before publishing examples.
- Publish showcase configs, not production secrets.

## Files to Publish in a Showcase Repo

A minimal showcase can include:

- one `SKILL.md`
- one or more redacted example job JSON files
- one short reference note describing the architecture pattern

## Reference Files

Read `references/examples.md` for sample sentinel job structures and publication guidance.
