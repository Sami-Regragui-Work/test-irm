# Git Basics — Teaching Checklist

## 1. Start from GitHub
- [ ] Create a new repo on GitHub
- [ ] Walk through GitHub's own "…or create a new repository on the command line" instructions
- [ ] Explain why this is a good anchor: even if you forget everything else, GitHub's own steps tell you how to proceed
- [ ] `git clone <url>` — cloning an existing repo instead of starting fresh

## 2. Install Git
- [ ] Install Git (check with `git --version`)
- [ ] `git config --global user.name "..."`
- [ ] `git config --global user.email "..."`

## 3. Basic Workflow
- [ ] `git status` — check current state
- [ ] `git add <file>` / `git add .` — stage changes
- [ ] `git commit -m "message"` — save a snapshot
- [ ] `git log` / `git log --oneline --graph` — view history
- [ ] `git diff` — see unstaged changes
- [ ] `.gitignore` — what it is, why you need one early

## 4. Remotes
- [ ] `git remote add origin <url>`
- [ ] `git remote -v` — verify remotes
- [ ] `git fetch` vs `git pull` — download vs download+merge

## 5. Stashing
- [ ] `git stash` — save uncommitted work temporarily
- [ ] `git stash pop` — reapply and remove from stash
- [ ] `git stash apply` — reapply but keep in stash (mention the difference from pop)
- [ ] `git stash list` — see all stashes

## 6. Branching
- [ ] `git branch` — list/create branches
- [ ] `git switch <branch>` — modern way to change branches
- [ ] `git checkout <branch>` — older/multi-purpose command (also restores files, detached HEAD)
- [ ] Explain why `switch`/`restore` were split out of `checkout` (less confusing)

## 7. Removing / Untracking Files
- [ ] `git rm --cached <file>` — untrack a file without deleting it locally
- [ ] Pair this with adding it to `.gitignore` afterward

## 8. Rewriting / Pushing
- [ ] `git push` — normal push
- [ ] `git push --force` — overwrite remote history (explain the danger)
- [ ] `git push --force-with-lease` — safer force push (fails if remote has new commits you don't have)
- [ ] `git commit --amend` — edit the last commit's message/contents
- [ ] `git commit --amend --no-edit` — amend without changing the message
- [ ] `git commit --allow-empty` — create a commit with no changes (useful for triggering CI, testing)

## 9. Resetting / Cleaning
- [ ] `git reset --soft <commit>` — move HEAD, keep changes staged
- [ ] `git reset --mixed <commit>` — move HEAD, keep changes unstaged (default)
- [ ] `git reset --hard <commit>` — move HEAD, discard all changes
- [ ] `git clean -fd` — remove untracked files/directories
- [ ] `git reflog` — the safety net if you reset/clean too aggressively

## 10. Conflicts & Rebase
- [ ] How a merge conflict happens
- [ ] Reading conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
- [ ] Resolving manually, then `git add` + `git commit`
- [ ] `git merge --abort` — bail out
- [ ] `git rebase <branch>` — replay commits on top of another branch
- [ ] `git rebase -i <commit>` — interactive rebase (squash, reorder, edit commits)
- [ ] `git rebase --abort` / `--continue`
- [ ] Merge vs rebase — when to use which

## 11. Practice Exercise Ideas
- [ ] Create a repo on GitHub, clone it, make commits, push
- [ ] Stash changes mid-task, switch branches, pop the stash back
- [ ] Create a branch, cause a merge conflict on purpose, resolve it
- [ ] Amend a commit, then force-push safely with `--force-with-lease`
- [ ] Reset hard by accident, recover the "lost" commit using `git reflog`
- [ ] Rebase a feature branch onto main and squash commits interactively