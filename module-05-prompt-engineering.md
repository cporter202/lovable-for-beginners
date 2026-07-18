# Module 5: Prompting for Reliable Results

Prompting is product specification in compact form. The most reliable prompts define the user outcome, constrain scope, name important states, and say how success will be verified.

## Learning goals

- Write prompts with outcome, context, constraints, and acceptance criteria
- Build by flow and component instead of generating everything at once
- Use real content and explicit UI states
- Prompt for safe changes and useful verification
- Recover from vague or unsuccessful prompts

## 1. The five-part prompt

### Outcome

State what should become true for the user.

### Context

Name the audience, current behavior, relevant files, data, or prior decisions.

### Requirements

List behavior and content that must exist.

### Constraints

Say what must remain unchanged, what tools or patterns to use, and what is out of scope.

### Acceptance criteria

Define observable checks that prove the task is complete.

```text
Outcome:
Members can filter the reading list by status without losing their search term.

Context:
Use @src/pages/Library.tsx and the existing FilterBar component.

Requirements:
- Status options: All, Want to Read, Reading, Finished
- Keep status and search in the URL query string
- Show the number of matching books
- Include a useful no-results state

Constraints:
- Do not change the card design or database schema
- Reuse existing query and button components
- Preserve keyboard navigation

Acceptance criteria:
- Refreshing the page preserves both filters
- Back and forward navigation restores prior filter state
- Works at 320px, 768px, and desktop widths
- Add and run focused frontend tests
```

## 2. Plan before implementation

Before a large prompt, answer:

- What is the product or feature?
- Who is it for?
- Why will they use it?
- What is the one key action?

Use Plan mode to fill gaps. A strong closing line is:

```text
Ask focused questions about any requirement that would materially change
the data model, user flow, security, or visual direction before proposing a plan.
```

## 3. Build by flow and component

Large page prompts often produce inconsistent results. Work through a user journey and implement reusable parts:

1. Entry point and navigation
2. Primary form or action
3. Confirmation or result
4. Empty, loading, error, and permission-denied states
5. Responsive and accessibility behavior

Use precise interface nouns: button, input, dialog, table, card, tabs, toast, tooltip, checkbox, menu, drawer, and pagination. They communicate more than phrases such as "make the UI better."

## 4. Use real content

Real copy exposes layout constraints. Provide realistic names, prices, dates, errors, and long values. Include edge cases such as a 60-character title or a user with no profile image.

```text
Use realistic book titles and club descriptions. Include one long title,
one missing cover image, one empty note, and one completed book from last year.
```

## 5. Prompt visual direction

Describe tone and decisions, not just adjectives:

```text
Use a restrained editorial style with a white background, near-black text,
forest-green actions, thin gray dividers, compact cards, and generous page margins.
Use Source Serif for display headings and Inter for controls. Avoid gradients,
glass effects, oversized rounded cards, and decorative animation.
```

When the direction is open, ask for design options. When it is fixed, provide fonts, colors, density, references, and what to avoid.

## 6. Protect stable behavior

For authentication, payments, migrations, and shared components, tell Lovable to inspect before editing and isolate the change.

```text
This touches a critical authentication path. First inspect related code and
dependencies. Change only the password-reset flow. Preserve Google sign-in,
session duration, current redirect behavior, and existing RLS policies.
If the requested behavior conflicts with the current architecture, stop and explain.
```

## 7. Ask for verification explicitly

Build mode does not run every testing tool for every request. Say what to verify:

```text
After the change:
- Run the existing test suite and typecheck
- Add a regression test for the bug
- Use browser testing to complete the mobile checkout flow
- Report what was tested and any remaining limitation
```

For large work, implement first and run browser testing in a follow-up message.

## 8. Repair a poor result

Avoid "try again" or "make it nicer." Instead:

1. State what is wrong in observable terms.
2. Select or reference the exact area.
3. Say what must remain unchanged.
4. Provide a target state and acceptance check.
5. Revert first if the current version is substantially worse.

## Practice challenges

1. Rewrite three vague prompts using the five-part structure.
2. Build one feature component by component.
3. Add realistic edge-case content and repair resulting overflow.
4. Use Plan mode for a risky change, then approve only the first milestone.
5. Add explicit test and browser-verification criteria.

## Official references

- [Prompting best practices](https://docs.lovable.dev/prompting/prompting-one)
- [Best practices](https://docs.lovable.dev/tips-tricks/best-practice)
- [Debugging prompts](https://docs.lovable.dev/prompting/prompting-debugging)
- [Test and verify your app](https://docs.lovable.dev/features/testing)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 6 - Full-Stack Apps with Lovable Cloud](module-06-adding-fullstack-capabilities.md)
