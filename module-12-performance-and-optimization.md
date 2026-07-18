# Module 12: Performance, SEO, and Operations

Optimization begins with measurement. A fast preview does not prove a fast production experience, and a high pageview count does not prove users completed the key workflow.

> Audit and optimize a live project: [Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Establish performance budgets and reproduce slow behavior
- Optimize frontend, data, and Cloud usage with evidence
- Use SEO and AI search review, analytics, logs, and monitoring
- Avoid premature or cosmetic optimization

## 1. Define a measurable target

Choose critical flows and conditions:

- First public page on a mid-range phone and ordinary mobile network
- Authenticated dashboard with realistic data volume
- Search, filtering, or table interaction with the expected record count
- File upload and processing at the accepted maximum size
- Checkout or other revenue-critical flow

Example:

```text
Investigate dashboard performance in Plan mode.
Target: the main content should become usable quickly on a mid-range mobile device
with 500 books and 50 members in the club. Identify the slowest user-visible step,
measure network and rendering behavior, and propose fixes ordered by impact.
Do not change code yet.
```

## 2. Frontend performance

Common high-impact areas:

- Oversized images or video
- Large initial JavaScript bundles
- Unnecessary rerenders
- Fetching data the screen does not use
- Waterfall requests that could run together
- Missing pagination or virtualization for long lists
- Layout shift from media without stable dimensions
- Heavy work on every keystroke

Prefer changes tied to observed evidence. Lazy-load below-the-fold assets, compress images, cache stable data, debounce expensive search, and split large routes only when measurements justify it.

Preserve accessibility and correctness. Removing labels, error handling, or loading states is not a valid speed improvement.

## 3. Data and backend performance

Check:

- Missing indexes for filters, joins, and sort order
- N+1 requests
- Fetching unbounded rows
- Repeated functions or external API calls
- Slow edge functions and timeouts
- Realtime subscriptions broader than needed
- Large files or database payloads

Lovable Cloud includes database health and usage views. Use logs to connect a slow screen to specific requests. Add indexes only for real query patterns because every index also adds write and storage cost.

## 4. Cloud and AI usage

Cloud usage can include database server, storage, compute, network, realtime, and file storage. Runtime AI features consume AI gateway usage. Review the Cloud Usage view and Settings -> Plans & credit usage.

Control cost by:

- Avoiding polling when events or user actions suffice
- Limiting query fields and rows
- Caching stable responses appropriately
- Moving expensive repeated work to a deliberate job
- Setting practical AI input, output, and request limits
- Monitoring loops, retries, and failed webhooks

Do not expose cost controls only in the UI. Enforce limits server-side where abuse is possible.

## 5. SEO and AI search review

More -> SEO & AI search can audit:

- Metadata and canonical URLs
- Semantic HTML and heading structure
- Sitemap and `robots.txt`
- Image alt text
- Structured data
- Accessibility and mobile usability
- Performance and indexing
- AI-search readiness and `llms.txt`

New TanStack Start projects use SSR. Older React and Vite apps use Lovable-hosted prerendering for verified crawlers. Neither replaces clear content, meaningful internal links, accurate metadata, good performance, and external authority.

Only public sites can be indexed. Re-run the review after publishing and after connecting a custom domain. Use Google Search Console and Semrush connectors when their data is relevant and available.

## 6. Analytics

More -> Analytics reports visitors, pageviews, bounce rate, visit duration, traffic sources, devices, and pages in real time.

Turn metrics into questions:

- Are users reaching the primary flow?
- Where do they leave?
- Does mobile behavior differ from desktop?
- Did a release improve completion without increasing errors?

Built-in page analytics may not answer product-specific questions. Add privacy-conscious event tracking only for decisions you plan to make, and avoid collecting unnecessary personal data.

## 7. Monitoring and release observation

Project monitoring can inspect code and recent visitor errors on a daily or weekly schedule for supported paid plans. Use "if edited since last check" to avoid spending credits on unchanged projects.

After release, watch:

- Visitor errors and failed routes
- Auth and payment failures
- Function logs and external API health
- Cloud usage spikes
- Analytics changes in the primary flow
- Monitoring and security findings

Lovable cannot monitor production infrastructure hosted outside its control. External hosting requires external observability and incident response.

## Optimization workflow

1. Define the slow user outcome and realistic data.
2. Reproduce in preview or production.
3. Capture browser, network, log, and query evidence.
4. Rank causes by user impact and confidence.
5. Make one targeted change.
6. Run regression tests and repeat the measurement.
7. Keep the change only if it improves the target without harming correctness.

## Official references

- [SEO and AI search](https://docs.lovable.dev/features/seo-aeo)
- [Project analytics](https://docs.lovable.dev/features/analytics)
- [Project monitoring](https://docs.lovable.dev/features/project-monitoring)
- [Lovable Cloud](https://docs.lovable.dev/integrations/cloud)
- [Debugging prompts](https://docs.lovable.dev/prompting/prompting-debugging)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 13 - Advanced Integrations and APIs](module-13-advanced-api-integration.md)
