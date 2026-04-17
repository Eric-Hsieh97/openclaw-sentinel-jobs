# HEARTBEAT.md

## Self-improvement loop for Jarvis

When a heartbeat arrives, do the following in order, but keep the whole pass lightweight:

1. Check whether recent sessions in the last 1-3 days contain repeated multi-step tasks that were completed successfully.
2. If a repeated workflow appears at least twice, summarize it into a candidate reusable pattern.
3. If the pattern is strong enough, update or create a skill/config/workspace note that helps future execution.
4. Update memory with:
   - what pattern was observed
   - what was improved
   - what should be remembered about the user or workflow
5. Do not make speculative or risky changes. Prefer prompt/config/workflow improvements over large framework changes.
6. Do not send proactive user messages unless there is a high-value result worth reporting.

Priority improvement targets:
- repeated business reporting workflows
- repeated Feishu automation workflows
- repeated Fabric query/report patterns
- repeated formatting corrections from Erick

If nothing clear is found, reply HEARTBEAT_OK.
