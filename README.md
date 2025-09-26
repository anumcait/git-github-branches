# ﻿GIT-GITHUB-BRANCHES

1. Create a new local repo and initial commit

### inside your project folder
git init
echo "git-github-branches" > README.md
### create a sensible .gitignore (example below)
```
echo "node_modules/" > .gitignore
git add README.md .gitignore
git commit -m "chore: initial commit (add README and .gitignore)"
```
2. Create the remote GitHub repo

Via web UI: GitHub → New repository → name it → do NOT initialize with README (since you already have one). Copy the remote URL.

Manual push:
```
git remote add origin git@github.com:youruser/project-name.git
git branch -M main   # set local branch name to main
git push -u origin main
```
3. Create dev and feature branches (local → push)
```
# create dev branch
git checkout -b dev
git push -u origin dev

# create a feature branch off dev
git checkout -b feature/add-login dev
# do work, stage changes, commit
git add .
git commit -m "feat(auth): add login endpoint and tests"
git push -u origin feature/add-login

```

4. Use Pull Requests (PRs) to merge

Use Pull Requests (PRs) to merge

On GitHub create a PR from feature/* → dev. Add reviewers, description, and link to issue.

After approvals, merge using one of three merge options (Merge commit, Squash and merge, Rebase and merge). Pick policy (recommended: squash for tidy history, or no-ff merges to preserve feature merges).

5. Integrate dev into main with PR

When dev is ready (staged for a release), open PR dev → main, run CI, get approvals, merge. Tag the commit for a release (next step).

6. Create tags and releases
```
# annotated tag (recommended)
git checkout main
git pull origin main
git tag -a v1.0.0 -m "Release v1.0.0 - initial stable release"
git push origin v1.0.0   # just the tag
# or push all tags
git push --tags
```
7. Use .gitignore and tags — included below (example .gitignore for Node + common)
```
# Node
node_modules/
dist/
.env
.DS_Store

# OS
*.log
.idea/
.vscode/

# Python (if mixed)
__pycache__/
*.pyc

```

8. Document everything in markdown
```
README.md
docs/
  tasks.md
  branching.md
  PR_CHECKLIST.md
.github/
  PULL_REQUEST_TEMPLATE.md
```

### Branching model & naming conventions (recommended)

- main — production-ready (always green)
- dev — integration branch (next release integration)
- feature/<short-desc> — feature branches off dev
- bugfix/<issue-id>-short-desc — fixes
- hotfix/<version>-desc — emergency fixes off main
- release/x.y.z — optional pre-release stabilization

Keep branch names lowercase, short, and hyphenated. 

Example: feature/add-payments or bugfix/42-login-error.

### Screens :

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/898f7bc5-d97a-478b-8945-d27030f1c166" />
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/1e197d92-5e29-4430-8096-d5542f778fe2" />
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/481ae406-6403-4daf-972a-7080f2b128ee" />
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/cab848ab-093e-410e-a308-e25a60464178" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/fd8ca758-6f23-48ad-a67d-68072b88500d" />

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/34dc87ef-6ab7-4e6e-9c76-0bfe4f546514" />
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/22fc6126-ca80-4093-91cb-9968e48a4deb" />
<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/506b2b2e-27ea-4fe2-ac2d-db64ea89ae7f" />










