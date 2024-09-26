# Git Cheat Sheet

This Git cheat sheet is a quick reference guide to essential Git commands, complete with descriptions and examples for each command. It covers a range of topics including initializing a repository, managing branches, working with remote repositories, stashing changes, undoing changes, and viewing commit history. Whether you're a beginner or an experienced developer, this guide provides practical examples to help you navigate and use Git effectively for version control in your projects.

### Git Basics

#### 1. **Initialize a Repository**

- **Command:** `git init`
- **Example:**

  ```bash
  git init
  ```

- **Description:** Initializes a new Git repository in the current directory.

#### 2. **Clone a Repository**

- **Command:** `git clone <repo_url>`
- **Example:**

  ```bash
  git clone https://github.com/user/repo.git
  ```

- **Description:** Creates a local copy of a remote repository.

#### 3. **Check Status**

- **Command:** `git status`
- **Example:**

  ```bash
  git status
  ```

- **Description:** Shows the current status of the working directory and the staging area.

#### 4. **Add Files**

- **Command:** `git add <file>`
- **Example:**

  ```bash
  git add filename.txt
  ```

- **Description:** Stages changes for the next commit.

#### 5. **Commit Changes**

- **Command:** `git commit -m "message"`
- **Example:**

  ```bash
  git commit -m "Initial commit"
  ```

- **Description:** Records changes to the repository with a message.

#### 6. **Push Changes**

- **Command:** `git push origin <branch>`
- **Example:**

  ```bash
  git push origin master
  ```

- **Description:** Uploads local branch commits to the remote repository.

#### 7. **Pull Changes**

- **Command:** `git pull origin <branch>`
- **Example:**

  ```bash
  git pull origin master
  ```

- **Description:** Fetches and integrates changes from the remote repository.

---

### Branching

#### 1. **Create a New Branch**

- **Command:** `git branch <branch_name>`
- **Example:**

  ```bash
  git branch feature-branch
  ```

- **Description:** Creates a new branch.

#### 2. **Switch to a Branch**

- **Command:** `git checkout <branch_name>`
- **Example:**

  ```bash
  git checkout feature-branch
  ```

- **Description:** Switches to the specified branch.

#### 3. **Create and Switch to a New Branch**

- **Command:** `git checkout -b <branch_name>`
- **Example:**

  ```bash
  git checkout -b new-feature
  ```

- **Description:** Creates a new branch and switches to it.

#### 4. **Merge a Branch**

- **Command:** `git merge <branch_name>`
- **Example:**

  ```bash
  git merge feature-branch
  ```

- **Description:** Merges the specified branch into the current branch.

#### 5. **Delete a Branch**

- **Command:** `git branch -d <branch_name>`
- **Example:**

  ```bash
  git branch -d feature-branch
  ```

- **Description:** Deletes the specified branch.

---

### Remote Repositories

#### 1. **Add a Remote Repository**

- **Command:** `git remote add <name> <url>`
- **Example:**

  ```bash
  git remote add origin https://github.com/user/repo.git
  ```

- **Description:** Adds a new remote repository.

#### 2. **List Remote Repositories**

- **Command:** `git remote -v`
- **Example:**

  ```bash
  git remote -v
  ```

- **Description:** Lists the URLs of the remote repositories.

#### 3. **Remove a Remote Repository**

- **Command:** `git remote remove <name>`
- **Example:**

  ```bash
  git remote remove origin
  ```

- **Description:** Removes a remote repository.

---

### Stashing

#### 1. **Stash Changes**

- **Command:** `git stash`
- **Example:**

  ```bash
  git stash
  ```

- **Description:** Saves changes temporarily.

#### 2. **Apply Stashed Changes**

- **Command:** `git stash apply`
- **Example:**

  ```bash
  git stash apply
  ```

- **Description:** Applies the last stashed changes.

#### 3. **List Stashes**

- **Command:** `git stash list`
- **Example:**

  ```bash
  git stash list
  ```

- **Description:** Lists all stashed changes.

#### 4. **Pop Stashed Changes**

- **Command:** `git stash pop`
- **Example:**

  ```bash
  git stash pop
  ```

- **Description:** Applies and removes the last stashed changes.

---

### Undoing Changes

#### 1. **Undo Changes in Working Directory**

- **Command:** `git checkout -- <file>`
- **Example:**

  ```bash
  git checkout -- filename.txt
  ```

- **Description:** Discards changes in the working directory.

#### 2. **Unstage Changes**

- **Command:** `git reset <file>`
- **Example:**

  ```bash
  git reset filename.txt
  ```

- **Description:** Unstages changes without modifying the working directory.

#### 3. **Reset to a Previous Commit**

- **Command:** `git reset --hard <commit>`
- **Example:**

  ```bash
  git reset --hard HEAD~1
  ```

- **Description:** Resets the current branch to a specific commit, discarding all changes.

---

### Logs and History

#### 1. **View Commit History**

- **Command:** `git log`
- **Example:**

  ```bash
  git log
  ```

- **Description:** Displays the commit history.

#### 2. **Show Changes for a Specific Commit**

- **Command:** `git show <commit>`
- **Example:**

  ```bash
  git show abc123
  ```

- **Description:** Displays changes made in a specific commit.

#### 3. **Show Changes Between Commits**

- **Command:** `git diff <commit1> <commit2>`
- **Example:**

  ```bash
  git diff HEAD~1 HEAD
  ```

- **Description:** Shows differences between commits.
