# GitHub Collaboration Guidelines

This repository is a learning resource for effective GitHub collaboration. Follow these guidelines to ensure smooth teamwork, code quality, and project stability.

## Getting Started: Cloning the Repository

To get a copy of this project on your computer:
```sh
git clone https://github.com/ERAU-CTS/github_resources.git
cd github_resources
```

## Checking Your Branch Status

To see which branch you are currently on:
```sh
git status
```
The current branch will be shown near the top (e.g., `On branch main`).

To list all branches:
```sh
git branch
```

## Viewing Changes and Commit History

To see what files have changed (before you commit):
```sh
git status
```

To see a summary of recent commits:
```sh
git log --oneline
```

To see what changed in the last commit:
```sh
git show
```

## Forking the Repository (for outside contributors)

If you are not a member of the team, you can still contribute by forking:
1. Go to the repository page on GitHub.
2. Click the **Fork** button (top right).
3. Clone your fork to your computer:
	```sh
	git clone https://github.com/<your-username>/github_resources.git
	cd github_resources
	```
4. Make changes and push to your fork.
5. Open a Pull Request from your fork to the original repository.

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
```

**Examples:**
```
git checkout main
git pull origin main
git checkout -b feature/login-form-andy
git checkout -b bugfix/navbar-responsive-jane
```

## Typical Workflow

1. **Sync with main:**
	```
	git checkout main
	git pull origin main
	```
2. **Create your branch:**
	```
	git checkout -b feature/awesome-feature-yourname
	```
3. **Work and commit locally:**
	```
	git add .
	git commit -m "Add awesome feature"
	```
4. **Push your branch:**
	```
	git push origin feature/awesome-feature-yourname
	```
5. **Open a Pull Request (PR):**
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

Following these steps will help the team collaborate efficiently and maintain high code quality.

# github_resources
Getting started with GitHub.