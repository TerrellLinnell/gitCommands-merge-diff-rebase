# Git Workshop on Diff, Merge, and Rebase

### Step 1: Create branches, show diffs and merge

* Create a new git repo, Add README.md and index.html file (default ato html snippet).
* Add, commit and push these changes to gitHub.
* run `git log` to see the new commit in the history. run `git status` and `git diff` to see that there are not changes in your working dir.
* Create a topic branch `git branch newFeature` then `git checkout newFeature`. This creates a new branch and makes it your working branch.
* `git checkout -b newFeature` is a shortcut equivalent to running both commands
* run `git branch` to see the branches. The `*` is the active branch.
* run `git log --all --graph --decorate --oneline`. (make an alias to this command - mine is gitg) this shows all commits in all branches and labels the branches and HEAD.
* create `css/style.css` and add content then run `git diff`. Notice that style.css is not in the diff. Only tracked files are in the diff.
* run `git add -A` and `git diff`. notice that there is still no output.  Run `get diff --staged`  this shows staged changes.
* add and commit changes
* run `gitg` (or what you named the alias). Output should look like this:

```
247c577 (HEAD -> NewFeature) Readme updates and added css/style.css
d9a638e (master) updated to Readme
26988b1 (origin/master) Initial commit of README and index on brnch master
```
* run `git checkout master` to change back to the master branch.  run `git merge new_feature` to bring the changes in from the new_feature branch.
* `gitg` still shows a linear series of changes.
* edit the index.html file in the master branch; switch to the new_feature branch; edit the same lines in the new_feature branch.
* commit these changes to the new_feature branch.
* `gitg` now shows diverging branches.  Note that the HEAD is the most recent commit on new_feature.
* `git checkout master`.  Now the HEAD is now the most recent commit on master.


### Step 2:
