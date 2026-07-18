# Module 10: Debugging, Testing, and Security

Debugging is the process of turning an observed failure into a reproducible case, finding its root cause, making the smallest correct fix, and proving the behavior stays fixed.

## Learning goals

- Investigate in Plan mode before editing fragile code
- Use browser testing, frontend tests, direct edge calls, and edge tests correctly
- Read console, network, build, and backend signals
- Run and interpret Basic and Deep security scans
- Build a repeatable incident and regression workflow

## 1. Describe the failure precisely

A useful report contains:

- Expected behavior
- Actual behavior
- Exact steps to reproduce
- User role and authentication state
- Page, device, and viewport
- Error text and approximate time
- Whether the issue occurs in preview, production, or both
- Last known working version

```text
In production, a club member sees a blank page after opening /clubs/alpha/books/42.
Expected: the book detail page.
Actual: white page after the loading skeleton.
Reproduces on iPhone width and desktop, but only for members, not owners.
Started after today's note-visibility update. Investigate in Plan mode.
Do not change code yet.
```

## 2. Investigate before changing code

Plan mode can inspect code, logs, and context without modifying files. Ask it to:

1. Reproduce or locate the failure.
2. Identify the first bad signal, not just the final symptom.
3. Compare the failing and working roles or environments.
4. State the likely root cause with evidence.
5. Propose a narrow fix and regression test.

Avoid broad repair prompts such as "nothing works, fix it."

## 3. Choose the right verification tool

| Tool | Best for |
| --- | --- |
| Browser testing | Real user flows, routing, auth, visual behavior, timing, and state |
| Frontend tests | Fast, repeatable UI rules and regressions |
| Direct edge-function call | Isolating backend behavior with specific inputs |
| Edge tests | Preserving backend authorization and business rules over time |
| Build, typecheck, lint | Compile, type, import, and static-quality failures |

### Browser testing

Lovable can click, type, navigate, submit forms, capture screenshots, inspect console and network activity, and test multiple screen sizes in a remote browser.

It has limits: canvas interactions, complex file uploads, drag-and-drop, clipboard actions, subtle color judgments, and icon-only controls may be unreliable. Signed-in browser testing currently requires Lovable Cloud; external auth setups can be tested only on public pages.

Build first, then test in a follow-up request for large changes.

### Frontend tests

Lovable's documented stack uses Vitest, React Testing Library, and jsdom. Use frontend tests for forms, filters, conditional rendering, state transitions, and fixed regressions. Test user-visible behavior, not implementation details.

### Backend verification

Call an edge function directly to isolate inputs, auth, and response behavior. Then add edge tests for rules that must remain correct. Test valid, unauthorized, malformed, duplicate, boundary, and failure cases.

## 4. Observe the whole request path

For frontend failures, inspect:

- Browser console errors
- Failed network requests and status codes
- Request payloads and response bodies without exposing secrets
- Route parameters and application state
- Loading and error boundaries

For backend failures, inspect:

- Edge-function logs
- Auth claims and authorization checks
- Database errors and RLS denials
- External API status, timeout, and rate-limit behavior
- Secret presence by name, never value

## 5. Fix and prove

```text
Implement the narrow fix identified in the plan.

Guardrails:
- Preserve owner behavior and current note privacy rules
- Do not weaken RLS or bypass authorization in the client
- Add a regression test for member access to book details
- Run the focused frontend test and existing related tests
- Then use browser testing as owner, member, and non-member
- Report changed files, test results, and remaining risk
```

If the fix requires a broad workaround or disabling security, stop and revisit the root cause.

## 6. Security scans

Open More -> Security. The project Security view brings together built-in findings and optional security connectors.

- Basic scan checks database configuration, RLS, schema access, and dependencies.
- Deep scan performs a more detailed agentic code review for access control, exposed secrets, unprotected endpoints, unsafe input handling, and related risks.

Both scans are currently free. Deep scans do not run automatically. Run scans before publishing, after meaningful code or database changes, after dependency updates, and periodically for production apps.

Scan results are tied to a project version. Any later change can make them outdated.

Prioritize findings:

1. Exposed secrets or public privileged endpoints
2. Missing or overly broad RLS
3. Authentication and authorization bypasses
4. Injection and unsafe input handling
5. Vulnerable dependencies
6. Lower-risk hardening recommendations

Never fix a scan finding by hiding the UI while leaving the underlying operation accessible.

## 7. Regression and incident routine

1. Record the production version and time.
2. Reproduce with the least-privileged relevant role.
3. Contain severe impact by reverting and republishing if necessary.
4. Investigate the root cause in Plan mode.
5. Add a failing regression test.
6. Implement the smallest correct fix.
7. Run focused and surrounding tests.
8. Verify in preview and production.
9. Refresh security scans.
10. Document the cause and prevention in project knowledge or an issue.

## Practice

Create three deliberate failures in a disposable project: a broken route, a client validation regression, and an authorization failure. For each, write a bug report, choose the correct tool, fix it, and add a regression test.

## Official references

- [Test and verify your app](https://docs.lovable.dev/features/testing)
- [Browser testing](https://docs.lovable.dev/features/browser-testing)
- [Debugging prompts](https://docs.lovable.dev/prompting/prompting-debugging)
- [Project security view](https://docs.lovable.dev/features/security-view)
- [Security overview](https://docs.lovable.dev/features/security)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 11 - Advanced Prompt Patterns](module-11-advanced-prompt-patterns.md)
