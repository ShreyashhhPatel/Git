# Git & GitHub Essentials for Rails Projects

Git & GitHub Essentials for Rails Projects

1. Initialize a Git Repository
   git init
   - Creates a new .git folder in your project directory.

2. Add Files to Staging
   git add .
   - Stages all files for the next commit.

3. Commit Changes
   git commit -m "Your message"
   - Saves your staged changes to history with a message.

4. Rename Branch to Main
   git branch -M main
   - Renames the current branch to 'main'.

5. Connect to a GitHub Repo
   git remote add origin https://github.com/<username>/<repo>.git
   - Links your local repo to a GitHub repo.

   git remote -v
   - Shows connected remotes.

   git remote set-url origin https://github.com/<username>/<repo>.git
   - Updates the remote link.

6. Push Code to GitHub
   git push -u origin main
   - Push local commits to GitHub.

   git push -u origin main --force
   - Force push (overwrites GitHub).

7. Pull Changes from GitHub
   git pull origin main
   - Downloads changes from GitHub.

   git pull origin main --allow-unrelated-histories
   - Allows combining two different histories.

8. Remove and Reset Git
   rm -rf .git
   git init
   - Removes all Git history and starts fresh.

9. Fix Submodule Issue (for folders like store/)
   git rm --cached store
   git add store
   git commit -m "Re-add store as normal folder"
   - Removes submodule reference, commits real files.

10. Empty a GitHub Repo (but keep it alive)
    git checkout --orphan wipe
    git commit --allow-empty -m "Empty repo"
    git push origin wipe:main --force
    - Repo becomes empty but still exists.

11. Clone a Repo
    git clone https://github.com/<username>/<repo>.git
    - Download a repo from GitHub.

12. Rails .gitignore (example)
    /log/*
    /tmp/*
    /storage/*
    /node_modules
    /config/master.key
    /db/*.sqlite3
