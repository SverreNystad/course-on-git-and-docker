## Getting Started with Git

Initialize a new Git repository in the current directory.
```bash
git init
```
Clone an existing repository from a URL to your local machine.

```bash
git clone <repository-url>
```


## Basic Snapshotting
Show the status of changes as untracked, modified, or staged.
```bash
git status
```

Add a file to the staging area, making it ready for commit.
```bash
git add <file>
```

Commit the staged changes to the repository with a descriptive message.
```bash
git commit -m "Descriptive message"
```

If you want to add all files and commit them in one command.
```bash
git commit -am "Descriptive message"
```


## Branching and Merging
List all local branches in the repository. With -a, shows all branches.
```bash
git branch
```

Create a new branch.
```bash
git branch <branch-name>
```

Switch to the specified branch.
```bash
git checkout <branch-name>
```

Create a new branch and switch to it.
```bash
git checkout -b <branch-name>
```

Merge the specified branch’s history into the current branch.
```bash
git merge <branch>
```


## Sharing and Updating Projects
Push commits made on your local branch to a remote repository.
```bash
git push
```

Fetch and merge changes on the remote server to your working directory.
```bash
git pull
```

Fetch changes from the remote repository but doesn't merge them.
```bash
git fetch
```


## See history
Show the commit history for the current branch.
```bash
git log
```

To see the commit in a more condensed view.
```bash
git log --oneline
```

To see the history in a nice graph.
```bash
git log --graph --oneline --decorate
```

## Stashing and Cleaning
Temporarily stash changes in the working directory so you can work on a different task.
```bash
git stash
```

Apply stashed changes back to your working directory.
```bash
git stash pop
```
## Working with Remotes
Add a new remote repository.
```bash
git remote add <remote-name> <repository-url>
```
 List all configured remote repositories.
```bash
git remote -v
```


## Advanced Commands
Apply changes from one branch onto another.
```bash
git rebase <branch>
```

Unstage a file while retaining the changes in the working directory.
```bash
git reset <file>
```

Reset the current HEAD to the specified commit, discarding all changes in the working directory and index.
```bash
git reset --hard <commit>
```