### **HEAD in Git**
In Git, HEAD is a reference to the current or last commit in the currently checked-out branch. It can be thought of as a pointer to the current branch or current state of your repository. As you commit, the HEAD moves forward with each commit. It always represents the latest commit in the branch.

#### Detached HEAD State: 
> When you check out a specific commit instead of a branch, Git enters a 'detached HEAD' state. 
> In this state, HEAD points directly to a commit, rather than a branch. Changes made in this state aren’t attached to a branch, so they can be difficult to find after switching back to a branch. It's useful only for temporary exploration or read-only purposes in a repository. It’s generally a good idea to avoid making permanent changes while in a detached HEAD state, as these changes can be lost when switching back to a branch.

#### HEAD in Branches: 
> When you switch branches with ```git checkout [branch-name]```, HEAD updates to point to the tip of the new branch. If you create a new commit on this branch, HEAD moves forward with the new commit.

### Git Remotes
>Git remotes are like offsite backups or mirrors of your local Git repository. They allow you to collaborate with others, share your code, and work on different versions of your project simultaneously. Think of them as remote locations where your Git repository lives. 

>It could be:
>1. A remote Git server: like GitHub, GitLab, or Bitbucket.
>2. Another developer's local machine.

#### _Setting Up a Remote Repository_
> - Copy the URL of the remote repository. It's often in the format https://github.com/username/repository.git.
> - Clone the remote repository to your local machine, use: git clone <remote-repository-URL>
>
> This creates a local copy of the repository on your computer, including all files and history.

#### _Linking a Local Repository to a Remote_
- Initialize Local Repository: 
    >If you already have a local repository, initialize it with:
    ```
    git remote add <remote-name> <remote-repository-URL>
    ```

#### _List all remotes_
```
git remote -v
```

#### Fetch Command
> To fetch changes from the remote repository without merging them:
```
git fetch <remote-name>
```

#### Pull Command
> To update your local repository with changes from the remote:
```
git pull origin master
```

> Git attempts to automatically merge changes. If there's a conflict, you'll need to resolve it manually.

> Internally, git pull starts with git fetch. This command retrieves commits, files, and refs from a remote repository into your local repo.Following the fetch, git pull executes git merge to merge the retrieved branch heads into the current local branch. 
> As it executes git merge, pull can create a new merge commit as well. Optionally, git pull can rebase instead of merging. This is done using git pull --rebase  This is often a recommended approach.

#### Push Command
> Push your changes to the remote repository:
```
git push origin master
```


#### Delete Remote Branch
>To delete a branch on the remote:
````
git push origin --delete <branch-name>
````

#### Tips and Best Practices
- Regular Pulls:
  > Regularly pull from the remote to stay updated.
- Push Small Changes:
  > Push small, incremental changes rather than large, infrequent updates.

### Working on Github
#### Forking Repository
>Forking is creating your own copy of a repository. This allows you to freely experiment with changes without affecting the original project. 
> - On the GitHub page of the repository, click the "Fork" button.
> - This creates a copy under your GitHub account.
> - Now clone this repository into your local. 
> - Use the command 
>```
>git clone [URL of your fork]
>```
>This URL is found on your fork's GitHub page.
#### Syncing with Original Repository
>To ensure you have the latest changes from the original repository, add the original repository as a remote source: 
>```
>git remote add upstream [URL of original repository]
>```
>Whenever you want to fetch the changes, use the command: 
> ```
> git fetch upstream 
> ```
> and then merge the changes into your local branch: 
>```
>git merge upstream/main
>```
#### Creating a New Branch
>It's a best practice to create a new branch for your changes. This keeps your contributions organized and separated from the main project. 
> Use
> ```
> git checkout -b [new-branch-name]
> ```
> to create a new branch. Make your intended changes in the code.
#### Pushing Changes to GitHub
>Use
```
git push origin [your-branch-name]
```
> to push your changes to your fork on GitHub.
#### Creating a Pull Request (PR)
>A PR is a way to propose your changes to the original repository. On your fork's GitHub page, select your branch and click "New pull request". Add details about your changes and submit the PR.
#### Making Further Changes
> Maintainers might ask for changes. Make these changes in your local branch. After committing these changes, push them to GitHub. The PR will automatically update. Ensure you keep rebasing your repository to upstream.
#### Final Merging
>Once your PR is approved, the maintainers of the original repository will merge your changes. Congratulations, your contributions are now part of the project!

### Git Cherry-Pick
>Git cherry-pick is a powerful tool that allows you to select and apply individual commits from one branch into another. Unlike merging or rebasing, which typically apply a series of commits, cherry-picking applies only the commits you specify.

#### When to Use Cherry-Pick?
1. Selective Changes:
  > When you want to apply specific changes from one branch to another without bringing in the entire branch history.
2. Bug Fixes and Feature Backporting: 
  > For applying bug fixes or features from the main branch to a release or maintenance branch.

#### How to Cherry-Pick?
1. Identify the Commit Hash:
   > First, you need the hash of the commit you want to cherry-pick.
2. Switch to the Target Branch:
   > Use 
   > ```
   > git checkout [target-branch]
   > ```
   > to switch to the branch where you want to apply the commit.
3. Cherry-Pick the Commit:
   > - Use 
   > ```
   > git cherry-pick [commit-hash]
   > ```
   > If the commit applies cleanly, it will be added to your branch. 

   > - If there’s a conflict, Git will pause the cherry-pick operation. Manually resolve the conflicts in your code editor.
   > After resolving, add the files with
   > ```
   > git add [file-name]
   > ```

   > - Complete the cherry-pick with 
   > ```
   > git cherry-pick --continue
   > ```
4. Push the Changes: 
   > Use 
   > ```
   > git push origin [target-branch]
   > ```
   > to push the changes to the remote repository.

#### Best Practices and Tips
1. Commit Isolation: 
   > Cherry-pick works best with commits that are isolated in their changes (i.e., the commit doesn’t contain a mix of unrelated changes).
2. Testing: 
   > Always test your changes after a cherry-pick to ensure functionality hasn’t been compromised.
3. Avoid Cherry-Picking Over Regular Merges: 
   > Cherry-pick is a useful tool, but it's not a substitute for regular merging or rebasing. 
