# Module 3: Build Mode and Plan Mode

Lovable has two complementary working modes. The current interface calls them Build and Plan. Some official pages and older project history may use Agent mode for Build and Chat mode for Plan.

> Follow along in the editor: [Open Lovable and try Build and Plan modes](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Choose the correct mode for a task
- Create, review, and approve implementation plans
- Give Build mode useful constraints and verification instructions
- Understand prompt queues, stopping, undo, and credit behavior

## 1. Plan mode

Plan mode is for thinking without code changes. It can inspect project files, logs, and other context, ask clarifying questions, compare approaches, investigate bugs, and produce a structured implementation plan.

Use Plan mode for:

- Product discovery and user-flow decisions
- Architecture, schema, and integration choices
- Understanding existing code
- Root-cause investigation
- Reviewing a risky change before implementation
- Comparing cost, security, or maintenance tradeoffs

Plan mode never modifies code. Each Plan message currently costs one credit.

### Plans and approval

When there is a concrete implementation to propose, Plan mode can create a dedicated plan. Review and edit it before approval. An approved plan is saved to `.lovable/plan.md`, Lovable switches to Build mode, and implementation begins from that approved version.

Earlier plans remain in chat history even though only the latest approved plan is stored in the file.

Useful planning prompt:

```text
Plan a secure team invitation flow for this app.

Requirements:
- Existing admins can invite by email
- Invites expire after 72 hours
- Duplicate active invites are blocked
- New users choose a password after accepting
- Every server-side action is authorized

Inspect the current auth and database setup. Ask questions where product
behavior is unclear. Produce a plan with schema changes, access policies,
UI states, email behavior, tests, migration risks, and rollout order.
Do not modify code.
```

## 2. Build mode

Build mode implements changes directly. It explores the codebase, edits files, can use tools, investigates errors, and reports diffs and results. Cost is usage-based and depends on complexity, codebase exploration, files changed, and verification tools used.

Use Build mode for:

- Adding or changing features
- Fixing a confirmed bug
- Refactoring coordinated files
- Applying an approved plan
- Running requested tests or browser checks
- Verifying backend functions and user flows

Strong Build prompt:

```text
Implement the approved invitation plan.

Guardrails:
- Preserve the existing login flow
- Do not change the shared navigation component
- Keep all privileged operations server-side
- Add or update RLS policies with the schema migration
- Add frontend tests for validation and an edge test for authorization
- After implementation, run the tests and use browser testing on the invite flow
```

## 3. A practical mode decision

| Situation | Mode |
| --- | --- |
| "What are my options?" | Plan |
| "Why does this fail? Investigate only." | Plan |
| "Create a schema and let me review it." | Plan |
| "Implement this approved design." | Build |
| "Fix the reproduced mobile bug." | Build |
| "Run tests and verify checkout." | Build |

For a small, obvious change, go directly to Build. For a broad or high-risk request, plan first.

## 4. Execution controls

### Task visibility

Build mode shows current tasks, files, tools, and progress in a Details view. Use this to notice unexpected scope or repeated failures.

### Prompt queue

You can send more prompts while Build mode is working. They enter a visible queue and run one at a time. Queue items can be paused, reordered, edited, copied, removed, or repeated.

Do not queue dependent instructions in an ambiguous order. Each prompt should state what prior outcome it depends on.

### Stop and undo

Stopping a Build request halts the current task but keeps changes already made. Charges are based on completed work. Use undo or version history if you want to remove those changes.

### File references

Use `@` to reference a file or project. In the code editor, you can also reference exact lines. Focused references reduce exploration and make the request easier to review.

## 5. Recommended operating rhythm

1. Plan the behavior and risks.
2. Review or edit the plan.
3. Approve and build one milestone.
4. Inspect the diff and preview.
5. Test in a separate follow-up request.
6. Return to Plan mode if the result exposes a product or architecture question.

Separating a large build from browser testing is especially useful because browser verification is slower and can get stuck. Build first, then explicitly test the finished flow.

## Practice

In your reading-list project:

1. Ask Plan mode how to add persistent multi-user lists securely.
2. Require a schema, RLS rules, UI states, and test plan.
3. Edit one assumption in the generated plan.
4. Approve only the first milestone.
5. Review Build mode's changed files and summary.
6. Ask for verification in a new prompt.

## Checklist

- [ ] I use Plan mode for decisions and Build mode for execution
- [ ] I review generated plans before approval
- [ ] I add guardrails around sensitive or stable areas
- [ ] I inspect diffs instead of trusting the preview alone
- [ ] I understand that Stop keeps completed changes
- [ ] I use separate build and verification prompts for large work

## Official references

- [Brainstorm in Plan mode](https://docs.lovable.dev/features/plan-mode)
- [Implement changes in Build mode](https://docs.lovable.dev/features/agent-mode)
- [Credits and usage](https://docs.lovable.dev/introduction/credits-and-usage)
- [Test your app in a browser](https://docs.lovable.dev/features/browser-testing)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 4 - Editing, Knowledge, and Iteration](module-04-editing-and-refining.md)
