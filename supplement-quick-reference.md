# Lovable Quick Reference

Current as of July 18, 2026.

## Mode chooser

| Need | Use |
| --- | --- |
| Ask questions, compare options, investigate, or create a plan | Plan mode |
| Generate, edit, fix, refactor, or verify the project | Build mode |
| Inspect or manually edit files | Code editor, paid plans |
| Point at visible UI | Preview toolbar |

Older references may call Plan mode Chat mode and Build mode Agent mode.

## Best prompt structure

```text
Outcome:
What should become true for the user?

Context:
Who is the user, what exists now, and which files or references matter?

Requirements:
- Required behavior
- Required content and states

Constraints:
- What must not change
- Required patterns, security, accessibility, and scope limits

Acceptance criteria:
- Observable checks
- Tests and viewport coverage
```

## First-project prompt

```text
Build [product] for [audience].
The primary user action is [action].

Include [routes/components/workflow].
Use [visual direction, colors, type, density].
Include realistic content and loading, empty, error, success, and mobile states.
Use local sample data only. Do not add [out-of-scope features].
Ask focused questions if any product or design decision is ambiguous.
```

## Plan before a risky change

```text
Inspect the current implementation and plan [change].
Do not modify code.

Preserve:
- [invariants]

Return:
- Current-state summary
- Decisions and tradeoffs
- Affected files and data
- Security and migration risks
- Ordered implementation steps
- Tests and rollback plan
```

## Build safely

```text
Implement the approved plan for [feature].
Change only [scope]. Preserve [stable behavior].
Do not weaken authorization or expose secrets.
Add focused regression tests and run related checks.
Report changed files, test results, and remaining risk.
```

## Debugging prompt

```text
Expected: [behavior]
Actual: [behavior]
Steps: [numbered reproduction]
Role/session: [state]
Environment: [preview or production, device, route]
Started after: [change or version]

Investigate in Plan mode. Separate confirmed facts, likely causes, and unknowns.
Do not change code until the root cause and narrow fix are identified.
```

## Verification prompts

```text
Run the existing frontend tests and add a regression test for [behavior].
```

```text
Call [edge function] directly with valid, unauthorized, malformed,
duplicate, and boundary inputs. Add edge tests for durable rules.
```

```text
Use browser testing on mobile and desktop to verify [user flow].
Inspect screenshots, console errors, and network failures. Report what passed.
```

## Preview toolbar

| Shortcut | Action |
| --- | --- |
| `S` | Select one or more elements and prompt a change |
| `T` | Edit visible text inline |
| `D` | Draw an annotation and send it with a prompt |

Use Add comment to pin collaborative feedback. Cmd or Ctrl-click selects multiple elements.

## Knowledge and references

- Workspace knowledge: always-on standards across projects
- Project knowledge: product, domain, architecture, and brand context for one project
- Skill: task-specific reusable workflow loaded on demand
- `@file`: reference a project file
- Exact line reference: add from the code editor gutter
- `@Project`: read-only reference to an accessible project in the same workspace

## Lovable Cloud checklist

- Choose the correct region before enabling Cloud
- Review Cloud tool permissions
- Plan schema, indexes, relationships, and delete behavior
- Enforce authorization with RLS and server-side checks
- Keep secrets in managed storage and privileged calls in edge functions
- Define file type, size, and storage access rules
- Inspect logs and usage
- Test with multiple users and a signed-out session

## Integration chooser

| Need | Integration |
| --- | --- |
| Deployed app calls a supported service | App connector |
| Each app user connects their own account | App-user connector |
| Lovable reads builder context from tools | Chat connector using MCP |
| Unsupported custom functionality | Custom API through an edge function |

## Pre-publish checklist

- [ ] Critical user flow passes in browser testing
- [ ] Frontend, edge, build, and type checks pass
- [ ] Basic and Deep security scans are current
- [ ] RLS is tested across roles
- [ ] No secrets appear in client code or logs
- [ ] Site title, description, icon, and social image are correct
- [ ] SEO and AI search review is complete
- [ ] A rollback version is identified
- [ ] Production is tested after publishing

Remember: edits are not live until Publish -> Update.

## Current navigation

- Cloud settings: Cloud tab or Connectors -> App connectors -> Lovable Cloud
- Security: More -> Security
- SEO and AI search: More -> SEO & AI search
- Analytics: More -> Analytics
- Domains: Project Settings -> Domains or Publish -> Custom domain
- Credit usage: Settings -> Plans & credit usage
- Project monitoring: Project Settings -> Project monitoring

## Official references

- [Documentation index](https://docs.lovable.dev/llms.txt)
- [Plan mode](https://docs.lovable.dev/features/plan-mode)
- [Build mode](https://docs.lovable.dev/features/agent-mode)
- [Lovable Cloud](https://docs.lovable.dev/integrations/cloud)
- [Testing](https://docs.lovable.dev/features/testing)
- [Publish](https://docs.lovable.dev/features/publish)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)
