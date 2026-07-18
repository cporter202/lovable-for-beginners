# Practice Solutions and Hints

These are reference approaches, not scripts to follow blindly. Try each exercise first, compare your result, and adapt the solution to your project's stack and requirements.

## Module 2: Strong first project

### Challenge

Turn the vague request "build a nice habit tracker" into a reliable initial prompt.

### Hint

Define the user, key action, routes, real content, visual direction, states, and excluded backend work.

### Reference solution

```text
Build a responsive habit tracker for a college student managing five daily habits.

Primary flow:
The user sees today's habits, marks each complete, and reviews a seven-day summary.

Screens:
- Today
- Weekly progress
- Habit settings

Design:
Compact and optimistic, with a white background, near-black text, green primary
actions, and a coral highlight. Use accessible contrast and visible focus states.

Behavior:
- Use realistic sample habits
- Include complete, missed, empty, loading, and error states
- Prevent duplicate submissions
- Work from 320px through desktop widths

Scope:
Use local sample data only. Do not add authentication, notifications, or a database.
Ask focused questions if the product or visual direction is ambiguous.
```

Why it works: it creates a useful first milestone without committing to auth or backend architecture.

## Module 3: Plan then build

### Challenge

Add multi-user synchronization without letting Build mode invent the security model.

### Reference approach

1. In Plan mode, ask for user roles, schema, ownership, RLS, conflict behavior, offline behavior, and tests.
2. Resolve whether habits are private, shared, or both.
3. Edit and approve only the auth and schema milestone.
4. Build that milestone.
5. Inspect policies and migrations.
6. Test as two users before building sharing UI.

Key acceptance criterion:

```text
A signed-in user cannot read or modify another user's private habits by changing
a URL, request body, or client-side state.
```

## Module 4: Focused refinement

### Challenge

The weekly cards look uneven and one title overflows on mobile.

### Reference solution

Select all affected cards with the preview toolbar and prompt:

```text
Make these cards use the same internal grid so titles, progress values, and actions
align. Allow titles to wrap to two lines and preserve a stable action row.
Keep the existing colors, copy, card width, and desktop grid.
Verify no overflow at 320px and 200% text zoom.
```

Add the typography and accessibility choices to Project knowledge only if they should apply across the whole app.

## Module 5: Repair a vague prompt

### Vague prompt

```text
Make the dashboard better.
```

### Reference rewrite

```text
Outcome:
Help club owners understand reading progress and take the next action in under 10 seconds.

Context:
Update @src/pages/ClubDashboard.tsx using existing data and components.

Requirements:
- Show the current book, due date, and member progress counts first
- Put pending invitations and overdue setup tasks in one action list
- Add empty, loading, and recoverable error states
- Use real labels and realistic long values

Constraints:
- Do not change navigation, database schema, or permissions
- Keep the current design tokens and compact editorial style
- Do not expose member email addresses or private notes

Acceptance criteria:
- Main action is visible without scrolling at 390x844
- No overflow at 320px
- Keyboard order follows visual order
- Existing dashboard tests pass and changed behavior has focused tests
```

## Module 6: Secure data model

### Challenge

Create a comments table where members can read comments in their clubs and edit only their own.

### Reference model

Fields:

- `id`
- `club_id`
- `book_id`
- `author_id`
- `body`
- `created_at`
- `updated_at`

Policy intent:

- Select: authenticated user is a member of `club_id`.
- Insert: `author_id` equals the authenticated user and the user belongs to the club.
- Update/delete: `author_id` equals the authenticated user and the user still belongs to the club.
- Foreign keys ensure the book belongs to the same club, preferably through server-side validation or schema design.

Tests:

- Member reads club comments.
- Non-member cannot read them.
- Member inserts as self.
- Member cannot insert as another user.
- Author edits own comment.
- Different member cannot edit it.

## Module 8: Release decision

### Challenge

Decide whether an app is ready to publish after browser tests pass but the Deep security scan reports an unprotected edge function.

