Introduction to `Git` 
==============
Myeong Lee and Kevin Lybarger
-------------

# Git and GitHub — Background and Exercise

## Background

* Git is a distributed version control system for tracking changes, collaborating, and recovering prior states.
* GitHub is a hosted platform for Git repositories that adds pull requests, code review, issues, and permissions.
* Typical student workflow for contributing to a class repository: fork the upstream repo to your GitHub account, clone your fork locally, make changes on your fork, push to your fork, open a pull request to the upstream repo.

---

## Prerequisites

1. **Git installed**

   * Windows: install "Git for Windows" from git-scm.com. Use Git Bash or PowerShell.
   * macOS: Git is often preinstalled. Otherwise install via Xcode Command Line Tools or from git-scm.com.
   * Linux: install via your package manager, for example `sudo apt install git` or `sudo dnf install git`.
2. **GitHub account** and the ability to sign in on the web.
3. **One-time Git identity on your machine**

   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```
4. **Authentication for pushes over HTTPS**

   * When Git prompts for a password, use a GitHub personal access token. Store it in your OS credential manager when asked.

---

## Exercise: Fork, edit, and contribute to the class repository

You will contribute a short introduction file to the upstream class repo and submit it via a pull request.

> Upstream repository: `https://github.com/lybarger/IT700`

### A. Fork the repository on GitHub

1. Open the upstream repo in your browser.
2. Select **Fork**. Accept defaults to create `https://github.com/<your-username>/IT700`.

### B. Clone **your fork** to your computer

1. On your fork’s page, select the green **Code** button and copy the **HTTPS** URL.
2. Open a terminal:

   * Windows: Git Bash or PowerShell
   * macOS: Terminal
   * Linux: your preferred terminal
3. Choose or create a working folder, then run:

   ```bash
   git clone https://github.com/<your-username>/IT700.git
   cd IT700
   ```
4. Verify you are inside the repo:

   ```bash
   git status
   ```

### C. Add your introduction file

1. Create a Markdown file in the `introductions/` folder named with your last name, for example `introductions/garcia.md`.

   * Use any text editor. Add your name and 1–2 sentences on research interests.
2. Stage, commit, and push to **your fork**:

   ```bash
   git add introductions/<your-last-name>.md
   git commit -m "Add introduction: <Your Name>"
   git push origin main
   ```

   * If the default branch is not `main`, replace `main` with the default shown by `git branch -a`.

### D. Open a pull request to the upstream repository

1. In your fork on GitHub, click **Contribute** or **Compare & pull request**.
2. Ensure the comparison is:

   * **base repository**: `lybarger/IT700`, **base**: `main`
   * **head repository**: `<your-username>/IT700`, **compare**: `main` (or your branch if you used one)
3. Write a brief description and click **Create pull request**.

### E. Keep your fork and local clone up to date

Once your PR is merged, sync with upstream so your fork and local copy include classmates’ changes.

1. Add the upstream remote once:

   ```bash
   git remote add upstream https://github.com/lybarger/IT700.git
   git remote -v
   ```
2. Fetch upstream updates and integrate them:

   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```
3. Push the updated main to **your fork**:

   ```bash
   git push origin main
   ```

---

## Minimal Git command reference for this exercise

```bash
# clone your fork
git clone https://github.com/<you>/IT700.git
cd IT700

# create or edit files, then:
git add <path>
git commit -m "Message"
git push origin <branch>

# set and use upstream
git remote add upstream https://github.com/lybarger/IT700.git
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```
