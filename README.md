# Advanced Git Exercises

This repo contains step-by-step solutions to advanced Git exercises including:

- Interactive rebase
- Commit squashing
- Commit splitting using `git reset`
- Cleaning commit history using `rebase --root`

---

## ✅ Step-by-Step Git Process

---

### 🟢 Step 1: Cloning the Repo and Making Initial Commits

```bash
# Cloned the GitHub repo
git clone https://github.com/Celxine/advanced-git-exercises.git
cd advanced-git-exercises

# Created test files and made first two commits
touch test1.md test2.md
git add .
git commit -m "chore: Create initial file"

touch test3.md test4.md
git add .
git commit -m "chore: Create third and fourth files"


```
### 🟢 Step 2: Squashing Commits from Root

```bash

# Used rebase from root to squash first two commits
git rebase -i --root

# In the editor:
# - Change second commit from 'pick' to 'squash'
# - Combine commit messages as:
#   chore: Create initial file and second file

```

### 🟢 Step 3: Splitting a Commit Using git reset
```bash
# Reset back one commit to unstage files
git reset --soft HEAD~1

# Add and commit third file only
git add test3.md
git commit -m "chore: Create third file"

# Add and commit fourth file
git add test4.md
git commit -m "chore: Create fourth file"
```

git log --oneline
# Confirmed: commits are clean and separated correctly

# Start interactive rebase on the last two commits
git rebase -i HEAD~2

# In the editor, change the second commit's action from pick to squash or s
# Save and exit the editor, when prompted edit the combined commit message to Create third and fourth file


# Verify the new combined commit
git log --oneline

# You should see one commit for both files with the message: "Create third and fourth file"
```

### 🟢 Step 7: Reordering commits
```bash

```