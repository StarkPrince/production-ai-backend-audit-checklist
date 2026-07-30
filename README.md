# Production AI Backend Audit Checklist

A practical checklist for founders and small engineering teams shipping AI/backend systems into production.

Use this before launching or scaling AI agents, copilots, meeting tools, workflow automations, search/recommendation systems, support tools, or backend-heavy SaaS products.

## What This Covers

- Critical user flows.
- AI/LLM workflow reliability.
- API, auth, RBAC, validation, and rate limits.
- Databases, caches, migrations, and backups.
- Queues, workers, cron jobs, retries, and idempotency.
- Deployment, CI/CD, secrets, and rollback.
- Observability, incident response, and commercial risk.

## Start Here

- [Checklist](./checklist.md)
- [Architecture intake template](./architecture-intake-template.md)
- [Sample audit report](./sample-report.md)

## Who This Is For

This is most useful if you are:

- Preparing an AI/backend product for launch.
- Moving from demo/MVP to production.
- Seeing failures in queues, workers, LLM calls, auth, deployments, or data flows.
- Trying to prioritize backend fixes before fundraising, customer onboarding, or scale.

## How To Use It

1. Score each checklist item as 0, 1, or 2.
2. Mark the top 5 user flows where failure would hurt users, revenue, or trust.
3. Identify categories below 60%.
4. Pick the top 10 risks.
5. Rank each risk by severity, effort, and business impact.
6. Turn the top risks into a 7-day fix plan.

## When To Ask For An External Audit

Consider an external review if:

- You have multiple unknowns across AI workflows, queues, auth, deployment, or observability.
- Your team is close to launch and wants a second pair of production-focused eyes.
- You have had incidents but do not know which fixes matter most.
- Your AI workflows are slow, expensive, unreliable, or hard to debug.

## Backend AI Production Audit

I offer a 7-day Backend AI Production Audit for startups that want a ranked risk map and practical fix plan.

The audit reviews architecture, AI workflows, APIs, databases, queues, auth, CI/CD, observability, and rollback readiness.

CTA:

```text
Book a call at https://cal.com/starkprince. Paid audits are scoped at $80/hour minimum.
```

## Notes

This checklist is not penetration testing, compliance certification, or a substitute for your own engineering judgment. It is a production-risk review framework.
