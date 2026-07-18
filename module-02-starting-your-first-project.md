# Module 2: Starting Your First Project

The first build sets the architecture, design language, and scope that later prompts inherit. A good start is less about writing a giant specification and more about making the product, audience, main action, and constraints clear.

> Ready to practice? [Start a new project in Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Choose the right way to start a project
- Write a useful initial prompt
- Use design guidance and references intentionally
- Evaluate the first build before adding features
- Avoid copying protected content or connecting a backend too early

## 1. Ways to start

### Start from a prompt

This is the default for most projects. State the product, user, primary workflow, required screens, visual direction, and what should not be built yet.

### Remix a project

Remixing creates a new project from the current state of a project you own, can access, or that has public remixing enabled. The original remains unchanged. A project owned by someone else cannot be remixed when it is connected to Supabase.

Use remixing for exploration and internal reuse. Confirm that you have permission to reuse any code, copy, branding, and assets.

### Start with an image, sketch, or screenshot

Attach a Figma screenshot, wireframe, hand-drawn sketch, or visual reference. Explain what to copy and what to reinterpret. A screenshot is context, not proof that you have rights to duplicate a site.

Good instruction:

```text
Use the attached screenshot as layout inspiration only.
Keep the information hierarchy and spacious rhythm, but use original copy,
our own teal and coral palette, and different imagery. Do not copy logos,
brand names, or proprietary content.
```

### Use a design template or design system

Availability depends on plan. Business workspaces can use design templates, and Enterprise workspaces can also provide centrally managed design systems. These are useful when consistency matters more than a blank-canvas start.

### Reference another project

Within the same workspace, use `@ProjectName` to ask Lovable to read and reuse components, assets, chat context, authentication patterns, or integrations from a project you can access. Cross-project access is read-only and respects project permissions.

## 2. Write the initial prompt

Use this structure:

```text
Product:
Build a lightweight appointment request app for an independent dog groomer.

Audience:
Busy local pet owners using phones.

Primary flow:
Choose a service, select an available time, enter contact details,
review the request, and see a confirmation.

Screens:
Home, services, booking form, confirmation.

Design direction:
Friendly and trustworthy, not childish. Use warm white, forest green,
and a small coral accent. Use accessible contrast and real copy.

Behavior and states:
Validate required fields, show inline errors, include loading and success states,
and make every screen responsive.

Scope:
Use local sample data. Do not add authentication, payments, or a backend yet.

Before building, ask focused questions if any requirement is ambiguous.
```

## 3. Use design guidance

For visually open-ended requests, Lovable may show three lightweight design directions before building. Compare typography, layout, color, spacing, and tone. You can refine a direction before selecting it.

If your preferences are already specific, Lovable may ask short design questions instead. If the prompt has a clear visual reference or only requests a small functional change, it may build directly.

Choose a direction based on the user's task, not novelty. Check:

- Is the primary action obvious?
- Is text readable at phone width?
- Does the visual tone match the audience?
- Can the system grow to more screens without becoming inconsistent?

## 4. Review the first build

Do not immediately ask for five more features. First inspect:

- Routing and navigation
- Responsive layout at mobile, tablet, and desktop widths
- Real content length and overflow
- Empty, loading, error, disabled, and success states
- Keyboard focus and labels
- Whether buttons actually do what their labels promise
- Reusable components and consistent spacing

Use a focused follow-up:

```text
Review this first build before adding features.
List any broken interactions, accessibility issues, mobile layout problems,
and missing states. Do not change code yet.
```

Run that in Plan mode. Then approve a narrow set of fixes in Build mode.

## Hands-on project

Create one project using a prompt and one using an image reference. For each:

1. Record the intended user and key action in Project knowledge.
2. Inspect the first build at three viewport sizes.
3. Make one preview-toolbar edit.
4. Make one prompt-based behavioral edit.
5. Revert one change and confirm the earlier version returns.

## Checklist

- [ ] The initial prompt names a product, user, and primary flow
- [ ] The scope explicitly excludes later features
- [ ] Realistic content is used instead of lorem ipsum
- [ ] Visual references are used legally and with clear adaptation instructions
- [ ] The first build has been reviewed before backend work begins

## Official references

- [Quick start](https://docs.lovable.dev/introduction/getting-started)
- [Design guidance](https://docs.lovable.dev/features/design-guidance)
- [Cross-project referencing](https://docs.lovable.dev/features/cross-project-referencing)
- [Control project access](https://docs.lovable.dev/features/project-visibility)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 3 - Build Mode and Plan Mode](module-03-understanding-lovable-modes.md)
