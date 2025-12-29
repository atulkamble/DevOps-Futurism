## 🔧 **Git Commands with Examples (DevOps & Interview-Ready Guide)**

![Image](https://nvie.com/img/git-model%402x.png)

![Image](https://media.brntn.me/01-version-control_gitflow.drawio.png)

![Image](https://wac-cdn.atlassian.com/dam/jcr%3A1896adb1-5d49-419a-9b50-3a36adac186c/09.svg?cdnVersion=3110)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AXurNAi3h2jpD67Pq2OgmrQ%402x.png)

This is a **practical, real-world Git command reference** you can use for **daily DevOps work, CI/CD pipelines, and interviews**.

---

## 📌 1. Basic Git Setup (One-Time)

```bash
git config --global user.name "Atul Kamble"
git config --global user.email "atul@example.com"
git config --global --list
```

👉 Sets your identity for commits.

---

## 📂 2. Repository Initialization

```bash
git init
```

👉 Initializes a new Git repository.

```bash
git clone https://github.com/user/repo.git
```

👉 Copies a remote repository to local machine.

---

## 📄 3. File Status & Tracking

```bash
git status
```

👉 Shows modified, staged, and untracked files.

```bash
git add file.txt
git add .
```

👉 Stages one file or all changes.

---

## 💾 4. Commit Changes

```bash
git commit -m "Initial commit"
```

👉 Saves staged changes with a message.

```bash
git commit -am "Quick commit"
```

👉 Add + commit **only tracked files**.

---

## 🕵️ 5. View History & Logs

```bash
git log
git log --oneline
git log --graph --all
```

👉 Shows commit history (useful for debugging).

---

## 🌿 6. Branching (Very Important)

```bash
git branch
git branch dev
git checkout dev
```

👉 Create & switch branches.

```bash
git checkout -b feature/login
```

👉 Create + switch in one command.

---

## 🔀 7. Merge & Rebase

### Merge

```bash
git checkout main
git merge dev
```

👉 Combines branch history.

### Rebase

```bash
git checkout dev
git rebase main
```

👉 Rewrites history (clean linear commits).

---

## 🌐 8. Remote Repository Commands

```bash
git remote -v
git remote add origin https://github.com/user/repo.git
```

👉 Manage remote connections.

```bash
git push origin main
git pull origin main
```

👉 Upload / Download changes.

---

## ⚠️ 9. Undo & Fix Mistakes

```bash
git restore file.txt
```

👉 Discard file changes.

```bash
git reset --soft HEAD~1
git reset --hard HEAD~1
```

👉 Undo commits (soft keeps changes, hard deletes).

```bash
git revert <commit-id>
```

👉 Safely undo a commit (recommended for prod).

---

## 🧳 10. Stash (Temporary Save)

```bash
git stash
git stash list
git stash apply
```

👉 Temporarily save unfinished work.

---

## 🔍 11. Difference & Comparison

```bash
git diff
git diff HEAD
git diff branch1 branch2
```

👉 Compare file and branch changes.

---

## 🏷️ 12. Tags (Releases)

```bash
git tag v1.0
git tag
git push origin v1.0
```

👉 Mark production releases.

---

## 🔐 13. Ignore Files (.gitignore)

```gitignore
node_modules/
.env
*.log
```

👉 Prevent sensitive/unwanted files from tracking.

---

## 🚀 14. Common DevOps Scenarios

### CI/CD Checkout

```bash
git clone repo
git checkout main
```

### Fix Last Commit Message

```bash
git commit --amend -m "Updated message"
```

### Delete Branch

```bash
git branch -d dev
git push origin --delete dev
```

---

## 🧠 Interview Must-Remember Commands

| Use Case     | Command                   |
| ------------ | ------------------------- |
| Check status | `git status`              |
| Stage files  | `git add .`               |
| Commit       | `git commit -m`           |
| Branch       | `git checkout -b`         |
| Merge        | `git merge`               |
| Rebase       | `git rebase`              |
| Undo         | `git reset`, `git revert` |
| Remote       | `git pull`, `git push`    |
| Temp save    | `git stash`               |

---

## ✅ Pro Tip for DevOps Engineers

* **Use rebase for feature branches**
* **Use merge for main/master**
* **Never force-push on production branches**
* **Tag releases**
* **Keep commits small & meaningful**

---
