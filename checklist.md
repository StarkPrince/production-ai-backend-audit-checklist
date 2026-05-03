# Production AI Backend Audit Checklist

Score each item:

- 0: missing or unknown.
- 1: partly handled, but untested or undocumented.
- 2: handled, tested, and owned.

## Critical User Flows

- [ ] Top 5 user flows are listed.
- [ ] Each flow has an owner.
- [ ] Each flow has known success and failure states.
- [ ] External dependencies are visible per flow.
- [ ] Database writes are mapped per flow.
- [ ] Queue jobs or background workers are mapped per flow.
- [ ] AI/LLM calls are mapped per flow.
- [ ] User-facing fallback behavior is defined.
- [ ] Business impact is known if the flow fails.
- [ ] Alerts exist for the highest-risk flows.

## AI Workflow Reliability

- [ ] Every prompt has a version or change history.
- [ ] Model, prompt version, tool calls, latency, and token/cost estimates are logged.
- [ ] Tool inputs and outputs are validated.
- [ ] LLM calls have timeout limits.
- [ ] Retry budgets are explicit.
- [ ] Fallback behavior exists for model/API failure.
- [ ] Expensive workflows have cost caps or throttling.
- [ ] There is a small evaluation set for important AI behavior.
- [ ] Human handoff exists for uncertain or high-risk cases.
- [ ] Abuse and prompt-injection risks have been considered.

## API, Auth, And Data Boundaries

- [ ] All public endpoints validate request bodies and query params.
- [ ] Auth is enforced server-side, not only in the UI.
- [ ] RBAC/tenant boundaries are tested for sensitive routes.
- [ ] Rate limits exist for expensive or abuse-prone routes.
- [ ] Idempotency is used for payment, notification, and job-triggering endpoints.
- [ ] Sensitive fields are not returned accidentally.
- [ ] Secrets are not present in client bundles, logs, or repos.
- [ ] Webhook signatures are verified.
- [ ] Admin-only actions are auditable.
- [ ] Error responses do not leak sensitive internals.

## Data, Database, And Cache

- [ ] Critical tables/collections have clear ownership.
- [ ] Indexes match actual query patterns.
- [ ] Slow queries are visible.
- [ ] Migrations have rollback or recovery plans.
- [ ] Backfills can be resumed safely.
- [ ] Cache invalidation rules are documented.
- [ ] Redis keys have TTLs where appropriate.
- [ ] Data integrity assumptions are enforced in code or schema.
- [ ] Backups exist and restoration has been tested.
- [ ] Analytics/reporting reads cannot overload production paths.

## Queues, Workers, Cron, And Background Jobs

- [ ] Jobs are idempotent or protected against duplicate execution.
- [ ] Retry policy is defined per job type.
- [ ] Failed jobs go to a visible dead-letter path or failure queue.
- [ ] Long-running jobs are isolated from urgent jobs.
- [ ] Worker concurrency is configured intentionally.
- [ ] Job payloads contain enough context to debug failures.
- [ ] Scheduled jobs are monitored.
- [ ] External provider failures are retried with backoff.
- [ ] Replaying a failed job is safe.
- [ ] Queue depth and worker processing time are tracked.

## Deployment, CI/CD, And Rollback

- [ ] Deployment steps are scripted.
- [ ] Environment variables are documented per environment.
- [ ] CI runs tests before deploy.
- [ ] Database migrations are reviewed before deploy.
- [ ] Rollback path is known and recently tested.
- [ ] Deploy markers appear in logs or monitoring.
- [ ] Preview/staging environment matches production enough to catch issues.
- [ ] Build artifacts are reproducible.
- [ ] Secrets are managed outside source control.
- [ ] Ownership is clear when deployment fails.

## Observability And Incident Readiness

- [ ] Request logs include correlation IDs or trace IDs.
- [ ] Errors are grouped and searchable.
- [ ] Latency is visible by route, job, and external provider.
- [ ] AI workflow failures are distinguishable from normal backend failures.
- [ ] Alerts map to business-critical flows.
- [ ] On-call or owner escalation is defined.
- [ ] Incident notes can be written quickly from available logs.
- [ ] There is a basic runbook for the top failure modes.
- [ ] Customer-impacting issues can be identified quickly.
- [ ] Post-incident fixes are tracked.

## Commercial Risk

- [ ] The team knows which failure would block revenue.
- [ ] The team knows which failure would corrupt or lose data.
- [ ] The team knows which workflow has the highest AI/API cost risk.
- [ ] The team knows which launch assumption is least tested.
- [ ] There is a 7-day fix plan for the highest-risk items.

