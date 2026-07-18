# Troubleshooting Lovable Projects

Use this guide to move from symptom to evidence. Menu names and plan availability are current as of July 18, 2026.

## First response to any issue

1. Decide whether it affects preview, production, or both.
2. Record the route, user role, device, expected result, and actual result.
3. Check whether production needs Publish -> Update.
4. Reproduce in the smallest flow possible.
5. Investigate in Plan mode before editing fragile code.
6. Restore a known working version if impact is severe.

## "Lovable built the wrong thing"

Likely cause: the request described appearance but not the user outcome, behavior, constraints, or states.

Response:

- Select the exact element or reference the file.
- State what is observably wrong.
- Define the target behavior.
- State what must remain unchanged.
- Add acceptance criteria.
- Revert first if the new version is substantially worse.

## "I cannot find Chat, Agent, Visual Edits, or Code Mode"

Current terminology:

- Chat mode became Plan mode.
- Agent mode is generally presented as Build mode, though some docs still say Agent.
- Visual Edits was replaced by the preview toolbar.
- Code Mode is documented as the code editor.

Some controls move into menus on narrow windows, and code editing requires a paid plan.

## "My live site does not show the latest changes"

Publishing deploys a snapshot. Editor changes are not automatic releases.

1. Open Publish.
2. Check for unpublished changes.
3. Click Update.
4. Wait for deployment to finish.
5. Test the live URL in a clean session.
6. Check service-worker or CDN caching only if the updated deployment is confirmed.

## "The app works in preview but not production"

Check:

- Production was updated
- Production environment variables and secrets exist
- OAuth redirect URLs include the live domain
- Connector domain restrictions include the live domain
- Webhook URLs point to production
- Published website access permits the test user
- Database and storage policies allow the production role
- Production logs and network responses

External hosting has separate configuration and cannot be monitored by Lovable infrastructure.

## "A direct link returns 404"

First identify the stack.

- Older React/Vite SPAs on external static hosting need a fallback rewrite to `index.html`.
- TanStack Start SSR projects need a compatible server runtime and route handling.
- Lovable-hosted projects should be checked for a missing route and stale publish snapshot.

Do not add an SPA rewrite to an SSR deployment without inspecting the configuration.

## "Authentication works for one user but not another"

Compare:

- Account confirmation and auth provider
- User role and membership rows
- Session and token state
- RLS policies for the exact operation
- OAuth redirect and allowed origin
- Route guards versus server-side authorization

Test as owner, ordinary member, signed-in non-member, and signed-out visitor. A hidden UI control does not prove the operation is secure.

## "Data is missing or access is denied"

An RLS denial may be correct. Inspect the authenticated user, ownership fields, membership row, and policy conditions.

Use a direct backend call or query to separate UI state from database behavior. Never fix the issue by disabling RLS or adding a universal policy.

## "Data is visible to the wrong user"

Treat this as a security incident.

1. Stop or roll back the affected release and republish if exposure is active.
2. Preserve logs and identify the exposed tables and time window.
3. Test the exact query as multiple roles.
4. Repair RLS and server-side authorization.
5. Run Basic and Deep security scans.
6. Review whether notification or legal obligations apply.

Do not rely on client filters to isolate user data.

## "An API key is visible"

First determine whether it is intentionally publishable. Values in `VITE_` variables are embedded in frontend output.

For a private credential:

1. Revoke or rotate it at the provider immediately.
2. Remove it from code, history where appropriate, logs, and prompts.
3. Store the replacement in managed secrets.
4. Move the call to an edge function or managed connector.
5. Review provider logs for misuse.
6. Run a Deep security scan.

## "The API or connector fails"

Check:

- Connection still exists and has sufficient scopes
- Correct account owns the connection
- Gateway or direct-key model for that connector
- Secret names and server-side availability
- Domain or IP restrictions
- Request schema and endpoint
- 401, 403, 404, 409, 429, and 5xx behavior
- Timeout, retry, pagination, and rate limit
- Disconnect and reconnect behavior

Never print credentials while debugging. Log an operation ID, provider status, and safe metadata.

## "Payments work in preview but not live"

Preview payment flows use a test environment; published apps use live payments after go-live.

Verify:

- Provider account verification is complete
- Products and prices are live and synchronized
- The latest project snapshot is published
- Webhooks reach production and signatures validate
- Users are authenticated and purchases map correctly
- Live domain and redirects are configured
- Access updates are idempotent

Test success, failure, cancellation, duplicate webhooks, refunds, and subscription changes.

## "Cloud cannot be moved to another region"

Cloud region is selected when the project is enabled and cannot be changed for that project. Existing Cloud projects also cannot be moved between regions. Migration requires a new backend project and a planned transfer of schema, data, storage, auth, functions, secrets, and domains.

## "Browser testing cannot complete the flow"

Browser testing may struggle with canvas, complex uploads, drag-and-drop, clipboard interactions, subtle visual comparisons, and icon-only controls. Signed-in tests currently require Lovable Cloud.

Break the flow into smaller checks, use direct edge calls for backend behavior, add frontend tests for UI rules, and manually verify unsupported interactions.

## "The project is slow"

Collect evidence before optimizing:

- Browser network timing and bundle size
- Console errors and repeated requests
- Cloud and edge-function logs
- Database query shape and indexes
- Data volume and realtime subscriptions
- Image and video size
- Cloud usage spikes

Use a realistic device, network, and data set. Change one suspected bottleneck and measure again.

## "Credits disappear faster than expected"

Open Settings -> Plans & credit usage and filter Build, Cloud, and AI usage by project and person. Also inspect exact message cost and Cloud Usage.

Common causes include broad Build prompts, repeated failed iterations, browser tests, web research, image generation, polling, large queries, realtime usage, jobs, retry loops, and runtime AI calls.

## "GitHub changes are not appearing"

Confirm:

- The workspace connection and project repository link are healthy
- Lovable and GitHub are using the same active branch
- The commit was pushed, not only created locally
- Organization app permissions still permit the repository
- There is no unresolved merge conflict

Lovable syncs one branch at a time. Work on another branch does not appear until you switch to it or merge it into the active branch.

## Escalation package

When requesting support, provide:

- Project URL or ID, without secrets
- Preview or production URL
- Approximate timestamp and timezone
- User role and route
- Expected and actual behavior
- Reproduction steps
- Screenshots or short recording
- Safe console, network, and backend log excerpts
- Last working version and recent change
- Tests and scans already run

## Official references

- [Debugging prompts](https://docs.lovable.dev/prompting/prompting-debugging)
- [Testing](https://docs.lovable.dev/features/testing)
- [Security](https://docs.lovable.dev/features/security)
- [Publish troubleshooting](https://docs.lovable.dev/features/publish)
- [GitHub sync troubleshooting](https://docs.lovable.dev/integrations/github)
