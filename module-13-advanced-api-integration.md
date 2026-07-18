# Module 13: Advanced Integrations and APIs

An integration is secure only when credentials, authorization, rate limits, failure behavior, and data ownership are designed together. Lovable offers app connectors, app-user connectors, chat connectors, and custom APIs for different jobs.

> Build an integration while following the guide: [Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Select the correct integration type
- Design secure server-side API calls
- Handle OAuth, rate limits, retries, webhooks, and partial failure
- Test connectors and APIs without exposing credentials
- Understand gateway security and runtime access

## 1. Choose the integration model

### App connector

Use when the deployed app needs to call a supported external service through a managed connection. Many connectors use Lovable's gateway, which stores encrypted credentials and handles authentication or token refresh.

### App-user connector

Use when each end user should connect their own third-party account and act with their own permissions. This avoids making every user share one workspace-level service identity.

### Chat connector using MCP

Use when Lovable needs personal tool context while building, such as Notion documents or Linear issues. This is primarily builder context, not a runtime app backend.

### Custom API

Use when no connector fits. Public unauthenticated endpoints may be called from the frontend if CORS, privacy, and abuse controls permit. Authenticated or privileged APIs should be called from an edge function with managed secrets.

## 2. Plan the contract

Before implementation, record:

- Endpoint and method
- Authentication method and credential owner
- Request and response schema
- Error status codes
- Pagination and filtering
- Rate limits and quotas
- Timeout and retry behavior
- Idempotency requirements
- Webhook signature verification
- Personal or regulated data involved
- Data retention and deletion behavior

```text
Plan an integration with Service X for creating invoices.
Do not write code yet.

Determine:
- Whether a Lovable app connector exists and whether it uses the gateway
- Whether the workspace account or each app user should authenticate
- Required scopes and least-privilege permissions
- Server-side request flow and secret handling
- Idempotency, retries, rate limits, webhooks, and failure states
- Tests, logs, and disconnect behavior
```

## 3. Gateway security

For gateway-based app connectors:

- Credentials are encrypted and not readable after saving.
- The connected service account limits what the app can access.
- Disconnecting removes secrets and stops access.
- OAuth refresh can be managed by the gateway.
- Current per-project limit is up to 1,000 requests per minute per connector.
- Stable outbound IP ranges can support allowlisting.

Confirm gateway behavior for the specific connector. Some connectors use direct browser keys or other models and need domain restrictions for Lovable preview, published, and custom domains.

## 4. Secure custom API pattern

```text
Browser -> authenticated edge function -> third-party API
```

The edge function should:

1. Authenticate the caller.
2. Authorize the requested action.
3. Validate and normalize input.
4. Read the secret from managed storage.
5. Apply timeout, rate limit, and idempotency rules.
6. Call the provider.
7. Return only necessary fields.
8. Log an operation ID and safe metadata, never credentials.

Do not treat a hidden button or frontend route as authorization.

## 5. OAuth and scopes

Decide whether the integration is:

- One shared workspace connection
- One connection per app user
- A Lovable-managed OAuth flow
- Your own OAuth client and credentials

Request the smallest scopes needed. Define token refresh, revocation, reconnect, account switching, and disconnect behavior. Add every preview and production redirect URL required by the provider, especially after a custom-domain or external-hosting change.

## 6. Resilience

### Timeouts

Fail in a bounded time and show a recoverable message.

### Retries

Retry only transient failures and use exponential backoff with jitter. Do not blindly retry validation, authentication, or permission errors.

### Idempotency

Use provider idempotency keys or your own operation records for payments, orders, invitations, and any action that must not duplicate.

### Rate limits

Respect provider headers and quotas. Cache safe responses, batch calls, paginate, and move heavy processing to jobs when appropriate.

### Webhooks

Verify signatures on the raw request, reject stale or replayed events where supported, store provider event IDs, and make handlers idempotent.

## 7. Testing matrix

- Valid request
- Invalid input
- Signed-out and unauthorized caller
- Missing, expired, or revoked connection
- Provider 400, 401, 403, 404, 409, 429, and 500 responses
- Timeout and network failure
- Duplicate request or webhook
- Pagination boundary
- Disconnect and reconnect
- Provider success followed by local database failure

Use direct edge-function calls for isolation, edge tests for durable rules, and browser testing for the complete user flow.

## Official references

- [Lovable integrations](https://docs.lovable.dev/integrations/introduction)
- [Integration security](https://docs.lovable.dev/integrations/security)
- [App-user connectors](https://docs.lovable.dev/integrations/app-user-connectors)
- [Chat connectors and MCP](https://docs.lovable.dev/integrations/mcp-servers)
- [Test and verify your app](https://docs.lovable.dev/features/testing)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 14 - Git Sync and Collaboration](module-14-version-control-github.md)
