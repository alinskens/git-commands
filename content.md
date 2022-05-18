## What is the difference between push, pull, and fetch?
Consider how the following `git` commands synchronize your local repository with a remote repository:
* `git push` sends changes from your local branch to a remote repository.
* `git fetch` collects changes from a remote repository into your tracking branch.
* `git pull` collects changes from a remote repository into your local branch and merges them into a local branch.

`git push` takes your current local branch, and checks to see whether or not it connects to a remote repository. If so, your changes upload to the remote repository. Run this command to upload your local-branch commits to a remote repository. This fails if the remote branch diverges from your local branch: if not all the commits in the remote branch exist in your local branch. When this happens, synchronize your local branch with the remote branch with git pull or git fetch and git merge.

`git fetch` again takes your current local branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. Run this command to review any changes in remote tracking branches before deciding if you want to merge them into your local branch. It does not change your local branch. To do that, you need to run `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".

While `git push` and `git pull` sound equivalent, one command performs a single action while the other performs two. `git pull` simply does a `git fetch` followed immediately by `git merge`. Use this command to update your current local branch with all new commits from the corresponding remote branch. Run git fetch followed by git merge separately if you want to better understand the changes before you merge them into your local branch.