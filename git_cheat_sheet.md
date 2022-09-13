### Git Commands

* `git remote show origin` - check which repo you are pointing at
* `git add <filename>` - add a file to your commit - https://git-scm.com/docs/git-add
* `git log --name-status` - see last commit items
* `git commit -m <commit_message>` - stage commit
* `git push` - push commit
* `git checkout <filename>` - revert to upstream
* `git checkout -b my_branch_name` - create and checkout on branch
* `git branch` check which branch your on
* `git branch <branch_name>` - create a branch
* `git push -u origin my_branch_name` - tell github that you have made a new branch - otherwise it will fail when attempting to push
* `git push origin --delete remoteBranchName` - delete branch remotely (and locally)
* `git reset --hard origin/branch_to_overwrite` - hard reset if something breaks
* `git reset --hard && git pull` - reset and pull
* `git pull --set-upstream` - pull the live version down


* git checkout <hash_key^ <folder_path>/>file> - restore a previously deleted file that has been commited and pushed to Github 


### Git Stats

* `git shortlog -s -n` -- see total commits broken down by users
* `brew install git-extras` -> `git summary --line` -- see total line changes in git history

### Git config and SSH

[More on git config here](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

[SSH key platform notes all here](https://user-guidance.services.alpha.mojanalytics.xyz/github.html#jupyterlab)


<br>
<hr>

## Working with github

#### Cloning from a specific branch
`git clone -b <branch-to-clone> <ssh-key> clone-name`

Or in a working example:
`git clone -b write_df_to_s3_fix git@github.com:moj-analytical-services/s3tools.git alt-ringfence`
<br><br>
#### Branches
`git push origin --delete {the_remote_branch} # Delete branch locally + remotely`
git checkout
<br><br>
#### Syncing up repos (specifically to allow creation of a test repo for an app)
https://www.opentechguides.com/how-to/article/git/177/git-sync-repos.html

Working example of the above:

To get everything setup, initially ensure you cd into your home directory. You can do this by using `cd ..`. If you go too far up the folder branches, you can path back down using `cd my_folder_i_want_to_access`.

If done correctly, your cmd session should end up looking like this: <br>
![Screenshot 2021-08-09 at 14 49 34](https://user-images.githubusercontent.com/45356472/128717070-4cba4063-1e12-488e-aaf0-bde7629220e9.png)

From there, enter the following code into terminal, line by line:
```
git clone --mirror git@github.com:moj-analytical-services/criminal-scenario-tool.git
cd criminal-scenario-tool.git
git remote add --mirror=fetch secondary git@github.com:moj-analytical-services/criminal-scenario-tool-testing.git
git fetch origin
git push secondary --all
```
Once done, ensure your directory stays within `criminal-scenario-tool-testing.git` (or equivalent).

Any updates from the master repo can subsequently be captured running the following lines:
```
git fetch origin
git push secondary --all
```

Please note, any changes to your secondary repo will lead to errors when attempting to run the above lines.
<br><br>
#### Resetting to a previous commit
More here - https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit

**Start by resetting to your previous commit**
`git reset --hard <commitId> && git clean -f
**Then update the github version**
```
git push origin/master --force
# or
# git push --force
```

<br>
<hr>
