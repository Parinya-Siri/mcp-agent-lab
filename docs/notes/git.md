# Git undo cheat sheet

Rule: only rewrite history that you haven't pushed. For pushed commits, use `revert`.

| Situation | Command | What it does | Safe after push? |
|---|---|---|---|
| Discard an unstaged edit | `git restore <file>` | Puts the file back to the last commit's version. **The edit is gone for good.** | n/a (local only) |
| Unstage a file | `git restore --staged <file>` | Removes the file from staging; your edit stays in the file | n/a (local only) |
| Fix the last commit | `git commit --amend -m "msg"` | Replaces the last commit (message and anything staged); gives it a new SHA | ❌ No (needs a force push) |
| Un-commit, keep the work | `git reset --soft HEAD~1` | Removes the last commit; its changes stay staged | ❌ No |
| Throw away commits and edits | `git reset --hard <sha>` | Moves the branch to `<sha>` and **deletes all uncommitted changes** | ❌ No |
| Undo a pushed commit | `git revert <sha>` | Adds a new commit that does the opposite of `<sha>`; history is kept | ✅ Yes |
| Park unfinished work | `git stash` / `git stash pop` | Saves uncommitted changes aside; `pop` brings them back | n/a (local only) |
| Preview untracked files to delete | `git clean -n` | Lists untracked files that `-f` would delete (dry run) | n/a (local only) |
| Delete untracked files | `git clean -f` | Deletes untracked files. **Can't be undone.** | n/a (local only) |
| Find a "lost" commit | `git reflog` | Shows everywhere HEAD has been, so you can recover commits after reset or rebase | n/a (local only) |