# Git & GitHub Essentials for Rails Projects

## 1. Initialize a Git Repository
```bash
git init
```
- Creates a new `.git` folder in your project directory.  
- This makes Git start tracking changes.  
- By default, it creates a branch called `master` (you can rename it to `main`).  

---

## 2. Add Files to Staging
```bash
git add .
```
- Stages all files for the next commit.  
- `.` means “everything in this folder.”  

---

## 3. Commit Changes
```bash
git commit -m "Your message"
```
- Saves your staged changes to history with a message.  
- Always write a clear commit message.  

---

## 4. Rename Branch to Main
```bash
git branch -M main
```
- Renames the current branch to `main`.  
- Standard naming convention on GitHub.  

---

## 5. Connect to a GitHub Repo
```bash
git remote add origin https://github.com/<username>/<repo>.git
```
- Links your local repo to a remote GitHub repo.  

Check remotes:
```bash
git remote -v
```

Change remote if needed:
```bash
git remote set-url origin https://github.com/<username>/<repo>.git
```

---

## 6. Push Code to GitHub
```bash
git push -u origin main
```
- Sends commits from your local `main` branch to GitHub.  
- `-u` sets the upstream, so later you can just run `git push`.  

Force push (⚠️ overwrites GitHub with your local code):
```bash
git push -u origin main --force
```

---

## 7. Pull Changes from GitHub
```bash
git pull origin main
```
- Downloads changes from GitHub into your local repo.  

If history is different, allow unrelated histories:
```bash
git pull origin main --allow-unrelated-histories
```

---

## 8. Remove and Reset Git
```bash
rm -rf .git
git init
```
- Completely removes git history and re-initializes tracking.  
- Use this to start fresh if your repo setup breaks.  

---

## 9. Fix Submodule Issue (like your `store/` folder)
When Git treats a folder as a submodule:
```bash
git rm --cached store
git add store
git commit -m "Re-add store as normal folder"
```
- This removes the submodule reference so Git tracks the actual contents of `store/`.  

---

## 10. Empty a GitHub Repo (but keep it alive)
Overwrite `main` with an empty commit:
```bash
git checkout --orphan wipe
git commit --allow-empty -m "Empty repo"
git push origin wipe:main --force
```
- Repo stays but has no files/history.  

---

## 11. Clone a Repo
```bash
git clone https://github.com/<username>/<repo>.git
```
- Downloads a full copy of a repo from GitHub.  

---

## 12. .gitignore for Rails
`.gitignore` tells Git which files/folders to skip:  

```gitignore
/log/*
/tmp/*
/storage/*
/node_modules
/config/master.key
/db/*.sqlite3
```

---

✅ With these commands, you can:  
- Initialize Git  
- Connect to GitHub  
- Push & pull safely  
- Reset history when needed  
- Avoid submodule mistakes  
- Empty a repo  
- Keep your Rails repo clean  
