# Module 7: Inspecting and Editing Code

The feature once commonly called Code Mode is now documented as the code editor. It provides direct access to project files for inspection, targeted manual edits, downloads, and precise references back into chat.

Code editing is currently available on paid plans. Build mode does not require you to edit code manually.

## Learning goals

- Navigate the code editor and identify a project's stack
- Search, inspect, edit, format, and download files
- Reference files and exact lines in prompts
- Make small manual changes safely
- Know when Git sync or a local IDE is a better tool

## 1. Start by identifying the project

Before changing code, inspect:

- `package.json` for framework, scripts, and dependencies
- Route files for page structure
- `src/components` or equivalent for reusable UI
- Styling tokens and Tailwind configuration
- Backend configuration and migrations
- Test files and test scripts
- `.env` names, without exposing values

Current projects may use TanStack Start or an older React and Vite stack. File layout, routing, rendering, and deployment requirements can differ.

## 2. Code editor capabilities

The editor can:

- Browse and search the full project tree
- Inspect and edit files directly
- Format code
- Copy or download files
- Preview Markdown as rendered text
- Download the full codebase
- Reference files in chat with `@`
- Reference an exact line or range from the line-number control

Changes made in the editor affect the project immediately. Make one coherent edit at a time and check the preview.

## 3. Use references instead of pasting code

```text
Review @src/components/BookForm.tsx:42-88.
Explain why validation errors appear only after a second submit.
Do not modify code yet.
```

After the cause is clear:

```text
Fix the validation timing in the referenced form.
Preserve the schema, field labels, and submit behavior.
Add a regression test and run it.
```

Exact references improve scope and leave a clearer review trail.

## 4. Safe manual edits

Good manual edits are small and obvious:

- Correcting copy or an import
- Adjusting one token or class
- Fixing a simple condition
- Adding a missing type
- Updating a configuration value that is safe for source control

Use Build mode for cross-file features, migrations, auth, payment logic, or changes that need systematic tests.

After a manual edit:

1. Format the file.
2. Check diagnostics and imports.
3. Refresh the preview.
4. Run the relevant test, typecheck, or build command.
5. Review the changed file in history or Git.

## 5. Environment variables and secrets

Variable names beginning with `VITE_` are public at runtime because their values are embedded in frontend output. Never store private API keys in them.

Use Cloud secrets and an edge function for private credentials. It is fine for frontend code to contain identifiers or publishable keys designed for browser use, but confirm each service's security model.

## 6. Download versus Git sync

Download the codebase when you need a one-time copy. Use Git sync when you need:

- Continuous backup
- Local development
- Branches and pull requests
- Code review
- External CI/CD or hosting
- Collaboration with developers

Do not edit the same synced branch simultaneously in Lovable and locally without coordination. Pull and inspect changes before pushing to reduce conflicts.

## Practice

1. Find the framework and build scripts in `package.json`.
2. Locate the component that renders the main card.
3. Reference one exact line in Plan mode and ask for an explanation.
4. Make a one-line manual copy edit.
5. Use Build mode for a related behavioral change and ask it to run a test.

## Official references

- [View and edit project code](https://docs.lovable.dev/features/code-mode)
- [Implement changes in Build mode](https://docs.lovable.dev/features/agent-mode)
- [Git sync overview](https://docs.lovable.dev/integrations/git-sync-overview)
- [Security overview](https://docs.lovable.dev/features/security)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 8 - Publishing and Operating Your App](module-08-deploying-and-publishing.md)
