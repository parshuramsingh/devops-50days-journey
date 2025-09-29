# 🚀 Day 3 – Git Branching & Workflow

## 🎯 Learning Goals

* Understand why branches are used in Git.
* Learn how to create, switch, merge, and delete branches.
* Practice pushing a branch to GitHub and merging it back.
* Explore merge strategies (Fast-forward vs Rebase).
* Follow professional Git workflow (feature branches + cleanup).

---

## 📖 Concepts in Detail

### 🔹 What is a Branch?

A branch in Git is a lightweight movable pointer to a commit.

* `main` (or `master`) → the production-ready branch.
* Feature branches → used for new features, bug fixes, or experiments.

This allows multiple developers to work **in parallel** without interfering with each other.

---

### 🔹 Creating and Switching Branches

```bash
git checkout -b feature/day3-branch
```

* Creates a new branch `feature/day3-branch`.
* Switches to it immediately.

---

### 🔹 Adding Work to the Branch

```bash
echo "Learning Git Branching" >> Day-03-Git-Branching.md
git add Day-03-Git-Branching.md
git commit -m "Start Day 3: Git Branching"
```

Now the branch has new commits isolated from `main`.

---

### 🔹 Pushing Branch to GitHub

```bash
git push -u origin feature/day3-branch
```

* Publishes branch to GitHub.
* `-u` sets upstream tracking so future pushes/pulls are easier.

---

### 🔹 Merging Back to Main

```bash
git checkout main
git merge feature/day3-branch
```

If no conflict exists, Git performs a **fast-forward merge** (main simply moves its pointer forward).

---

### 🔹 Deleting Branches

After merging, delete the feature branch to keep repo clean:

```bash
git branch -d feature/day3-branch        # local delete
git push origin --delete feature/day3-branch   # remote delete
```

---

### 🔹 Rebase (Optional Advanced)

Instead of merging, we can rebase a feature branch onto `main`:

```bash
git checkout feature/day3-branch
git rebase main
```

This rewrites commit history to keep it **linear**.
⚠️ Use with care in team projects (don’t rebase shared branches).

---

## 🛠 Hands-On Exercise

1. Create a new branch → Add a file → Commit → Push.
2. Merge into `main`.
3. Delete the feature branch.
4. Try the same with **rebase** before merging.

---

## ✅ Key Takeaways

* Branches allow isolated, parallel development.
* Merges integrate work back into main.
* Rebasing rewrites history → cleaner logs.
* Always delete merged branches for clarity.

---

## 📌 Real-World Usage

* Teams create **feature branches** per ticket/feature.
* Pull Requests (PRs) review the code before merging.
* Branch naming convention:

  * `feature/...` → New features
  * `bugfix/...` → Bug fixes
  * `hotfix/...` → Urgent fixes

---

## 🔗 Resources

* [Git Branching Basics](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* [Atlassian Git Branching Guide](https://www.atlassian.com/git/tutorials/using-branches)

---
