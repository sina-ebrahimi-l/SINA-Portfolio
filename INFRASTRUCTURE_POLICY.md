# Infrastructure & Cost Policy

**Status:** Active  
**Effective:** 2026-09-28  
**Scope:** This repository and any runtime, CI/CD, database, storage, queue, worker, preview, or deployment infrastructure it uses.

## Current infrastructure baseline

Sina Ebrahimi now operates an owned server with **Coolify + Docker** available as shared infrastructure for the product ecosystem.

This changes the default infrastructure decision. Paid managed services are no longer the automatic answer when a project encounters execution limits, quotas, collaboration/paywall restrictions, runtime limits, or rising usage cost.

GitHub remains the canonical source of truth for source code, history, review, and project documentation. Coolify/the owned server is an available execution and deployment target.

## Cost-first rule

When this project hits any of the following:

- paid-plan requirement;
- usage/runtime/build-minute limit;
- project/seat/collaborator limit;
- deployment or preview restriction;
- database/project-slot limit;
- worker/cron/queue execution limit;
- storage/bandwidth cost that grows materially with usage;
- a SaaS feature that can be provided reliably by the owned infrastructure;

the **first option to evaluate is the owned server/Coolify infrastructure**, before upgrading the external SaaS plan.

Do not purchase or recommend a paid tier merely to remove a platform limit until the self-hosted alternative has been evaluated for technical fit, operational risk, migration cost, backup/recovery requirements, and expected savings.

## Migration priority

Infrastructure migration is **need-driven, not migration-for-migration's-sake**.

Priority order:

1. New capabilities whose purpose depends on the owned server or that remove an immediate blocker/cost.
2. Projects not yet in production, where moving before launch avoids later migration risk.
3. Services approaching a real quota, execution, collaboration, or cost limit.
4. Stable production services that are already inexpensive and working reliably.

A stable production service must not be moved merely because self-hosting is possible. Migrate it when there is a measurable benefit or a platform constraint.

## GitHub Actions policy

Target architecture:

```text
GitHub = source of truth / review / CI tests
Coolify + owned server = primary deployment/runtime path where appropriate
```

GitHub Actions should be minimized and used primarily for tests, linting, validation, or other CI work that genuinely benefits from it.

**Important:** this is a target policy, not a claim that every repository has already migrated. Do not delete or disable an existing production deployment workflow until the replacement Coolify/server path is implemented, tested, observed, and explicitly accepted.

When GitHub-hosted Actions cost/minutes become a constraint, evaluate server-side execution/self-hosted CI before increasing recurring Actions spend.

## Managed-service policy

Managed services such as Supabase, Cloudflare, Vercel, or similar providers may remain in use when they are currently the safer, simpler, or cheaper choice.

However:

- Vercel or another paid hosting tier is not a default requirement when Coolify can host the application.
- Supabase paid capacity is not a default requirement solely because a free project/usage limit is reached; first evaluate PostgreSQL/Supabase-compatible self-hosting on owned infrastructure.
- Cloudflare services should be retained where their edge/network/queue/worker role provides real value and the cost remains low.
- Product isolation must be preserved even when multiple products share the same physical server.

## Operational safety

Self-hosting transfers responsibility to us. Any production migration must account for:

- persistent volumes and data durability;
- automated off-server backups;
- restore testing;
- secrets management;
- TLS/domain configuration;
- health checks and restart policy;
- resource limits;
- logging/monitoring;
- upgrade/rollback procedure;
- database security and least privilege.

Do not trade a small SaaS bill for an unbounded reliability or data-loss risk.

## Agent/developer rule

Before introducing a new paid infrastructure dependency or upgrading an existing SaaS plan:

1. identify the exact limit/problem;
2. check whether Coolify/owned-server infrastructure can solve it;
3. compare recurring cost and operational burden;
4. prefer the owned infrastructure when it is technically sound and materially reduces recurring cost;
5. preserve working production systems until the replacement is verified.

Any architecture document that predates 2026-09-28 and assumes Vercel, Supabase Pro, GitHub-hosted deployment, or another paid managed service as the mandatory future path must be interpreted in light of this policy and updated when that area is next changed.
