# Some important tips

## Ways to undo committed changes
1. Using `git checkout <commit-hash>` for detaching the HEAD to a particular commit.  
	This creates detached HEAD and any commits during this stage are orphaned. Such commits are disposed by git's garbage collector over time. However, if we wish to keep these changes, we need to create a new branch not having all the future commits but only this new commit and commits before that.  
	Use `git checkout -b <branch-name> <orphan-commit-hash>`  
2. Using `git revert HEAD`  
	* Ideal undo method for public shared repos
	* Simply creates a new commit having the changes undone
3. Using `git reset --hard _<commit-hash>_`
	* This method of undoing changes has the cleanest effect on history.
	* Doing a reset is great for local changes however it adds complications when working with a shared remote repository. 