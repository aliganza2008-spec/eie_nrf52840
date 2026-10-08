git commit
Creates a snapshot of the changes currently in the staging area and saves it in the repository’s history. Unstaged changes are not included.
git commit — Opens the configured editor to write a commit message.
git commit -m "message" — Creates the commit with a message entered directly in the command.

git branch
A branch is a movable pointer to a commit that allows you to develop changes separately.
git branch — Lists local branches. The current branch has an asterisk (*).
git branch <branch-name> — Creates a new branch without switching to it.
git branch -d <branch-name> — Deletes a merged branch.
git branch -f <branch-name> <commit> — Moves a branch pointer to another commit.

git checkout
Switches to another branch or accesses a particular commit.
git checkout <branch-name> — Switches to an existing branch.
git checkout -b <branch-name> — Creates a new branch and switches to it.
git checkout <commit-hash> — Checks out a commit in detached HEAD mode.
git switch <branch-name> — Newer command for switching branches.
git switch -c <branch-name> — Creates a new branch and switches to it.

git pull
Downloads changes from a remote repository and integrates them into the current local branch.
git pull — Pulls from the current branch’s configured remote.
git pull <remote> <branch> — Pulls a particular remote branch.
git pull --no-rebase — Fetches and merges remote changes.
git pull --rebase — Fetches and rebases local commits onto the remote changes.

git push
Uploads committed changes from a local branch to a remote repository.
git push — Pushes to the configured remote branch.
git push <remote> <branch> — Pushes a particular branch to a remote repository.
Example: git push origin main
Git push sends only committed changes. A push may be rejected if the remote has commits that your local branch does not have.

git merge
Combines another branch’s changes into the branch currently checked out.
git merge <branch-name> — Merges the named branch into the current branch.
Example: Switch to main using git switch main, then run git merge feature to bring feature into main.
Compatible changes are combined automatically. Incompatible changes may cause a merge conflict. Merging does not delete the source branch.

git rebase
Replays the current branch’s commits on top of another branch or commit, creating replacement commits with new hashes.
git rebase <branch-name> — Rebases the current branch onto the named branch.
git rebase -i HEAD~3 — Interactively edits the last three commits.
git rebase --continue — Continues after resolving a conflict or editing a commit.
git rebase --abort — Cancels the rebase.
Avoid rebasing commits that other people are already using because rebase rewrites history.

git fetch
Downloads commits and branch information without changing the current local branch or working files. It updates remote-tracking branches such as origin/main.
git fetch — Fetches from the configured remote.
git fetch <remote> — Fetches from a particular remote.
git fetch <remote> <branch> — Fetches a particular remote branch.
Example: git fetch upstream main
Unlike git pull, git fetch does not automatically merge or rebase the downloaded changes.