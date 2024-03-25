# Git Cheatsheet
###### Everything You Need to Know in One Handy Cheatsheet
Git is a version control system that allows you to track changes to files and folders. It’s a powerful tool that can be used for everything from small personal projects to large-scale enterprise applications.

This guide is a quick reference to the most common Git commands. It’s not meant to be a comprehensive guide to Git, but rather a quick reference to the most common commands.

Here’s the revised git cheatsheet with improved section titles and reorganized:

## Useful Common Commands
### Setup and Configuration:
###### Initialize a new Git repository
>```
>git init 
>```
###### Clone and create a local copy of a remote repository
>```
>git clone <url>
>```
###### Configure global Git settings
>```
>git config --global <setting_name> <value>
>```
###### Configure local Git settings for a specific repo
>```
>git config --local <setting_name> <value>
>```
###### Show a summary of your Git configuration settings
>```
>git config --list
>```

### File Operations:
###### Show working tree status
>```
>git status
>```
###### Add files to the staging area
>```
>git add <file(s)>
>```
###### Remove files from working tree and staging area
>```
>git rm <file(s)>
>```
###### Move or rename a file
>```
>git mv <old_file> <new_file>
>```
###### Commit changes with a message
>```
>git commit -m "commit message"
>```
###### Show differences between working tree and last commit
>```
>git diff
>```

### Branching and Merging:
###### List all branches
>```
>git branch
>```
###### Create a new branch
>```
>git branch <branch_name>
>```
###### Switch to a specific branch
>```
>git checkout <branch_name>
>```
###### Merge a branch into the current branch
>```
>git merge <branch_name>
>```
###### Delete a specific branch
>```
>git branch -d <branch_name>
>```
###### List all remote branches
>```
>git branch -r
>```
###### List branches with additional information
>```
>git branch -vv
>```
###### Create a new branch based on a remote branch
>```
>git checkout -b <branch_name> <remote_name>/<remote_branch>
>```
###### Cancel merge in case of conflicts
>```
>git merge --abort
>```
###### Rebase the current branch onto another branch
>```
>git rebase <branch_name>
>```
###### Cancel an ongoing rebase operation
>```
>git rebase --abort
>```
###### Interactive rebase for edit, squash, re-order or drop commits
>```
>git rebase -i
>```
###### Rebase commits in the current branch onto a remote branch interactively
>```
>git rebase -i <remote_name>/<remote_branch>
>```

### Remote Repositories:
###### List remote repositories
>```
>git remote
>```
###### Add a remote repository
>```
>git remote add <name> <url>
>```
###### Fetch from a remote repository
>```
>git fetch <remote_name>
>```
###### Pull changes from a remote branch
>```
>git pull <remote_name> <remote_branch>
>```
###### Push changes to a remote repository
>```
>git push <remote_name> <local_branch>
>```
###### Remove a remote repository
>```
>git remote rm <remote_name>
>```
###### Display information about a specific remote repository
>```
>git remote show <remote_name>
>```
###### Show the tracking branches for remote repositories
>```
>git remote show <remote_name> --verbose
>```
###### Fetch updates from all remote repositories
>```
>git remote update
>```
###### Force-push changes to a remote repository, overwriting remote history
>```
>git push --force <remote_name> <local_branch>
>```
###### Push all tags to a remote repository
>```
>git push --tags <remote_name>
>```
###### Rename a remote repository
>```
>git remote rename <old_name> <new_name>
>```
###### Change the URL of a remote repository
>```
>git remote set-url <name> <new_url>
>```
###### Remove stale remote-tracking branches
>```
>git remote prune <remote_name>
>```
###### List all remote branches that have been merged into the current branch
>```
>git branch -r --merged
>```
###### List all remote branches not yet merged into the current branch
>```
>git branch -r --no-merged
>```
###### Fetch updates from a remote repository and prune obsolete remote-tracking branches
>```
>git fetch -p
>```

### Commit History:
###### Show commit history
>```
>git log
>```
###### Display a condensed commit history
>```
>git log --oneline
>```
###### Show branching commit history
>```
>git log --graph
>```
###### Filter commit history by author
>```
>git log --author=<author_name>
>```
###### Show commit history since specific date
>```
>git log --since=<date>
>```
###### Show commit history until specific date
>```
>git log --until=<date>
>```

### Commit Management:
###### Modify the latest commit
>```
>git commit --amend
>```
###### Create a new commit that undoes changes from a previous commit
>```
>git revert <commit_id>
>```
###### Discard changes and move HEAD to a specific commit
>```
>git reset --hard <commit_id>
>```
###### Move HEAD to a specific commit, but preserve staged changes
>```
>git reset --soft <commit_id>
>```
###### Show a record of all changes made to the local repository head
>```
>git reflog
>```

### Tagging:
###### List all tags
>```
>git tag
>```
###### Create a new tag at a specific commit
>```
>git tag <tag_name> <commit_id>
>```
###### Create an annotated tag with a message
>```
>git tag -a <tag_name> -m "tag message"
>```
###### Delete a specific tag
>```
>git tag -d <tag_name>
>```
###### Delete a specific remote tag
>```
>git push <remote_name> --delete <tag_name>
>```
###### Show information about a specific tag
>```
>git show <tag_name>
>```

### Cherry-Picking:
###### Apply changes from a specific commit to the current branch
>```
>git cherry-pick <commit_id>
>```
###### Apply changes from a specific commit range to the current branch
>```
>git cherry-pick <start_commit_id>^..<end_commit_id>
>```
###### Apply changes from a specific commit range to a specific branch
>```
>git cherry-pick <start_commit_id>^..<end_commit_id> <branch_name>
>```

