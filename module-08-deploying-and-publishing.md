# Module 8: Publishing and Operating Your App

Publishing deploys a snapshot of the current project to a live URL. Later edits remain in preview until you explicitly publish an update.

> Prepare a project for launch: [Open Lovable and follow the release checklist](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Prepare a project for release
- Distinguish project access from website access
- Publish, update, unpublish, and connect a custom domain
- Configure metadata, security checks, SEO, analytics, and monitoring
- Verify production after every release

## 1. Preview is not production

The preview shows the current working version. Publishing creates a separate live deployment. After the first release:

- New edits are not automatically live.
- Use Publish -> Update to deploy the latest snapshot.
- If production looks old, first confirm that you updated it.

Publishing does not expose project code, chat, or editor access. Those are governed by project access settings.

## 2. Pre-publish checklist

### Product

- [ ] The primary user flow works from start to finish
- [ ] Empty, loading, error, success, and permission states are complete
- [ ] Copy, links, contact details, policies, and pricing are correct
- [ ] Destructive actions require confirmation and provide recovery where practical

### Quality

- [ ] Browser testing covers the main flow on mobile and desktop
- [ ] Frontend and edge tests pass
- [ ] Build and type checks pass
- [ ] No unexpected console or network errors remain

### Security

- [ ] Basic security scan is current
- [ ] Deep scan was run after major code, auth, database, or dependency work
- [ ] Critical and high findings are resolved or explicitly accepted
- [ ] RLS policies are tested with multiple users
- [ ] No secrets are present in frontend code or logs

### Discoverability

- [ ] Site title, description, icon, and social image are correct
- [ ] Pages use useful headings, semantic HTML, and image alt text
- [ ] Canonical URLs, sitemap, `robots.txt`, and structured data are appropriate
- [ ] SEO and AI search review has been run

## 3. Publish

1. Click Publish in the project header.
2. Review the generated `[name].lovable.app` URL.
3. Configure site title, description, icon, and social image.
4. Review published website access.
5. Let the basic security scan complete and resolve blocking findings.
6. Publish.
7. Open the live URL in a new session and verify the critical flow.

Lovable can also publish from chat when you ask it to deploy, ship, or go live, subject to workspace permissions.

## 4. Access settings

Project access controls who can open the editor and collaborate. Published website access controls who can visit the deployed app.

- On Free and Pro, published websites are externally accessible to anyone with the link.
- Business and Enterprise can publish to the workspace or to anyone, with additional people and group controls.
- Enterprise admins can restrict who may publish externally.

Do not use project privacy as a substitute for website access control.

## 5. Custom domains

Custom domains are available on paid plans. You can buy a domain through Lovable or connect an existing domain. A project must be published before the domain can serve the app.

Domain setup lives in Project Settings -> Domains, the Publish dialog, or Workspace settings. Domains purchased through Lovable belong to the workspace. Lovable handles SSL for connected domains.

After connecting a domain:

- Choose the primary domain
- Verify both root and `www` behavior as applicable
- Update OAuth redirect URLs and external webhooks
- Re-run SEO and security reviews
- Verify social previews and canonical URLs

## 6. SEO and AI search

Open More -> SEO & AI search. The review checks metadata, semantic HTML, sitemap, `robots.txt`, canonical tags, alt text, accessibility, mobile usability, performance, indexing, and AI-search readiness.

Reviews are free on all plans. Applying suggested fixes uses normal message credits. Publicly published apps unlock additional live checks. Private and unpublished apps are not indexable.

New TanStack Start apps use server-side rendering. Older React and Vite apps receive Lovable-hosted prerendering for verified search, social, and AI crawlers. Both still require good content and metadata.

## 7. Analytics and monitoring

More -> Analytics shows real-time visitors, pageviews, duration, bounce rate, sources, devices, and pages for published projects.

Project monitoring is a Pro, Business, and Enterprise beta feature. It can run daily or weekly, inspect code and recent visitor errors, email important findings, and offer fixes in chat. It consumes credits when checks run, so choose the schedule and "edited since last check" condition intentionally.

## 8. Release and rollback routine

1. Bookmark or tag the known working version.
2. Publish the update.
3. Test the production URL, not only preview.
4. Watch analytics, logs, payment events, and monitoring findings.
5. If a serious regression appears, restore the last working version and republish.

## Official references

- [Publish your project](https://docs.lovable.dev/features/publish)
- [Set up a custom domain](https://docs.lovable.dev/features/custom-domain)
- [SEO and AI search](https://docs.lovable.dev/features/seo-aeo)
- [Project analytics](https://docs.lovable.dev/features/analytics)
- [Project monitoring](https://docs.lovable.dev/features/project-monitoring)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 9 - Build a Complete App](module-09-real-world-project.md)
