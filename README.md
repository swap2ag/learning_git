# Some important tips

## Ways to undo committed changes
1. Using `git checkout <commit-hash>` for detaching the HEAD to a particular commit.  
	This creates detached HEAD and any commits during this stage are orphaned. Such commits are disposed by git's garbage collector over time. However, if we wish to keep these changes, we need to create a new branch not having all the future commits but only this new commit and commits before that.  
	Use `git checkout -b <branch-name> <orphan-commit-hash>`  
2. Using `git revert HEAD`  
	* Ideal undo method for public shared repos
	* Simply creates a new commit having the changes undone
3. Using `git reset --hard <commit-hash>`
	* This method of undoing changes has the cleanest effect on history.
	* Doing a reset is great for local changes however it adds complications when working with a shared remote repository. 

## Please refer to readme on both branches to see my extensive research results

# Exposing ports

If you want to access services running in your workspace, e.g. a development HTTP server on port `8080`,
you need to expose that port first. Gitpod has two means of doing that:

1. On-the-fly: when you start a process which listens on a port in your workspace, Gitpod will ask you if you want to expose that port to the internet.
2. In your configuration: if you already know that you want a particular port exposed, you can configure it in the `.gitpod.yml` file and skip the extra click later on. For example:

```text
ports:
  - port: 8080
    onOpen: open-browser
```

## Jupyter config

Enter below command to generate jupyter configuration file for the first time.  
`jupyter notebook --generate-config`

## Allow all ip addresses

```python
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
```

[Resource link](https://jupyter-notebook.readthedocs.io/en/stable/public_server.html#running-a-public-notebook-server)

