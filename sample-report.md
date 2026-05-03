# Sample Backend AI Production Audit Report

Client: Sample AI SaaS
Date: TODO_DATE
System: AI workflow automation backend

## Executive Summary

The system is viable for an MVP, but production risk is concentrated in AI workflow tracing, queue idempotency, and rollback readiness.

## Top Risks

| Rank | Risk | Severity | Effort | Business Impact |
| --- | --- | --- | --- | --- |
| 1 | AI workflow state is not traceable across retries and tool calls | High | Medium | Failed automations cannot be debugged quickly |
| 2 | Queue jobs are not idempotent | High | Medium | Duplicate actions or inconsistent data |
| 3 | No tested rollback plan | High | Low | Longer downtime during bad deploys |
| 4 | Missing rate limits on expensive AI routes | Medium | Low | Cost spikes and abuse exposure |
| 5 | Slow queries are not monitored | Medium | Medium | Latency growth without early warning |

## 7-Day Fix Plan

Day 1: Add workflow execution IDs and structured AI logs.

Day 2: Add prompt/model/tool-call metadata to execution records.

Day 3: Add idempotency keys to the highest-risk queue jobs.

Day 4: Add failed-job visibility and replay notes.

Day 5: Document deploy and rollback path.

Day 6: Add route/job/provider latency dashboards.

Day 7: Review fixes, test failure paths, and update incident runbook.

## Optional Sprint

Scope a focused implementation sprint around the top-ranked risks after the audit is complete.

