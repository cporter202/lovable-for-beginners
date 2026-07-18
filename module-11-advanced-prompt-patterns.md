# Module 11: Advanced Prompt Patterns

Advanced prompting is less about clever wording and more about structuring work so Lovable can investigate, decide, implement, and verify without losing the important constraints.

> Try each advanced pattern in context: [Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Use prompts for audits, migrations, refactors, and staged delivery
- Combine knowledge, skills, references, and subagents
- Define invariants and rollback points for risky work
- Review AI output as evidence, not authority

## Pattern 1: Read-only audit

Use Plan mode when you need findings before changes.

```text
Audit the current authentication and authorization system without changing code.

Trace:
- Sign-up, sign-in, sign-out, password reset, and Google OAuth
- Session loading and protected routing
- Every database policy for user-owned data
- Every edge function that depends on identity

Return:
- A diagram of the current flow
- Findings ordered by severity
- Evidence with file or policy references
- A minimal remediation plan
- Tests that would prove each fix
```

## Pattern 2: Invariants for fragile changes

An invariant is behavior that must remain true.

```text
Add organization switching while preserving these invariants:
- A user never reads data from an organization they do not belong to
- Existing single-organization accounts continue to work
- Refreshing preserves the active organization
- Server-side operations derive authorization from the session
- Current email and Google sign-in flows are unchanged

Inspect the implementation first. If any invariant conflicts with the current
architecture, stop and explain before changing code.
```

## Pattern 3: Staged migration

For schema or architecture changes, separate additive, backfill, switch, and cleanup stages.

```text
Plan the migration from a single `name` column to `first_name` and `last_name`.
Use four reversible stages:
1. Additive schema and compatibility reads
2. Backfill with verification queries
3. Switch writes and UI
4. Remove old behavior only after validation

For each stage include rollback, data checks, affected files, and tests.
Do not combine destructive cleanup with the initial deployment.
```

## Pattern 4: Vertical slices

Build one complete user outcome across UI, data, authorization, and tests before starting the next.

```text
Implement only the "create club" vertical slice:
- Form and validation
- Server-side creation
- Owner membership
- RLS
- Loading, duplicate, success, and failure states
- Frontend and edge tests
- Browser verification

Do not implement invitations, books, or notes yet.
```

## Pattern 5: Evidence-based debugging

```text
Investigate the intermittent duplicate order issue.
Do not propose a fix until you have:
- A reproducible sequence or strongest available evidence
- The request path from click to database write
- Any retry, timeout, webhook, or double-submit behavior
- The database constraints that should prevent duplication

Separate confirmed facts, likely causes, and unknowns.
```

## Pattern 6: Cross-project reuse

```text
Use @MainApp as a read-only reference.
Reuse its accessible form field and error-summary pattern in this project,
but keep this project's colors, routes, dependencies, and data model.
List what you copied or adapted and confirm @MainApp was not modified.
```

## Pattern 7: Parallel investigation with subagents

Lovable may use temporary read-only subagents for focused research and code exploration. They cannot edit files. The main agent combines their findings and makes changes.

```text
Use subagents to investigate this dashboard slowdown:
- One should trace data fetching and database queries
- One should inspect rendering and state updates
- One should review bundle and asset costs
- One should compare the current behavior with our performance requirements

Combine the evidence into a prioritized plan. Do not change code yet.
```

Subagents start with only the context Lovable gives them, so include important scope and constraints in the main request.

## Pattern 8: Reusable workspace skills

Skills are on-demand playbooks available across a workspace. Use them for repeatable workflows such as launch reviews, accessibility passes, release notes, or security handoffs. They can be invoked with a slash command or selected automatically when the description matches.

Knowledge should contain always-on rules. A skill should contain a task-specific procedure.

Example release skill content:

```text
When preparing a release:
1. Identify the version being shipped and user-visible changes.
2. Run focused tests, build, typecheck, and browser verification.
3. Run current Basic and Deep security scans.
4. Review metadata and SEO/AEO findings.
5. Confirm rollback point and production owner.
6. Return a go/no-go decision with evidence and unresolved risks.
```

Workspace owners and admins manage custom skills. Skills can be written, built with Lovable, imported from GitHub or ZIP, or saved from a successful chat workflow.

## Pattern 9: Review against acceptance criteria

```text
Review the implementation against the approved plan and acceptance criteria.
Do not make changes.

For each criterion report Pass, Fail, or Not verified, with evidence.
Then list regressions, security concerns, missing tests, and scope drift.
```

## Practice

Choose one real feature and produce: a read-only audit, an invariant list, a staged plan, one vertical-slice implementation prompt, and a final evidence-based review.

## Official references

- [Plan mode](https://docs.lovable.dev/features/plan-mode)
- [Subagents](https://docs.lovable.dev/features/subagents)
- [Workspace skills](https://docs.lovable.dev/features/skills)
- [Knowledge](https://docs.lovable.dev/features/knowledge)
- [Cross-project referencing](https://docs.lovable.dev/features/cross-project-referencing)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 12 - Performance, SEO, and Operations](module-12-performance-and-optimization.md)
