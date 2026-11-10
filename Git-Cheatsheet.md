# Git Cheatsheet

A quick reference guide to Git commands, concepts, and workflows.

---

## 1. What is Git?

Git is a **distributed version control system** that tracks changes in files over time.

It helps developers:
- Track changes in their code.
- Save different versions of projects.
- Undo mistakes.
- Collaborate with other developers.

### Git vs GitHub

| Git | GitHub |
|---|---|
| Version control system | Online code hosting platform |
| Works locally | Stores repositories online |
| Tracks project history | Hosts and shares project history |

---

## 2. Basic Git Commands

| Command | Description |
|---|---|
| `git --version` | Checks the installed Git version |
| `git init` | Initializes a Git repository |
| `git status` | Shows the current repository status |
| `git add filename` | Stages a particular file |
| `git add .` | Stages all changes in the current directory |
| `git commit -m "message"` | Saves staged changes as a commit |
| `git log` | Displays commit history |

### Example

```bash
git init
git add hello.py
git commit -m "Initial commit"
git status
```

---

## 3. Git Configuration

Git needs your identity to associate commits with their author.

### Set your identity

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### View your configuration

```bash
git config --global user.name
git config --global user.email
```

### Other useful configuration

```bash
git config --global --list
```

Displays your global Git configuration.

**Note:** If you use GitHub's email privacy protection, configure your GitHub noreply email instead of exposing your personal email.

---

## 4. Understanding Branches

A branch is an independent line of development within a repository.

| Command | Description |
|---|---|
| `git branch` | Lists local branches |
| `git branch -M main` | Renames the current branch to `main` |

### Important terminology

- `main`: Common default branch name.
- `master`: Older default branch name.
- Branches allow developers to experiment without directly changing the main development line.

---

## 5. Connecting Git to GitHub

A **remote repository** is a version of your project hosted on another computer or online platform.

### Add a remote repository

```bash
git remote add origin <repository-url>
```

Here, `origin` is the conventional nickname for the remote repository.

### View remote repositories

```bash
git remote -v
```

### Upload commits to GitHub

```bash
git push -u origin main
```

- `push`: Uploads local commits.
- `origin`: Identifies the remote repository.
- `main`: Specifies the branch.
- `-u`: Sets the upstream tracking relationship for future pushes.

After setting the upstream, you can generally use:

```bash
git push
```

---

## 6. Downloading Changes from GitHub

### Fetch

```bash
git fetch origin
```

Downloads new commits and remote-tracking information without integrating them into your current branch.

### Pull

```bash
git pull origin main
```

Fetches changes and integrates them into your current branch.

**Difference:**
- `fetch`: Downloads information; doesn't automatically update your working files.
- `pull`: Downloads and integrates changes.

---

## 7. Understanding the Git Workflow

Git uses three important areas:

1. **Working Directory:** Where you create and modify files.
2. **Staging Area:** Where you select changes for your next commit.
3. **Local Repository:** Where Git stores committed project history.

### Workflow

```text
Working Directory
       |
       | git add
       v
Staging Area
       |
       | git commit
       v
Local Repository
       |
       | git push
       v
GitHub Repository
```

---

## 8. Important Git Terminology

| Term | Meaning |
|---|---|
| Repository | A project managed by Git |
| Commit | A saved checkpoint of project changes |
| Branch | An independent line of development |
| Staging | Selecting changes for the next commit |
| Remote | A repository hosted elsewhere |
| Push | Uploading local commits |
| Pull | Downloading and integrating remote changes |
| Fetch | Downloading remote updates without integrating them |
| Clone | Creating a local copy of a remote repository |
| Merge | Combining changes from different development branches |
| HEAD | Reference to the currently checked-out commit |

---

## 9. Correcting the Latest Commit

If you need to update the author information of your latest commit while keeping its message:

```bash
git commit --amend --reset-author --no-edit
```

- `--amend`: Modifies the latest commit.
- `--reset-author`: Resets the author to your currently configured identity.
- `--no-edit`: Keeps the existing commit message.

Use this carefully, especially after a commit has already been shared.

---

## 10. Useful Git Tips

- Always check `git status` when you're unsure about your repository.
- Write meaningful commit messages.
- Commit related changes together.
- Pull remote changes before starting work on another device.
- Never upload passwords, API keys or other secrets to GitHub.
- Keep your repository organized.

---

<!-- ## My Learning Progress

- [x] Installed Git
- [x] Configured Git identity
- [x] Initialized a repository
- [x] Staged files
- [x] Created my first commit
- [x] Connected Git to GitHub
- [x] Pushed my first project

**Repository:** Python-Journey

**Learning phase:** Phase 0 — Development Environment & Tools -->

*This cheatsheet will be updated as I learn more Git commands.*