# Day 12 — Git & GitHub: Practical Workflow

## 1. Objective

The objective of this task is to understand Git and GitHub and practice the complete Git workflow using VS Code and GitHub.

By completing this task, I learned how to:

- Track code changes using Git.
- Create and switch branches.
- Stage and commit changes.
- Push a branch to GitHub.
- Create and merge a Pull Request.
- Update the local `main` branch.
- Verify changes using Git commands.

## 2. Basic Concepts

### Git
Git is a version control system that tracks changes in files and helps developers return to earlier versions.

### GitHub
GitHub is an online platform used to store Git repositories and collaborate with other developers.

### Repository
A repository is a project folder tracked by Git. It contains project files and their version history.

### Branch
A branch is a separate line of development that allows changes to be made without directly modifying the `main` branch.

### Commit
A commit is a saved checkpoint of changes in the local Git repository.

### Push
Push uploads local commits to a remote repository, such as GitHub.

### Pull
Pull downloads and integrates changes from a remote branch into the current local branch.

### Pull Request (PR)
A Pull Request proposes changes from one branch to another for review.

### Merge
Merge combines changes from one branch into another branch.

## 3. Project File: `hello.py`

The Python file contains the following code:

```python
print("Hello Git")
print("Learning version control")
print("I am learning Git step by step")
print("Practicing branches and pull requests")
```

### Expected Output

```text
Hello Git
Learning version control
I am learning Git step by step
Practicing branches and pull requests
```

The `print()` function displays each message in the terminal. Python executes these statements from top to bottom.

## 4. Complete Git Workflow

The workflow followed in this task is:

1. Check the repository status.
2. Check the available branches.
3. Create or switch to a feature branch.
4. Edit and save `hello.py`.
5. Run the Python file.
6. Review changes using `git diff`.
7. Stage changes using `git add`.
8. Save a checkpoint using `git commit`.
9. Upload the feature branch using `git push`.
10. Create and merge a Pull Request on GitHub.
11. Switch to the local `main` branch.
12. Pull the latest changes and verify the result.

## 5. Step-by-Step Practical

### Step 1: Check Git Status

```bash
git status
```

**Purpose:** Shows the current branch and whether files have changes that need to be staged or committed.

Example:

```text
On branch main
nothing to commit, working tree clean
```

This means the current branch is `main` and there are no uncommitted changes.

### Step 2: Check Branches

```bash
git branch
```

**Purpose:** Lists local branches. The `*` symbol identifies the current branch.

Example:

```text
* main
  feature/hello-message
```

### Step 3: Create or Switch to a Feature Branch

To create a new branch and switch to it:

```bash
git switch -c feature/hello-message
```

Use this only if the branch does not already exist.

If the branch already exists:

```bash
git switch feature/hello-message
```

**Purpose:** Allows feature work to be performed separately from `main`.

### Step 4: Run the Python File

Save `hello.py` in VS Code, then run:

```bash
python hello.py
```

If `python` is not recognized on Windows, try:

```powershell
py hello.py
```

**Purpose:** Executes the Python program. This does not create a Git commit or upload anything to GitHub.

### Step 5: Review Changes

```bash
git status
git diff
```

- `git status` checks the repository state.
- `git diff` shows changes in tracked files that have not yet been staged.
- A `+` indicates added lines, while a `-` indicates removed lines.

If there are no changes compared with the last commit, `git diff` may show no output.

### Step 6: Stage the File

```bash
git add hello.py
```

**Purpose:** Stages changes in `hello.py` for the next commit.

Check the result:

```bash
git status
```

The file may appear under `Changes to be committed`.

Note: `git add` does not upload the file to GitHub.

### Step 7: Commit the Changes

```bash
git commit -m "Add feature branch message"
```

**Purpose:** Creates a checkpoint of the staged changes in the local repository.

The `-m` option specifies a message describing the commit.

If Git reports that there is nothing to commit, check the status before continuing.

### Step 8: Push the Feature Branch

```bash
git push -u origin feature/hello-message
```

- `git push`: Uploads commits.
- `-u`: Sets the upstream branch for future pushes.
- `origin`: The configured remote repository name.
- `feature/hello-message`: The branch being uploaded.

This requires a configured remote repository and valid GitHub authentication.

### Step 9: Create a Pull Request

1. Open the repository on GitHub.
2. Open the Pull Requests tab or select **Compare & pull request**.
3. Set **Base** to `main`.
4. Set **Compare** to `feature/hello-message`.
5. Review the proposed changes.
6. Use the title `Add feature branch message`.
7. Click **Create pull request**.
8. Review the changes and merge the PR if the repository allows it.

**Purpose:** A Pull Request allows changes to be reviewed before they are merged into the target branch.

### Step 10: Update the Local Main Branch

After the Pull Request has been merged on GitHub:

```bash
git switch main
git pull origin main
```

- `git switch main` changes the current local branch to `main`.
- `git pull origin main` fetches and integrates updates from the remote `main` branch.

If there are uncommitted changes or Git reports a conflict, investigate the message before continuing. Do not force changes.

## 6. Verify the Result

Run these commands individually:

```bash
python hello.py
git log --oneline --graph --all
git status
```

Expected checks:

- The Python file prints the four messages.
- The Git log displays commit history.
- The working tree is clean if all changes have been committed and the local branch is up to date.

Example final status:

```text
On branch main
nothing to commit, working tree clean
```

## 7. Important Git Commands

| Command | Purpose |
|---|---|
| `git status` | Check the repository status |
| `git branch` | List local branches |
| `git switch main` | Switch to the main branch |
| `git switch -c branch-name` | Create and switch to a branch |
| `git diff` | View unstaged changes in tracked files |
| `git add hello.py` | Stage changes to a file |
| `git commit -m "message"` | Save a checkpoint |
| `git push` | Upload commits |
| `git pull` | Download and integrate remote changes |
| `git log --oneline` | View compact commit history |

## 8. Common Problems and Precautions

- **`python` is not recognized:** Try `py hello.py`.
- **Branch already exists:** Use `git switch feature/hello-message`.
- **Nothing to commit:** Check `git status` and confirm the file was saved.
- **Remote or authentication error:** Check the configured remote and GitHub authentication.
- **Push rejected:** Read the error and reconcile remote changes safely. Do not force-push without understanding the situation.
- **Uncommitted changes while switching branches:** Save or safely handle the changes before switching.

## 9. Conclusion

In this task, I practiced the Git and GitHub workflow, including branch management, staging, commits, pushing changes, Pull Requests, merging, and updating the local `main` branch.

This exercise helped me understand how version control supports collaboration and safe code management.
