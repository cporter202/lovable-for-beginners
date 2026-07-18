# Module 6: Full-Stack Apps with Lovable Cloud

Lovable Cloud is the default managed path from a frontend prototype to a working full-stack app. It provides hosting, database, authentication, storage, edge functions, jobs, AI, secrets, logs, and usage controls on a Supabase-compatible open-source foundation.

## Learning goals

- Decide between Lovable Cloud and an external Supabase project
- Enable Cloud with the correct region and permissions
- Design a database, authentication flow, storage rules, and server functions
- Distinguish app connectors, chat connectors, and custom APIs
- Protect data with authorization, RLS, and server-side secrets

## 1. Choose the backend path

### Lovable Cloud

Start here for most new projects. Lovable manages the infrastructure and integrates backend tools with the editor, preview, logs, testing, and publishing.

### External Supabase

Use the native Supabase integration when you already operate Supabase or need direct control outside Lovable Cloud. You take on more configuration, monitoring, auth-provider setup, and migration responsibility.

Do not connect both casually. Decide which service owns the production data and document that decision in Project knowledge.

## 2. Enable Cloud carefully

Lovable Cloud can be enabled automatically or when a feature needs backend capability. Before enabling it, choose the region closest to your users or required by data residency. Current regions are Americas, Europe, and Asia Pacific.

The selected region cannot be changed for an existing Cloud project, and Cloud projects cannot be moved between regions. Treat this as an architectural decision.

Cloud tool permissions are managed under Connectors -> App connectors -> Lovable Cloud -> Manage permissions. Individual tools can be set to:

- Always allow
- Ask each time
- Never allow

Permissions cover actions such as enabling Cloud, reading or modifying the database, adding data, configuring auth, reading logs, and running security checks. Teams handling sensitive data may prefer approval for schema and auth changes.

## 3. Database design

Describe entities, relationships, ownership, constraints, and indexes before asking for tables.

```text
Plan the database for a book-club app.

Entities:
- clubs: name, slug, owner, created_at
- club_members: club, user, role, joined_at
- books: club, title, author, cover_url, status, month, created_by
- notes: book, author, body, created_at, updated_at

Rules:
- A user can belong to multiple clubs
- Only owners can delete a club
- Members can read their clubs and add books or notes
- Users can edit only their own notes
- Prevent duplicate membership rows

Propose the schema, indexes, foreign-key delete behavior, and RLS policies.
Do not modify the database until I approve the plan.
```

Use the Cloud database view to inspect tables and records. Keep schema changes in migrations and review generated types after changes.

## 4. Authentication and authorization

Lovable Cloud supports built-in user management and can generate email, phone, and Google sign-in flows. Google authentication can be Lovable-managed or configured with your own Google Cloud credentials.

Authentication answers "who is this user?" Authorization answers "what may this user do?" A protected page is not enough. Enforce authorization in the database and server-side functions.

For every user-owned table:

- Enable row-level security
- Define explicit read, insert, update, and delete policies
- Test with at least two different users
- Test unauthenticated access
- Avoid policies that trust a user ID sent by the browser

## 5. Storage

Use Cloud storage for profile photos, documents, videos, and other files. Buckets are private by default and can be public when appropriate. Current file support is up to 2 GB per file.

Define:

- Allowed file types and maximum size
- Whether objects are public or private
- Who can upload, read, replace, and delete
- How filenames and paths avoid collisions
- What happens when a related database record is deleted

Do not rely only on client-side validation.

## 6. Edge functions, jobs, AI, and secrets

Use edge functions for trusted server-side work:

- Calling authenticated third-party APIs
- Sending email or notifications
- Payment webhooks
- Scheduled or background work
- Expensive computation
- Operations requiring secret keys

Store private credentials in Cloud secrets. Never put secret values in `VITE_` variables because those are embedded in frontend code. Frontend-safe publishable values and private server secrets are different categories.

Lovable AI can add runtime AI features without a separate provider key. Treat prompts and model output as untrusted input, define cost limits, and avoid sending unnecessary personal data.

## 7. Integrations: three categories

| Category | Purpose | Example |
| --- | --- | --- |
| App connector | Gives the deployed app access to an external service | Stripe, Shopify, Airtable, Google Maps |
| Chat connector | Gives Lovable personal or team context while building, using MCP | Notion, Linear, Jira, Miro |
| Any API | Adds custom functionality not covered by a connector | A niche data service |

App connectors and chat connectors are not interchangeable. A chat connector helps the agent build with context; an app connector provides capabilities to app users at runtime.

For APIs without authentication, the frontend may call a public endpoint if CORS and abuse risks are acceptable. For authenticated APIs, use a secret plus a server-side function or managed connector.

## 8. Built-in payments

Lovable's current built-in payment flow supports Stripe and Paddle for subscriptions and one-time purchases. It requires a Pro plan or higher and Lovable Cloud. Authentication is recommended so purchases map to users.

Preview uses a test payment environment. The published app uses the live environment after provider verification and go-live checks. Test success, failure, cancellation, duplicate events, expired sessions, webhooks, access changes, and refunds before launch.

## Security gate

Before continuing:

- [ ] Cloud region and permission defaults are intentional
- [ ] Every sensitive table has reviewed RLS policies
- [ ] Secrets exist only in managed server-side storage
- [ ] Privileged actions re-check authorization server-side
- [ ] File permissions and limits are enforced
- [ ] Logs contain enough context without exposing credentials or personal data
- [ ] Backend behavior has direct calls or edge tests

## Official references

- [Lovable Cloud](https://docs.lovable.dev/integrations/cloud)
- [Lovable integrations](https://docs.lovable.dev/integrations/introduction)
- [Chat connectors and MCP](https://docs.lovable.dev/integrations/mcp-servers)
- [Security overview](https://docs.lovable.dev/features/security)
- [Add payments](https://docs.lovable.dev/features/payments)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 7 - Inspecting and Editing Code](module-07-code-mode.md)
