# Module 1: Welcome to Lovable

Lovable is a full-stack AI development platform for building, iterating on, and deploying web applications with natural-language instructions. It creates real, editable code and can manage the frontend, backend, database, authentication, integrations, testing, security checks, and publishing workflow.

This course was reviewed against the official Lovable documentation on July 18, 2026.

## Learning goals

By the end of this module, you will be able to:

- Explain what Lovable does and what it does not do
- Distinguish an account, workspace, project, preview, and published app
- Navigate the dashboard and project editor
- Create a small first project
- Use version history and understand that publishing is a separate step

## 1. How Lovable works

You describe an outcome. Lovable plans or implements it, generates code, and shows the result in a live preview. You can then refine the app with more prompts, direct preview edits, code edits, or changes from a synced Git repository.

Lovable is focused on web applications. It can build responsive web experiences that work well on phones, but it does not generate native iOS or Android apps.

Current Lovable projects can use different frontend stacks:

- New projects created from May 13, 2026 use TanStack Start with server-side rendering by default, except on Enterprise plans.
- Older projects use React and Vite and continue to work normally.
- Tailwind CSS is commonly used for styling.

Do not assume every Lovable project has the same structure. When working with code or deploying elsewhere, inspect the project's `package.json` and existing configuration.

## 2. Core terms

| Term | Meaning |
| --- | --- |
| Account | Your personal Lovable identity and sign-in |
| Workspace | The home for projects, members, billing, settings, and shared connections |
| Project | One app and its code, chat history, settings, preview, and deployment state |
| Prompt | An instruction or question sent to Lovable |
| Build mode | The mode that changes code and verifies work; some docs also call this Agent mode |
| Plan mode | A read-only reasoning mode for questions, investigation, and implementation plans |
| Preview | The current working version inside the editor |
| Published app | A deployed snapshot available at a live URL |
| Lovable Cloud | Managed hosting and backend services including database, auth, storage, functions, jobs, secrets, logs, and AI |
| Knowledge | Persistent workspace or project instructions that Lovable reads when working |

## 3. The dashboard

The dashboard is the starting point for new projects and the home for existing ones. Its prompt input can accept typed text, voice, images, files, screenshots, references, and supported connectors.

From the dashboard you can:

- Start a project from a prompt
- Open recent projects
- Search and organize projects
- Switch workspaces
- Manage connectors, members, settings, plans, and usage
- Review notifications and product updates

Inside a project, the main working areas are chat, preview, Cloud, code, project settings, Share, and Publish. Some controls move into menus on narrow screens.

## 4. Your first project

Open Lovable and create a new project with this prompt:

```text
Build a responsive one-page personal reading list.

Include:
- A header with the title "My Reading List"
- Three book cards with real example titles and authors
- A status filter for Want to Read, Reading, and Finished
- A calm editorial style with strong contrast and readable typography
- Useful empty, hover, and mobile states

Use local sample data only. Do not add authentication or a database yet.
```

When the first build finishes:

1. Check the desktop and mobile previews.
2. Click each control and note what is functional versus decorative.
3. Ask Build mode to fix one specific issue.
4. Open version history and identify the two edits.
5. Do not publish yet.

## 5. A reliable beginner workflow

Use this loop throughout the course:

1. Define the user and the main action.
2. Use Plan mode when the problem is unclear or risky.
3. Make one meaningful change in Build mode.
4. Review the diff and preview.
5. Test the behavior that changed.
6. Revert or refine if needed.
7. Publish only after testing and security review.

## Important boundaries

- Preview changes are not automatically pushed to the published app. Use Publish, then Update for later releases.
- Project access and published website access are separate settings.
- AI-generated code can contain bugs or insecure assumptions. You still need to test and review it.
- Never paste secret API keys into frontend code or ordinary prompts. Use managed secrets and server-side functions.
- Features and plan limits change. Check the live documentation before making a purchase or launch decision.

## Practice checkpoint

You are ready for Module 2 when you can:

- Find your workspace and project settings
- Switch between desktop and mobile preview
- Explain the difference between preview and published app
- Locate version history
- Describe the difference between Plan mode and Build mode

## Official references

- [Welcome to Lovable](https://docs.lovable.dev/introduction/welcome)
- [Create an account](https://docs.lovable.dev/introduction/create-an-account)
- [Dashboard overview](https://docs.lovable.dev/introduction/dashboard-overview)
- [Lovable FAQ and current tech stacks](https://docs.lovable.dev/introduction/faq)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 2 - Starting Your First Project](module-02-starting-your-first-project.md)