### Reference answer

No-go. Browser success proves the happy path, not authorization. Protect the edge function, add unauthorized direct-call and edge tests, rerun related tests plus Basic and Deep scans, then publish. If production is already exposed, revert or disable the affected path and republish first.

## Module 9: Invitation workflow

### Challenge

Design an invitation flow that resists duplicates and replay.

### Reference approach

- Store a hash of a random invitation token, never the raw token.
- Store target email, club, role, creator, expiry, accepted time, and revoked time.
- Generate and send the raw token only once through a server-side function.
- On acceptance, authenticate the user and compare normalized email.
- Validate expiry, revocation, prior acceptance, existing membership, and inviter permissions.
- Create membership and mark the invitation accepted atomically.
- Use a unique constraint to prevent duplicate membership.
- Treat repeated acceptance as an idempotent success or explicit already-used response.

## Module 10: Root-cause debugging

### Challenge

A Save button occasionally creates two records.

### Reference investigation

Check these in order:

1. Is the button disabled while the request is active?
2. Can form submit and button click both invoke the handler?
3. Does the client retry after timeout?
4. Does the server function retry provider or database work?
5. Is a webhook repeating the write?
6. Is there a database uniqueness or idempotency constraint?

The durable fix usually combines client feedback with server-side idempotency or a database constraint. A disabled button alone is not enough because requests can repeat outside the UI.

## Module 11: Staged migration

### Challenge

Split `full_name` without breaking old clients.

### Reference stages

1. Add nullable `first_name` and `last_name`; keep `full_name` reads and writes.
2. Backfill names with a documented rule and flag ambiguous rows.
3. Update new writes and reads while maintaining compatibility.
4. Verify row counts, null rates, UI, exports, and integrations.
5. Make new fields required only when data is clean.
6. Remove `full_name` in a later release with a separate rollback point.

Do not guess how to split every name. Real names do not reliably map to two space-separated parts.

## Module 12: Performance review

### Challenge

The dashboard makes 51 requests for 50 members.

### Reference solution

This suggests an N+1 pattern: one member-list request plus one request per member. Ask Plan mode to trace the calls and confirm. Replace with an appropriate join, batched query, or server aggregation that returns only the fields needed. Add authorization to the aggregate query, test realistic data volume, and compare request count and response time before and after.

## Module 13: Reliable API action

### Challenge

Send one invoice even if the user retries after a timeout.

### Reference design

- Create a local operation record with a unique business key.
- Send a stable idempotency key to the provider.
- Mark operation states such as pending, succeeded, failed, or unknown.
- On timeout, query the provider or safely retry with the same key.
- Store the provider invoice ID under a unique constraint.
- Return the existing result for duplicate client requests.
- Log an operation ID, not credentials or full sensitive payloads.

## Module 14: Git sync workflow

### Challenge

Local changes are on `feature/invites`, but Lovable still shows main.

### Reference answer

Push the feature branch, then switch the Lovable project's active synced branch to `feature/invites`. Lovable syncs one branch at a time. Alternatively, open a pull request, merge the branch into main, and keep Lovable on main. Do not force-push main to make the branch appear.

## Module 15: External deployment

### Challenge

A host asks for build command, output directory, and SPA rewrite.

### Reference answer

Inspect the project first.

- For an older Vite SPA, the common values are `npm run build`, `dist`, and an `index.html` fallback.
- For TanStack Start SSR, use the project's configured server build and a compatible runtime or adapter. A static output directory and SPA rewrite may be wrong.

Then configure public environment values, OAuth redirects, monitoring, and production verification for the selected host.

## How to evaluate your work

For every solution, ask:

- Is the user outcome clear?
- Is authorization enforced outside the UI?
- Are failure and recovery states defined?
- Is the change scoped and reversible?
- Is there evidence from tests or observation?
- Does the instruction match the project's actual stack?

Return to the [course overview](README.md).
