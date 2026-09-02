# MyWebsite Repository Guide

This repository is organized around two branch flows:

- `feature/archive` keeps the current website version as an archived reference.
- `feature/development` is the working branch for updates intended to be reviewed and merged into `main`.

The usual workflow is:

1. Work on `feature/development` for edits and improvements.
2. Commit changes on that branch.
3. Open a pull request into `main` when the version is ready.
4. Keep `feature/archive` unchanged as a historical snapshot.

## Branch overview

### `feature/archive`
Use this branch when you want to preserve the current state of the live editorial version.

- It should remain stable.
- It acts as a backup/reference for prior work.
- Avoid making routine edits here unless you intentionally want to preserve an old version.

### `feature/development`
Use this branch for all active iteration and PR preparation.

- This is the branch to edit for new design work.
- It should reflect the version you want reviewed before merging into `main`.

## Common Git commands

### Switch branches

```bash
git checkout feature/archive
git checkout feature/development
```

Alternative modern command:

```bash
git switch feature/archive
git switch feature/development
```

### Check current status

```bash
git status
```

### See all branches

```bash
git branch -a
```

### Create a new branch from the current branch

```bash
git checkout -b feature/my-update
```

or

```bash
git switch -c feature/my-update
```

### Commit work

```bash
git add .
git commit -m "Describe the update"
```

### Push a branch

```bash
git push -u origin feature/development
```

### Pull latest changes

```bash
git pull origin feature/development
```

## Editorial vs PR workflow

### Working in editorial mode

Use `feature/development` when preparing updates that will eventually go to `main`.

```bash
git switch feature/development
```

Then edit the files, commit, and push.

### Preserve current editorial version

If the current site must be archived before changes are merged:

```bash
git switch feature/archive
git status
```

This branch remains available as the historical copy.

### Prepare for PR to main

When the development work is ready:

```bash
git switch feature/development
git status
git add .
git commit -m "Prepare landing page for PR"
git push -u origin feature/development
```

Then open a pull request in GitHub or GitHub Desktop from `feature/development` into `main`.

## VS Code basic Git actions

### 1. Switch branches
- Open the Source Control view.
- Click the branch name in the bottom-left status bar.
- Choose the target branch from the dropdown.

### 2. View file changes
- Open the Source Control panel.
- Review changed files and diffs before committing.

### 3. Stage changes
- Click the `+` icon next to files, or use the "Stage All Changes" button.

### 4. Commit changes
- Enter a commit message in the message box.
- Click the checkmark or Commit button.

### 5. Push to remote
- Click the sync/publish button in the Source Control panel.
- If needed, choose the upstream branch.

### 6. Create a pull request
- Push the branch to GitHub.
- Open the repository in GitHub and click "Compare & pull request".
- Set base branch to `main` and compare branch to `feature/development`.

## Recommended day-to-day flow

```bash
git switch feature/development
git pull origin feature/development
git status
# edit files
# test locally
git add .
git commit -m "Update landing page copy"
git push -u origin feature/development
```

## Notes

- Keep `feature/archive` untouched unless you intentionally want to preserve a snapshot.
- Treat `feature/development` as the branch most likely to be merged into `main`.
- Use clear commit messages so reviewers can quickly understand the purpose of each change.
