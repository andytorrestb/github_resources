# GitHub Collaboration Guidelines

This repository is a learning resource for effective GitHub collaboration. Follow these guidelines to ensure smooth teamwork, code quality, and project stability.

## Getting Started: Forking the Repository

The main repository should be protected from all direct commits. Users are to create forks of the main repository under their own account and and then open up Pull Requests (PR) on Github so team members can review and accept changes.
1. Go to the repository page on GitHub https://github.com/ERAU-CTS/github_resources/tree/main.
2. Click the **Fork** button (top right).
3. Clone your fork to your computer:
	```sh
	git clone https://github.com/<your-username>/github_resources.git
	cd github_resources
	```
4. Make changes and push to your fork (details below).
5. Open a Pull Request from your fork to the original repository.


## Checking Your Branch Status

To see which branch you are currently on and what files have changed (before commiting):
```sh
git status
```
The current branch will be shown near the top (e.g., `On branch main`).

To list all branches:
```sh
git branch
```

To see a summary of recent commits (--oneline is an optional argument for simple output):
```sh
git log --oneline
```

To see what changed in the last commit:
```sh
git show
```

## Main Branch Protection

**Never push directly to `main`.** Only peer-reviewed and tested code should be merged into the main branch. This keeps the main branch stable and production-ready.

### Why Protect the Main Branch?
- Prevents accidental overwrites or breaking changes
- Ensures all code is reviewed and tested
- Maintains a reliable codebase

## Branch Management

When working on a new feature or bugfix, create a new branch from `main`. Use descriptive names and include your own name to avoid conflicts.

**Branch naming convention:**
```
feature/<short-description>-<yourname>
bugfix/<short-description>-<yourname>
refactor/<short-description>-<yourname>
```

**Examples:**
```
git checkout main
git pull origin main
git checkout -b feature/rendezvous_mvp-bob
git checkout -b bugfix/server_crash-bob
```

## Typical Workflow (assuming project is forked to personal account)

1. **Sync with main:**
	```
	git checkout main
	git pull origin main
	```
2. **Create your branch:**
	```
	git checkout -b feature/awesome-feature-yourname
	```
3. **Check your changes with `git diff`:**
	- Before committing, you can review what has changed in your working directory compared to the last commit:
		```sh
		git diff
		```
	- To see changes staged for commit (after `git add`):
		```sh
		git diff --cached
		```
	- Example output:
		```diff
		diff --git a/README.md b/README.md
		index e69de29..b6fc4c6 100644
		--- a/README.md
		+++ b/README.md
		@@ ... @@
		+Added a new section about collaboration.
		```
	- Use this to verify your edits before committing.

4. **Work and commit locally:**
	```
	git add .
	git commit -m "Add awesome feature"
	```
5. **Push your branch:**
	```
	git push origin feature/awesome-feature-yourname
	```
6. **Open a Pull Request (PR):**
	- Go to you repository GitHub and open a PR from your branch to `main`.
	- Add a clear description of your changes.

## Code Review & Merging

- Request reviews from team members.
- Address feedback and make changes as needed.
- Only merge after approval and successful tests.
- Use GitHub's "Squash and merge" or "Rebase and merge" to keep history clean.

**Example: Merging after approval**
1. Reviewers approve the PR.
2. All checks/tests pass.
3. Merge using GitHub UI.

## Keeping Your Branch Up to Date

If `main` has new changes, update your branch:
```
git checkout main
git pull origin main
git checkout feature/awesome-feature-yourname
git merge main
```
Resolve any conflicts, commit, and push again.

## Summary

- Protect `main`—no direct pushes
- Use descriptive, unique branch names
- Always open PRs for review
- Merge only after approval and tests