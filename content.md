## What is the difference between push, pull, and fetch?
Consider how the following `git` commands synchronize your local repository with a remote repository:
* `git push` sends changes from your local branch to a remote repository.
* `git fetch` collects changes from a remote repository into your tracking branch.
* `git pull` collects changes from a remote repository into your local branch and merges them into a local branch.

`git push` uploads your local-branch changes to a remote repository. If you first want to match the commits in your local branch with the remote repository, run a single `git pull` or a sequence of `git fetch` and `git merge`.

`git fetch` checks your current local branch against changes in a remote branch, and pulls them into the tracking branch. Run this command to review any changes in remote tracking branches before deciding if you want to merge them into your local branch. Run `git merge origin/master` (for the "master" branch) to combine those changes into your local branch.

While `git push` and `git pull` sound equivalent, one command performs a single action while the other performs two. `git pull` simply does a `git fetch` followed immediately by `git merge`. Run this command to fetch updates from a remote repository and merge them into your local branch.