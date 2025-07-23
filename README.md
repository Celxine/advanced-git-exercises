# Advanced Git Exercises

This repo contains step-by-step solutions to advanced Git exercises including:

- Interactive rebase
- Commit squashing
- Commit splitting using `git reset`
- Cleaning commit history using `rebase --root`

---

## ✅ Step-by-Step Git Process

### 1. Setup and Initial Commits

```bash
# Cloned the GitHub repo
git clone <https://github.com/Celxine/advanced-git-exercises.git>
cd advanced-git-exercises

# Created test files
touch test1.md test2.md
git add .
git commit -m "chore: Create initial file"

touch test3.md test4.md
git add .
git commit -m "chore: Create third and fourth files"

git rebase -i --root
# Changed second commit from 'pick' to 'squash'
# Combined commit messages:
#   chore: Create initial file and second file

# Reset back one commit to unstage files
git reset --soft HEAD~1

# Add and commit third file only
git add test3.md
git commit -m "chore: Create third file"

# Add and commit fourth file
git add test4.md
git commit -m "chore: Create fourth file"

git log --oneline
# Confirmed: commits are clean and separated correctly
```
