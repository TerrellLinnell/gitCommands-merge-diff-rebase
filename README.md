# Git Workshop on Diff, Merge, and Rebase

### Step 1: Create branches, show diffs and merge

* Create a new git repo, Add README.md and index.html file (default ato html snippet).
* Add, commit and push these changes to gitHub.
* run `git log` to see the new commit in the history. run `git status` and `git diff` to see that there are not changes in your working dir.
* Create a topic branch `git branch newFeature` then `git checkout newFeature`. This creates a new branch and makes it your working branch.
* `git checkout -b newFeature` is a shortcut equivalent to running both commands
* run `git branch` to see the branches. The `*` is the active branch.
* run `git log --all --graph --decorate --oneline`. (make an alias to this command - mine is gitg) this shows all commits in all branches and labels the branches and HEAD.
* create `css/style.css` and add content then run ``
*
*
