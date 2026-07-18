# Module 9: Real-World Project - Book Club Hub

In this project you will build a complete multi-user web app with planning, design, Lovable Cloud, authentication, row-level security, testing, publishing, SEO, analytics, and monitoring.

> Build the complete project alongside this module: [Start in Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Product brief

Book Club Hub helps small groups choose a monthly book, track reading status, and discuss notes. A user can create or join clubs, but can access only clubs where they are a member.

### Core roles

- Owner: manages a club and its members
- Member: views club content, updates personal reading status, and writes notes
- Visitor: can reach the sign-in flow but cannot access club data

### Core flow

1. Sign up or sign in.
2. Create a club or accept an invitation.
3. Add the current month's book.
4. Update personal reading status.
5. Add and edit personal notes.
6. View the club's progress summary.

## Milestone 1: Product and architecture plan

Use Plan mode:

```text
Plan a production-ready Book Club Hub for small private groups.

Users can create multiple clubs, invite members, add monthly books,
track their own reading status, and write personal notes.

Before proposing implementation:
- Ask focused product and security questions
- Inspect the current project and stack
- Recommend the routes, components, database schema, indexes, and RLS policies
- Define loading, empty, error, offline, and permission states
- Include frontend tests, edge tests, browser tests, security scans, and release steps
- Separate the work into reviewable milestones

Do not modify code.
```

Review the plan. Confirm ownership rules, invite expiration, delete behavior, and whether notes are private to their author or visible to the club. Edit the plan before approval.

## Milestone 2: Design foundation

Add Project knowledge:

```text
Product: Private reading coordination for neighborhood book clubs.
Audience: Adults with mixed technical comfort, primarily on phones.
Primary action: See this month's book and update reading progress.

Design: Warm editorial style, compact and calm. White and soft gray surfaces,
near-black text, forest-green actions, muted coral highlights. Source Serif for
display headings and Inter for controls. Use thin dividers, modest radii, and
clear focus states. Avoid gradients, glass effects, decorative dashboards,
and oversized cards.

Quality: WCAG AA contrast, keyboard navigation, reduced-motion support,
responsive layouts from 320px upward, and explicit empty/loading/error states.
```

Ask Build mode to create the shell with local sample data only. Build routes for sign-in, club list, club detail, book detail, members, and settings. Use realistic content and verify phone, tablet, and desktop layouts.

Checkpoint: bookmark the approved design foundation.

## Milestone 3: Lovable Cloud and schema

Choose the Cloud region deliberately, then approve the schema portion of the plan.

Suggested model:

| Table | Purpose |
| --- | --- |
| `profiles` | Public app profile linked to an authenticated user |
| `clubs` | Club identity and owner |
| `club_members` | User membership and role |
| `club_invites` | Email invitation, role, token hash, and expiry |
| `books` | Club reading selections and month |
| `reading_progress` | One user's status for one book |
| `notes` | User-authored notes on a book |

Require unique membership and progress constraints, useful foreign keys, indexes for common filters, and explicit delete behavior.

RLS acceptance criteria:

- Non-members cannot read club rows or related data.
- Members can read their club and books.
- Only owners can change club settings or membership roles.
- Users can change only their own progress.
- Users can change only their own notes.
- Invitation acceptance validates token, email, expiry, and existing membership server-side.

Checkpoint: inspect migrations and policies before adding UI calls.

## Milestone 4: Authentication

Add email authentication and managed Google sign-in if appropriate. Include sign-up, sign-in, sign-out, password reset, session loading, and useful errors.

Test with:

- A club owner
- A club member
- A signed-in non-member
- A signed-out visitor

Do not use route hiding as authorization. Attempt direct data access for each role and confirm the database rejects unauthorized operations.

## Milestone 5: Core workflows

Implement one vertical flow at a time.

### Club creation

Create the club and owner membership atomically. Handle duplicate slugs, network failure, and double submission.

### Invitations

Generate an expiring invitation server-side. Send email through a supported connector or function. Never expose a service secret in the browser.

### Books and progress

Owners add monthly books. Members update their own status: Want to Read, Reading, or Finished. Include optimistic feedback only if failures roll back correctly.

### Notes

Members create, edit, and delete their own notes. Confirm the decided visibility rule in both UI and RLS.

Checkpoint after each flow: run focused tests and bookmark a working state.

## Milestone 6: Dashboard and quality states

Add a useful club summary from real data:

- Current book and due date
- Member progress counts
- Recent permitted activity
- Empty state for a new club
- Loading skeleton without layout shift
- Recoverable error state with retry

Avoid exposing private notes or user email addresses in aggregate data.

## Milestone 7: Verification

Ask Build mode in separate prompts:

```text
Run the existing frontend tests and add focused tests for:
- Sign-in validation
- Club form errors
- Reading-status filtering
- Permission-based controls
Report failures and fix only issues related to this project.
```

```text
Call the invitation edge function directly with valid, expired, duplicate,
unauthorized, and malformed requests. Add edge tests for the authorization
and expiry rules. Report request and response behavior without exposing secrets.
```

```text
Use browser testing on mobile and desktop to verify:
- Sign up and sign in
- Create a club
- Add a monthly book
- Update reading status
- Invite a member
- Confirm a non-member cannot access a club URL
Capture any console or network errors and report the tested account roles.
```

Run Basic and Deep security scans after tests pass. Review RLS, dependencies, input validation, exposed endpoints, and secrets.

## Milestone 8: Publish and operate

1. Configure title, description, icon, and social image.
2. Run the SEO and AI search review.
3. Publish to a temporary Lovable URL.
4. Test the production URL with a clean browser session.
5. Connect a custom domain if needed and update OAuth redirects.
6. Republish and rerun SEO and security reviews.
7. Review analytics after real traffic arrives.
8. Enable project monitoring on an intentional schedule if your plan supports it.

## Completion checklist

- [ ] The approved plan matches the implementation
- [ ] Project knowledge describes current product and architecture decisions
- [ ] All core workflows work at phone and desktop sizes
- [ ] RLS has been tested across roles
- [ ] Secrets remain server-side
- [ ] Frontend, edge, and browser tests pass
- [ ] Basic and Deep security scans are current
- [ ] Production was tested after publishing
- [ ] The live version and current editor state are clearly identified

## Official references

- [Lovable Cloud](https://docs.lovable.dev/integrations/cloud)
- [Google authentication](https://docs.lovable.dev/features/google-auth)
- [Test and verify your app](https://docs.lovable.dev/features/testing)
- [Project security view](https://docs.lovable.dev/features/security-view)
- [Publish your project](https://docs.lovable.dev/features/publish)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 10 - Debugging, Testing, and Security](module-10-debugging-and-testing.md)
