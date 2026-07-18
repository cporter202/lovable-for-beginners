# Module 15: External Hosting and Portability

Lovable Cloud is the recommended default for most projects. External hosting is appropriate when a real compliance, data-residency, network, infrastructure, or organizational requirement justifies the operational work.

## Learning goals

- Separate code, frontend hosting, and backend ownership
- Decide whether to stay on Lovable Cloud, use a hybrid setup, or self-host
- Deploy from Git with stack-aware build settings
- Migrate data and backend services without assuming full portability is automatic
- Plan monitoring, rollback, OAuth, secrets, and security outside Lovable

## 1. Three independent layers

| Layer | Default | Portable option |
| --- | --- | --- |
| Code | Managed in Lovable | GitHub or GitLab and any Git workflow |
| Frontend | Lovable hosting | Managed host, CDN, container, VM, or Kubernetes |
| Backend and data | Lovable Cloud | Managed or self-hosted Supabase-compatible services |

You can move the frontend while keeping the backend on Lovable Cloud. Moving the backend is a separate project involving database, auth, storage, functions, secrets, and operations.

## 2. Recommended adoption path

1. Start on Lovable Cloud.
2. Sync to GitHub.
3. Move only the layer that has a real constraint.

External hosting makes your team responsible for some combination of CI/CD, previews, rollbacks, environment variables, TLS, CDN behavior, uptime, logs, scaling, database backups, auth providers, OAuth token refresh, secrets, security scanning, and incident response.

Lovable cannot monitor or debug production infrastructure it does not control.

## 3. Identify the project stack

Do this before selecting a hosting recipe:

```text
Inspect package.json, routing, build scripts, server entry points, and deployment
configuration. Tell me whether this project is TanStack Start with SSR or an older
React/Vite SPA, what runtime it requires, what the build output is, and which
environment variables are public versus server-only. Do not change code.
```

Current official docs state that new projects created from May 13, 2026 use TanStack Start with SSR by default, except on Enterprise plans. Older projects use React and Vite.

The official external-hosting guide still contains Vite SPA examples such as `npm run build`, `dist`, Node 22, and an `index.html` fallback. Apply those instructions only to a project that actually matches that stack. TanStack Start SSR requires a compatible server runtime or adapter and should not be deployed as a static SPA unless the project is explicitly configured for static output.

## 4. External frontend with Lovable Cloud backend

This is the most common hybrid setup.

1. Connect the project to GitHub.
2. Import the repository into the hosting platform.
3. Configure the actual install and build commands.
4. Configure frontend-safe environment values required by the Cloud client.
5. Configure routing or SSR runtime for the detected stack.
6. Add the production domain to OAuth redirect and allowed-origin settings.
7. Deploy and test from a clean session.

For older Vite projects, public Cloud configuration commonly uses:

```text
VITE_SUPABASE_URL
VITE_SUPABASE_PUBLISHABLE_KEY
VITE_SUPABASE_PROJECT_ID
```

These values are embedded at build time. Never include private service-role or third-party secret keys.

Common managed hosts include Netlify, Cloudflare Pages, Vercel, AWS Amplify, Azure Static Web Apps, and Firebase Hosting. Compatibility depends on the project's stack and required runtime.

## 5. Self-managed frontend

Containers, VMs, and Kubernetes provide control but require your own:

- Build and deployment automation
- TLS and domain management
- CDN or reverse-proxy configuration
- Logs, metrics, alerting, and uptime checks
- Runtime and dependency patching
- Branch preview strategy
- Rollback procedure

For a Vite SPA, the server usually needs an `index.html` fallback for client-side routes. For TanStack Start SSR, deploy the generated server using the project's supported adapter and runtime. Do not apply SPA rewrites to an SSR server without understanding the route behavior.

## 6. Moving the backend

Lovable Cloud uses a Supabase-compatible foundation. Managed Supabase is the most direct external target because it provides comparable database, auth, storage, realtime, functions, and RLS concepts.

Migration categories:

| Asset | Typical migration |
| --- | --- |
| Schema and RLS | Apply reviewed SQL migrations in order |
| Table data | Export and import, then verify counts and relationships |
| Storage policies | Migrate schema policies |
| Stored files | Download and upload separately |
| Auth providers | Reconfigure manually |
| User passwords | Cannot be exported; plan password reset |
| Secrets and environment values | Recreate manually |
| Functions and webhooks | Deploy and reconfigure endpoints manually |

The current Cloud export documentation limits database exports to 5 GB and one request per 24 hours. Confirm limits in the live docs before planning a migration.

Plan migrations before onboarding real users. Use a maintenance window or dual-write strategy only if you can reason about consistency, replay, and rollback.

## 7. External release checklist

- [ ] GitHub is current and the production commit is identified
- [ ] Project stack and runtime were detected, not assumed
- [ ] CI installs reproducibly and runs tests plus build
- [ ] Public variables and private secrets are separated
- [ ] OAuth redirects, CORS, webhooks, and domain restrictions are updated
- [ ] SPA fallback or SSR adapter matches the stack
- [ ] TLS, custom domain, and canonical URLs are correct
- [ ] External logs, monitoring, alerts, backups, and rollback exist
- [ ] Preview and production user flows pass
- [ ] Security and dependency scans run outside Lovable as needed
- [ ] Ownership and incident contacts are documented

## 8. Decision guide

Stay fully on Lovable Cloud when speed and low operations overhead matter most. Use hybrid hosting when you need frontend deployment control but want managed backend services. Move the backend only for a concrete infrastructure requirement and after a tested migration and operations plan.

## Official references

- [Deployment, hosting, and ownership options](https://docs.lovable.dev/tips-tricks/deployment-hosting-ownership)
- [Deploying outside Lovable Cloud](https://docs.lovable.dev/tips-tricks/external-deployment-hosting)
- [Git sync overview](https://docs.lovable.dev/integrations/git-sync-overview)
- [Lovable Cloud](https://docs.lovable.dev/integrations/cloud)
- [Current stack FAQ](https://docs.lovable.dev/introduction/faq)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Return to the [course overview](README.md).
