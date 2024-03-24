## **Git**

Git is a version control system that allows developers to track changes made to their codebase over time. It was created in 2005 by Linus Torvalds, the founder of Linux, as a more powerful and efficient alternative to existing version control systems.

### Git Init
> The git init command is a fundamental tool in Git, used to initialize a new Git repository or reinitialize an existing one.

#### Syntax:
>```
>git init [repository name]
>```
> This creates a new subdirectory named .git that houses all of your necessary repository files. This .git directory is what makes your directory a Git repository and tracks the history and configuration.

#### *Purpose and Functionality*
- Initialization of New Repositories:
  > git init is used to start a new repository. When you run this command in a new directory, it creates a new Git repository in that directory.
- Reinitializing Existing Repositories:
  > It can also be used to reinitialize an existing repository with additional options or to repair a broken repository.
#### *Inside an Existing Directory:*
> If you have a project directory already, navigate into it and run git init. This transforms the current directory into a Git repository.
#### *Creating a New Directory for Repository:*
>You can also create a new directory and initialize it as a Git repository in one step by specifying the repository name: 
>```
>git init new-repo
>```
>where new-repo is the name of your new directory.

### Staging Area in Git
>The staging area is a layer between the working directory and the repository. It's a place where Git stores changes that you indicate (via git add) are ready to be committed to the repository.

#### *Purpose*
- Organizing Commits: 
> It allows you to craft your commits with precision. You can choose exactly which changes make up a commit.

- Partial Commits:
> This area facilitates partial commits, enabling you to stage only certain parts of the changes made in the working directory.

#### *How It Works*
> - When you make changes in your working directory, Git sees them as "modified." Using git add, these changes move to the staging area.
> - Once staged, changes are marked as "staged" and are ready to be committed.

> The git status command is useful to see which files are in which state (modified, staged, etc.).

### Git Add Command
> Git add adds changes in the working directory to the staging area, preparing them to be included in the next commit. This allows developers to choose which changes to commit.

#### Syntax:
````
git add [file or directory]
````
- Adding a Single File: 
  > To stage a specific file, use ```git add filename```.
- Adding Multiple Files:
  > You can add multiple files by listing them: ```git add file1 file2```.
- Adding All Changes:
  > To add all new and modified files, use ```git add .``` or ```git add -A```. This stages all changes in the current directory and its subdirectories.

### Git Commit
> When you run git commit, Git takes the changes that are in the staging area and saves them into the repository. When you make a commit, it is added to the end of the current latest commit.

#### Syntax:
````
git commit -m "Your message here"
````

#### Key Features
- Immutability:
  > Each commit is a permanent snapshot of the repository at a given point in time. This snapshot includes references to all the files as they existed at that moment.
- Unique Identifier:
  > Each commit is identified by a unique SHA-1 hash. This allows tracking and referencing specific commits in the repository history.

#### Best Practices
- Logical Changes: 
  > Commit related changes together. Avoid including unrelated changes in the same commit.
- Frequent Commits:
  > Commit often to capture stages of development. Smaller, more frequent commits make it easier to identify where and when changes were made.
- Testing Before Committing: 
  > Ensure your code works as expected before committing. This helps in maintaining a stable project history.

#### Understanding Commits
- Commits in History:
  > Commits are a part of the branch history. When you change branches, the commits that are part of that branch's history become the current state of the project.
- Relationship with Branches:
  > When you make a commit, it is added to the end of the current branch. This commit then becomes the latest snapshot on that branch.
- Immutability of a Git Commit

#### Immutable Nature:
> Once a commit is created in Git, it becomes an immutable snapshot of the repository at a certain point in time. This means that the commit itself cannot be altered or changed without generating a new commit.

#### ***How Immutability is Achieved:***
> Each commit is identified by a unique SHA-1 hash, which is generated based on the content of the commit (including changes, author information, date, and commit message). Changing any aspect of the commit would result in a different hash, thus creating a new commit altogether.

