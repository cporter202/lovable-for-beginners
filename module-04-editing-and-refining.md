# Module 4: Editing, Knowledge, and Iteration

Good Lovable work is iterative. Use the smallest editing surface that fits the change, give the agent persistent context where useful, and keep version history as part of the workflow.

> Practice these editing workflows: [Open your project in Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Use all four preview-toolbar modes
- Distinguish workspace knowledge, project knowledge, and skills
- Reference files, lines, and other projects
- Use version history, bookmarks, and comments
- Make focused changes without disturbing stable areas

## 1. The preview toolbar

The preview toolbar replaces the old Visual Edits experience.

| Mode | Best use |
| --- | --- |
| Select elements | Point at one or more elements and request a scoped change |
| Edit text inline | Fix copy directly without writing a prompt |
| Draw annotation | Explain position, grouping, or spatial changes visually |
| Add a comment | Leave contextual feedback for yourself or collaborators |

### Select elements

Press `S`, select an element, describe the change, and send it. Hold Cmd on macOS or Ctrl on Windows/Linux to select multiple elements. Selection-based requests use normal message credits.

```text
Make these two cards equal height and align their action rows.
Keep the current copy, colors, and mobile stacking behavior.
```

### Edit text inline

Press `T`, click text, edit, and send. Inline text edits are currently free for the first 100 edits per user each day, then use credits.

### Draw annotations

Press `D`, draw over the preview, add a short instruction, and send. This is useful for moving or replacing groups that are cumbersome to describe.

### Comments

Pin comments to visible elements when feedback should remain attached to the design. Comments support collaboration but do not themselves ask Lovable to change code.

## 2. Knowledge

Knowledge provides persistent instructions. Lovable reads it along with project code and supported instruction files such as `AGENTS.md` or `CLAUDE.md`.

### Workspace knowledge

Workspace knowledge applies across projects and is managed by workspace owners or admins. Use it for shared coding standards, libraries, architecture rules, testing expectations, brand voice, and organization-wide constraints. It supports up to 10,000 characters.

### Project knowledge

Project knowledge applies to one project. Use it for:

- Product purpose and audience
- Domain terms and business rules
- Architecture and database conventions
- Brand colors, typography, and voice
- Supported browsers and accessibility target
- Explicit non-goals

Example:

```text
Product
- A reading tracker for small neighborhood book clubs.
- The primary action is adding a book to the current month's list.

Design
- Editorial, warm, and compact.
- Use Source Serif for display text and Inter for controls.
- Meet WCAG AA contrast. Never rely on color alone for status.

Engineering
- Keep server state in React Query.
- Validate forms on client and server.
- Every user-owned table must enforce row-level security.
- Add tests for changed behavior and verify important flows in the browser.
```

Update knowledge when the stack or product changes. Stale knowledge is worse than missing knowledge because it repeatedly steers the agent in the wrong direction.

### Skills versus knowledge

Knowledge is always present. Skills are reusable instructions loaded only for matching tasks, such as a release checklist or content workflow. Put universal rules in knowledge and specialized procedures in skills.

## 3. References

Use references to reduce ambiguity:

- `@src/components/BookCard.tsx` for a file
- An exact line or range from the code editor
- `@BrandSite` for a project in the same workspace
- Attached screenshots, images, files, or connector data

Cross-project references are read-only and limited to projects you can access in the same workspace.

## 4. Version history

Lovable tracks project changes. Use history to preview an older state, revert, or edit an earlier message and take a different approach. Later chat remains available, so reverting does not erase the record of what happened.

Use bookmarks for milestones such as:

- Initial layout approved
- Authentication working
- Schema migrated
- Pre-launch security review passed
- Version currently in production

Before a risky change, create a clear milestone or sync to Git. After a bad change, prefer reverting to a known working state over layering vague repair prompts.

## 5. Focused iteration pattern

```text
Update only the selected pricing cards.

Change:
- Align prices on one baseline
- Add a visible "Most popular" label to Pro
- Improve mobile spacing

Preserve:
- Existing plan names, prices, and feature copy
- Header and footer
- Checkout behavior
- Current color tokens

Verify:
- No text overflow at 320px width
- Keyboard focus remains visible
```

## Practice

Use all four preview-toolbar modes on one project. Add project knowledge, reference a specific file in a prompt, bookmark a working version, make a deliberate breaking edit, and restore the bookmark.

## Official references

- [Edit from the preview](https://docs.lovable.dev/features/preview-toolbar)
- [Define workspace and project knowledge](https://docs.lovable.dev/features/knowledge)
- [Cross-project referencing](https://docs.lovable.dev/features/cross-project-referencing)
- [Project comments](https://docs.lovable.dev/features/project-comments)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 5 - Prompting for Reliable Results](module-05-prompt-engineering.md)
