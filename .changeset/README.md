# Changesets

This repository uses [changesets](https://github.com/changesets/changesets) to manage version bumping, changelogs and GitHub releases.

## Adding a changeset

When you make a change that needs to be documented in the changelog:

1. Run `pnpm changeset` in the root of the repository
2. Follow the prompts to select the type of change (patch, minor, major)
3. Write a summary of the changes that will be included in the changelog
4. Commit the generated changeset file along with your changes

## Workflow

1. Feature branches and fixes are merged into `dev` branch
2. When code is merged to `dev`, changesets are used to version the package and update the changelog
3. Code flows from `dev` → `staging` → `main`
4. When merged to `main`, a GitHub release is automatically created with the changelog
5. Hotfixes branch from `main`, make changes, and merge back to `main` directly

## Hotfix Process

For urgent fixes:

1. Create a branch from `main` named `hotfix/your-fix-name`
2. Make your changes
3. When merged to `main`, the workflow will:
   - Automatically create a changeset
   - Bump the version (patch)
   - Create a GitHub release