#### ***Implications of Immutability***
- Data Integrity:
  > The immutability of commits ensures data integrity and traceability within the repository. It allows Git to detect changes or corruption in the repository history.
- Traceability and Accountability:
  > The immutable nature of commits allows for a reliable and traceable history of changes, which is crucial for collaboration and version control.
- Amending Commits:
  > While you can't change a commit once it's made, Git allows you to "amend" a commit. However, amending actually creates a new commit with a new SHA-1 hash, replacing the old commit in the project history.

#### ***Contents of a Git Commit***
- Snapshot of Changes:
  > Contrary to a common misconception, Git does not store the complete snapshot of the entire repository in every commit. Instead, it stores a snapshot of the changes (delta) made since the last commit. This approach is more space-efficient.
- Parent Commit(s):
  > Each commit stores references to its parent commit(s). In the case of a merge commit, there will be multiple parents.
- Author Information:
  > Commits include the name and email address of the author who made the changes.
- Timestamp:
  > The date and time at which the commit was made.
- Commit Message:
  > A description provided by the author, explaining the changes made in the commit.

### Git Branching
> Multiple developers might be working on independent features at the same time. The primary purpose of branching is to diverge from the main line of development and continue to work independently without affecting the main line. Once the independent work is finished, you can converge the branches (merging back into the main branch). Branches serve as pointers to the latest commit. When you make a new commit, the branch pointer moves forward automatically. Creating a new branch in Git is a very quick and simple process as it is just creating a variable name.

- _**Creating a New Branch:**_ 
  >Use 
  >```
  >git branch [branch-name]
  >``` 
  >to create a new branch.
- _**Switching Branches:**_ 
  >Use 
  >```
  >git checkout [branch-name] 
  >```
  >to switch to an existing branch.
- _**Create and switch to a New Branch:**_ 
  ```
  git checkout -b [branch-name]
  ```
  
#### Branching Strategies
- Feature Branching: 
  > Creating a branch for each new feature or bug fix keeps the work organized and separated until it’s ready to be merged.
- Release Branching:
  > This involves creating a branch for release preparation, allowing for bug fixes and preparation without disrupting the main development work.
- Long-Running Branches:
  > Typically, a project has long-running branches like master or develop, which are stable versions of the project at different stages.

#### Best Practices
- Regular Commits and Mergers:
  > Regularly commit your changes within your branch and merge frequently from the main branch to minimize merge conflicts.
- Naming Conventions:
  > Use clear, descriptive names for branches to easily identify their purpose.
- Cleanup:
  > Delete branches after their changes have been merged to keep the repository clean and manageable.

#### Advanced Branching Commands
- _**Branch Deletion:**_ 
  >```
  >git branch -d [branch-name]
  >```
  >deletes a branch.
- _**Renaming Branches:**_
  >```
  >git branch -m [old-name] [new-name]
  >```
  >renames a branch.
- _**Viewing Branches:**_
  >```
  >git branch 
  >```
  >lists all branches.

### Git Log: 
>```
>git log --graph
>```
>provides a visual representation of the branching and merging history.

### Git Merge
>Merging in Git is a way to combine changes from different branches. It's like taking the work from one branch and adding it to another. For example, you might develop a new feature in a separate branch and then merge it into the main branch once it's ready.

_**How to Merge**_
- Choose the Target Branch: 
  > First, switch to the branch where you want the changes to go. 
  > For example,
  >  ```
  >  git checkout main
  >  ```
- Merge Another Branch: 
  > Then, use 
  >  ```
  >  git merge [branch-name]
  >  ```
  > to merge changes from [branch-name] into your current branch.

_**Dealing with Merge Conflicts**_
> - Sometimes, Git can't automatically combine changes from different branches. This happens if the same part of a file was changed in both branches. This is called a conflict. 
> - Git will mark the conflicting areas in your files. You'll need to open these files and decide how to combine the changes. After editing, save the file.
> - Once you've resolved the conflicts, use
>  ```
>  git add [file-name]
>  ```
>  to mark them as resolved, then make a commit to complete the merge.

