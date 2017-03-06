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


### Step 2:### Step 2: Merging with Rebase

* Create a new branch dev from the HEAD (master branch).
  * It is common to have long running branches for development
* add a new file `js/main.js` in the dev branch. (Make a commit).
* Create a branch off dev called new_function.
* create a new function in main.js in new_function branch. (make a commit).
* go back to dev and add a function there as well. (make a commit).
* checkout the new_function branch.
* `git rebase dev`
  * If merge conflicts, fix manually then `git add -A` and `git rebase --continue`
* These commands replay the new_function changes on dev.  The pointer for the dev branch is still behind the latest commit.
* run `git checkout dev && git merge new_function` to fast-forward the dev pointer.

Output of `gitg` now should look like this:

```
* 803106c (HEAD -> dev, origin/new_function, origin/dev, new_function) Added a new function in new_function branch
* 388eb7c new function on dev branch
* 36d500b added main.js to dev branch
*   63a4f2d (origin/master, master) fixed the merge conflict
|\  
| * e6e89fc changes to index.html in new_feature branch
* | 45d6a98 readme update
* | 47d5426 edits to index.html
|/  
* 870cc7a updated readme
* 247c577 Readme updates and added css/style.css
* d9a638e update to readme
* 26988b1 Initial commit of README and index on branch master
```

Notice that the rebase merged the changes from the new_function branch, but the commit history looks linear.
