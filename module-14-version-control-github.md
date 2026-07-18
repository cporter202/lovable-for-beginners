# Module 14: Git Sync and Collaboration

Git sync connects one Lovable project to one repository and keeps the active branch synchronized in both directions. Lovable currently supports GitHub and GitLab. This module focuses on GitHub.

> Connect a practice project to GitHub: [Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github).

## Learning goals

- Understand workspace connections and project repository links
- Set up two-way GitHub sync
- Work safely with branches, local development, pull requests, and CI
- Avoid conflicts and distinguish Git sync from the GitHub API connector

## 1. How Git sync works

GitHub sync has two layers:

1. A workspace connection authorizes Lovable to access a GitHub account or organization through the Lovable GitHub app.
2. A project repository link connects one Lovable project to one repository.

A workspace can have multiple GitHub connections. Once a project is linked:

- Lovable changes are committed and pushed to the active branch.
- Commits pushed to that branch sync back into Lovable.
- Lovable edits and syncs one branch at a time.

Commits on other branches do not appear until you switch Lovable to that branch or merge them into the active branch.

Git sync is available across current plans. The code editor and one-time code download have separate plan requirements.

## 2. Why connect GitHub

- Keep code in an account you control
- Work in a local IDE
- Use branches and pull requests
- Review changes with developers
- Run CI and automated checks
- Deploy to external platforms
- Maintain an auditable history

You do not need GitHub to build or publish entirely within Lovable.

## 3. Connect a project

Workspace owners or admins create the GitHub workspace connection. Project or workspace owners and admins link or disconnect a project repository. Editors can work with the synced repository and view status.

Before linking:

- Confirm the target GitHub account or organization.
- Confirm repository visibility.
- Check organization policies and Lovable GitHub app access.
- Decide the initial active branch.
- Make sure no unrelated repository is selected.

After linking, verify a small Lovable edit appears as a commit in GitHub, then push a harmless GitHub edit and confirm it appears in Lovable.

## 4. Branch workflow

For a meaningful feature:

1. Start from an up-to-date main branch.
2. Create a feature branch in Lovable or GitHub.
3. Switch Lovable to that branch.
4. Build and test the feature.
5. Open a pull request in GitHub.
6. Review CI and code changes.
7. Merge through GitHub.
8. Switch Lovable back to main and confirm sync.

Use descriptive branch names such as `feature/club-invitations` or `fix/member-book-access`.

## 5. Local development

Clone the repository and follow its actual scripts:

```bash
git clone <repository-url>
cd <repository-name>
npm ci
npm run dev
```

Inspect `package.json`; newer TanStack Start and older React/Vite projects can differ.

Before pushing:

```bash
git pull --rebase
npm test
npm run build
git status
```

Use the repository's real test, lint, and typecheck commands. Do not commit `.env` secrets, build output, or generated local files unless the repository intentionally tracks them.

## 6. Avoiding sync conflicts

- Coordinate who is editing the active branch.
- Pull before local work and before pushing.
- Keep commits focused.
- Avoid force-pushing the branch Lovable is actively syncing.
- Resolve conflicts in Git, test the result, then let Lovable sync the resolved commit.
- Use a separate branch for risky or long-running local changes.

Version history in Lovable and Git history complement each other. Lovable history is convenient for project iteration; Git provides portable code history and collaboration workflows.

## 7. Pull requests and CI

A useful pull request explains:

- User outcome
- Main implementation decisions
- Schema or configuration changes
- Security implications
- Tests and browser flows run
- Deployment or rollback notes

CI should at minimum install dependencies reproducibly and run the project's build and tests. Add lint, typecheck, security, and deployment checks according to risk.

## 8. Git sync versus GitHub API connector

Git sync stores and synchronizes your project's source code. The GitHub API connector lets a deployed Lovable app read or manage repositories, issues, and pull requests. They solve different problems and have different permissions.

## Practice

1. Link a disposable project to GitHub.
2. Verify a change in both directions.
3. Create a feature branch and switch Lovable to it.
4. Make a small tested change.
5. Open and merge a pull request.
6. Return Lovable to main and verify the merged version.

## Official references

- [Git sync overview](https://docs.lovable.dev/integrations/git-sync-overview)
- [Sync with GitHub](https://docs.lovable.dev/integrations/github)
- [View and edit project code](https://docs.lovable.dev/features/code-mode)
- [Deployment and ownership options](https://docs.lovable.dev/tips-tricks/deployment-hosting-ownership)

[Open Lovable](https://afflat3a2.com/trk/lnk/7BB81506-2890-47A0-9BDD-D03343EC49CB/?o=32337&c=918277&a=184866&k=D5D811C96B2D90FAF2ABF3287B46C45F&l=38178&s1=github)

Next: [Module 15 - External Hosting and Portability](module-15-deploying-to-custom-clouds.md)