_**Fast-Forward Merge and a Three-Way Merge**_
> - Imagine you're working on a project with a main branch, and you decide to work on a new feature. You create a new branch where you can make changes without affecting the main road.

_**Fast-Forward Merge**_
> - A fast-forward merge in Git is like having a straight road from your feature branch back to the main road. This occurs when there have been no new changes on the main branch since you started your feature branch. If nothing new has been added there, git can simply move the end of the main branch up to the end of your feature branch. Your changes are now part of the main branch. There won’t be merge conflicts in this case.

_**Three-Way Merge**_
> - A three-way merge happens when there have been other changes on the main branch while you were working on your feature. 
>- In this case, your side branch doesn’t directly fit onto the end of the main branch anymore. To merge your changes with the main branch, Git uses a special process. 
>- It looks at three points: 
>  - the end of your feature branch
>  - the end of the main branch, and 
>  - where both branches were last the same. 
>- Git then figures out how to combine these changes. 
>- In this case, there can be merge conflicts that you will have to resolve.

_**Squash Merge**_
>- Squash merging is a way to combine all the changes from a feature branch into a single commit when you merge it into another branch.
>- It's useful for keeping your history clean and organized. 
>- Instead of having many small commits from a feature branch, you have one concise commit.

_Syntax:_ 
> Use 
>```
>git merge --squash [feature-branch]
>``` 
>This combines all changes into a single commit. After this, you'll need to commit these changes manually with git commit.

### Best Practices for Merge and Conflict Resolution
- Regular Merges:
  > Frequently merge changes from the main branch into your feature branch. This reduces the chances of conflicts.
- Clear Commit Messages:
  > When you complete a merge or resolve a conflict, write a clear commit message explaining what you did.
- Test Before Merging:
  > Always test your code to make sure it works correctly before and after merging.

### Git Rebase
>In Git, rebase is a command that helps to move or combine a sequence of commits to a new base commit. It's a way to rearrange the history of your commits for a cleaner, more linear progression.

#### Why Rebase
- Clean History: 
  > Rebase is often used to tidy up a series of commits before merging them into a main branch. It can make the history more readable and easier to understand.
- Integrating Changes: 
  > Rebasing can also be used to integrate changes from one branch into another, similar to merging but with a different approach.

_**How Rebase Works**_
- Switch to Your Feature Branch:
  > Start by being in the branch with your new work, for example, git checkout feature-branch.
- Start the Rebase: 
  > Use
  >```
  >git rebase [base-branch]
  >```
  >where [base-branch] is the branch you want to rebase onto (often main or master). 
- Git Re-applies Commits: 
  > Git takes the commits from your feature branch and re-applies them on top of the latest commit in the base branch. This makes it look like your changes were made on top of the current state of the base branch.

_**Conflict Resolution in Rebase**_
- Handling Conflicts:
  > If Git encounters conflicts during rebase, it will pause and allow you to resolve them. This is similar to resolving conflicts in a merge.
- Resolving and Continuing:
  > After fixing the conflicts in a file, use 
  >```
  >git add [file-name]
  >```
  > to mark it as resolved. 
  
  > Then, continue the rebase with
  > ```
  > git rebase --continue.
  > ```

### Benefits of Rebase
- Linear History: 
  > Rebasing creates a linear project history, which can be easier to follow than the branched history created by merging.
- Avoiding Extra Merge Commits:
  > It eliminates the need for an extra merge commit that you get when using git merge.

### Best Practices for Rebase
- Not on Public Branches:
  > Avoid rebasing commits that are already on public branches. Rewriting history in this way can cause problems for others working on the same repository.
- Use in Local Development:
  > Rebase is best used for cleaning up your local commits before integrating them into a shared branch.

### Difference Between Merge and Rebase
- Merge: 
  > Keeps the original history and adds a new commit that merges two branches.
- Rebase: 
  > Moves the entire branch to start from a different point, creating a straight, linear history.
