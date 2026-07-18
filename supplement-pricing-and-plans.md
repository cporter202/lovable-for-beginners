# Pricing, Credits, and Plans

Verified against Lovable's official pricing documentation on July 18, 2026. Pricing, grants, and feature limits can change. Use the [live plan documentation](https://docs.lovable.dev/introduction/subscription-plans) and [Lovable pricing page](https://lovable.dev/pricing) before purchasing.

## Current plan overview

| Plan | Best for | Starting monthly credits and price | Selected capabilities |
| --- | --- | --- | --- |
| Free | Trying Lovable and smaller projects | No paid monthly credits | Git sync, public publishing, daily build grant; no code editor or custom domain |
| Pro | Individuals and fast-moving teams | 100 credits from $25/month | Code editor, custom domains, badge removal, monitoring, top-ups, rollover |
| Business | Departments needing controls | 100 credits from $50/month | Pro features plus internal publishing, roles, security center, SSO, templates |
| Enterprise | Large organizations | Contract-based | Advanced governance, publishing controls, SCIM, audit logs, scheduled security scans |

Annual billing and higher credit tiers are available for Pro and Business. Enterprise terms vary by contract.

## One credit balance

Lovable is gradually rolling out one credit balance across three usage types:

| Usage | What it covers |
| --- | --- |
| Build | Plan and Build mode messages, edits, generation, investigation, and verification |
| Cloud | Database server, storage, compute, network, realtime, and related hosted resources |
| AI gateway | Runtime AI features used by deployed apps |

Some workspaces may temporarily still display the older Cloud and AI balance experience during rollout.

## Included usage-specific grants

Current Free, Pro, and Business grants:

| Grant | Free | Pro | Business |
| --- | --- | --- | --- |
| Daily build credits | 5/day, capped at 30/month | 5/day | 5/day |
| Monthly Cloud grant | 20 credits | 20 credits | 20 credits |
| Monthly AI grant | 4 credits | 4 credits | 4 credits |

Daily credits reset at 00:00 UTC and do not roll over. On Free, the monthly 30-credit cap means the daily grant stops after six grant days and resumes the next calendar month.

Cloud and AI grants are described by Lovable as temporary and subject to change. Usage-specific grants are spent before general credits.

## Build costs

- Plan mode currently costs 1 credit per message.
- Build mode is usage-based. Small focused edits often cost less than broad generation, multi-file work, browser testing, web research, or image generation.
- Stopped Build requests are charged for work already completed.
- The exact message cost is available from the three-dot menu below the response.
- Preview-toolbar element selections use normal message credits.
- Inline text editing is currently free for the first 100 edits per user each day, then uses credits.

Do not treat example Build costs in the docs as quotes. Actual cost varies by the project and request.

## General credits and rollover

Paid monthly plan credits are general credits. They can cover Build, Cloud, and AI usage after relevant grants are exhausted.

- Monthly plan credits roll over while the paid subscription remains active.
- Monthly-plan credits expire two months after issue.
- Credits on annual plans expire one month after the annual billing period ends.
- Purchased top-up credits expire 12 months after purchase.
- Top-ups and auto top-up are available on Pro and Business.

If a workspace downgrades to Free, unexpired paid subscription and rollover credits are frozen until the workspace upgrades again or the credits reach their original expiry. Purchased top-up and bonus credits can remain usable until expiry.

## Selected plan differences

| Feature | Free | Pro | Business | Enterprise |
| --- | --- | --- | --- | --- |
| GitHub and GitLab sync | Yes | Yes | Yes | Yes |
| Code editor and code download | No | Yes | Yes | Yes |
| Custom domains | No | Yes | Yes | Yes |
| Remove Lovable badge | No | Yes | Yes | Yes |
| Project monitoring | No | Yes | Yes | Yes |
| Internal publishing | No | No | Yes | Yes |
| Design templates | No | No | Yes | Yes |
| Security center | No | No | Yes | Yes |
| SSO | No | No | Yes | Yes |
| Publishing controls | No | No | No | Yes |
| SCIM and audit logs | No | No | No | Yes |

Free and Pro published sites are externally accessible to anyone with the link. Business and Enterprise can publish internally to the workspace or externally.

## Managing usage

Open Settings -> Plans & credit usage to:

- View balance and expiry
- Filter usage by time, project, person, and usage type
- Review Build, Cloud, and AI consumption
- Configure alerts
- Purchase one-time or automatic top-ups
- Upgrade, downgrade, cancel, change billing cycle, or view invoices

For Cloud projects, also inspect the Cloud Usage view. It breaks down database server, database storage, compute, file storage, live updates, and network consumption.

## Cost-control habits

1. Use Plan mode when a broad Build request would likely be thrown away.
2. Keep Build prompts focused and include acceptance criteria.
3. Implement and browser-test large work in separate messages.
4. Stop repeated error loops and investigate the root cause.
5. Monitor Cloud queries, realtime subscriptions, storage, retries, and AI limits.
6. Use project-monitoring conditions that avoid unchanged projects.
7. Set credit alerts before a production launch.

## Official references

- [Subscription plans](https://docs.lovable.dev/introduction/subscription-plans)
- [Credits and usage](https://docs.lovable.dev/introduction/credits-and-usage)
- [Lovable Cloud usage](https://docs.lovable.dev/integrations/cloud)
- [Preview toolbar credit behavior](https://docs.lovable.dev/features/preview-toolbar)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)
