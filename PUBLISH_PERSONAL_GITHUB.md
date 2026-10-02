# Publish Yo Quiero skills to GitHub (personal account)

Push this project to **https://github.com/brianbeavers/yo-quiero-skills**.

## Before you start

In a terminal on your machine (logged into personal GitHub):

```bash
gh auth status
```

If needed: `gh auth login` with your personal account.

## Step 1 — Create an empty repo

1. Open https://github.com/new
2. **Repository name:** `yo-quiero-skills`
3. **Owner:** `brianbeavers`
4. **Public**
5. Do **not** add README, .gitignore, or license
6. Create repository

## Step 2 — Push from this project

```bash
cd path/to/this-project

git remote add github https://github.com/brianbeavers/yo-quiero-skills.git
# or, if you prefer origin on GitHub:
# git remote rename origin cursor-origin
# git remote add origin https://github.com/brianbeavers/yo-quiero-skills.git

git push -u github main
```

## Step 3 — Install elsewhere

```bash
git clone https://github.com/brianbeavers/yo-quiero-skills.git ~/.cursor/skills/yo-quiero
# or copy .cursor/skills/yo-quiero-mode and yo-quiero-labeling into a project
```

Demo board: open `docs/yo-quiero/how-it-works/board.html` after clone.
