# Some important tips

## Ways to undo changes
1. Using `git checkout <commit-hash>` for detaching the HEAD to a particular commit.  This creates detached HEAD and any commits during this stage are orphaned. Such commits are disposed by git's garbage collector over time. However, if we wish to keep these changes, we need to create a new branch not having all the future commits but only this new commit and commits before that.  
	Use `git checkout -b <branch-name> <orphan-commit-hash>`
		