## What is VCS (Version Control System) ?

- Version Control System is a software that tracks and manages changes to files over time.
- Version Control System allows users to revisit earlier versions of the files, compare changes between versions, undo changes, and a whole lot more.

## What is GIT?

- Git is VCS.
- Git helps in many ways:
  a) Track changes across multiple files
  b) Compare versions of projects
  c) "Time Travel" back to old versions
  d) Revert to a previous versions
  e) Collaborate and share changes
  f) Combine changes
  <br>
  Git Workflow
  ![Git Workflow](./images/GitFlow.png)

  ### Difference between Git and Github?

  #### Git

  - Git a VCS that runs on your machine
  - Don't need account to use git
  - Even internet is not needed

  #### Github

  - Github is a service that hosts git repositories in the cloud and makes it easier to collaborate with other people.
  - Account is needed to use Github.

### Configuring Git

#### Configuring User Name

`git config --global user.name "<name>"`

#### Configuring User Email

`git config --global user.email "<name@domain.com>"`

You can change above whenever you want. This only helps in logs. Help to identify who had makes changes.

### What are Git Repos?

A Git "Repos" is a workspace which tracks and manages files within a folder.

### Initiate a new Git Repos

`cd Project`<br>
`git init #this initiate a new git repo`<br>
`git status #check the status of new repo created`

#### If you want to delete a git repo

`rm -rf .git`<br>

- Prevent your .git to automatically get deleted by changing the permission to (555)<br>
  `chmod 555 .git` or `chmod -x .git`

⚠️ DO NOT INIT A REPO INSIDE A REPO, VERIFY IT USING `git status` first

### What is git commit ?

Inside a git repository there are three working area named. First when someone makes changes to the files inside the working directory its gets added to the staging area using the command <br>`git add <file> <file> ...`

Commit area is a save point where new files can be added till you decide it either push it to remote repository or roll it back to delete the file.

Then using command <br>
`git commit -m "<msg>"` <br>
it can be moved to repository where .git keeps tracks of all the commited files.

![Commit](./images/commit.png)

#### How to perform best commits ?

- Try to do atomic commits.
- In atomic commits, try to keep each commit focused on a single thing
- Atomic commits also makes code easy to review

##### Which tense to use while writing a commit message?

- Github document shows that we should use Present-Tense Imperative Style technique.
- You can either use past tense or present tense.

### Git default commit editor setup!

`git config --global core.editor "code --wait"`
=>[link_For_all_editor](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config)

### [About Git log](https://git-scm.com/docs/git-log)

- You can pretty print the git log also
- Suppose you only want one line of git log if the log message is very long you can use flag --oneline<br>
  `git log --oneline`

### Redoing previous commit

- Suppose you just made a commit and you realized that you forgot to include a file, or you made a typo in the commit message.
- Rather than making a brand new commit, you can redo the previous commit using command<br>
  `git commit --amend`

### Ignoring files

- Create a file with name as ".gitignore" in same directory.
- Inside this file enter the name of file and folder you want git to not track.
- `folderName/` will ignore an entire directory.
- `*.log` will ignore any file with .log extension. Here is \* is a wildcard

Note: Here gitignore.io which will help you to find all gitignore files for your project

## Branches

- Every commit in git contains a hash, a parent hash and a message.
- Branch are like alternative timelines for a project. They enable us to work on multiple things in parallel and they do not impact the other branches
- In 2020, Github renamed the default branch master to main.

#### What is HEAD?

- Head is simply a pointer that refers to the current "location" in your repository. It points to a particular branch reference
- It is possible to move around and HEAD will change.

###### Viewing all branches

- `git branch` -> This will show all branches.
- The \* before branch name shows in which branch you are on and currently working.

###### Creating and Switching branches

- `git branch <branch-name>` will create a branch, if branch does not exist.
- A branch name cannot include spaces.
- In order to switch between branches use `git switch <branch-name>`.

⚠️Note: `git add .` + `git commit -m <msg>` = `git commit -a -m "<msg>"`

##### Git Switch vs Git checkout

- Git switch is newer than git checkout
- Git switch only switches the branch, but checkout does alot more.
- There are different flags such as -b you can pass to create a branch
- Use git switch for simplisity

###### Git switch with -c

- If you want to create a new branch and switch it with same command you can use -c flag: <br>
- `git switch -c <branch-name>`

⚠️Note: You can't switch to another branch with unstaged changes. You either need to commit then or you can stash them.

### Deleting and renaming branches

##### Delete

- In order to delete branch first make sure it is merged with the main/master or not.
- After the successful merge use command: `git branch -d <branch-name>`. <br>
- If you want to delete the branch without merging use: `git branch -D <branch-name>`.<br>

##### Rename

- In order to rename branch -m flag is used.
- Also inorder the rename the branch you should be at that branch.
- Command to rename: `git branch -m <new-name>`<br>

### Merging

- If we want to incorporate changes from one branch to another merging is use.
- Command is `git merge <branch-name>`<br>
- Remember two merging concept:
  -- We merge branches not commits.
  -- We always merge to the current HEAD branch (change to branch where you want merge to happen then use the command to merge another branch to this branch)

#### There are three types of merges

- Fast-Forward Merge
- Merge Commit (No Conflicts)
- Merge Commit (Conflicts)

##### Fast-Forward Merge

- In fast forward merge we do not have any merge conflict. This means that new updated branch already contains all the works of the master/ main branch
- In this only the pointer of master branch gets shifted to the new branch HEAD position. (Easiest type of merge)

##### Merge Commit (No Conflicts)

- In this type of merge no conflict occur between the branches.
- In this the main/ master branch does not contain any changes that will create the conflict and merge can happen automatically

##### Merge Commit (Conflicts)

- In this type of merge conflict occur between the branches.
- In this the main/ master branch does contain any changes that will create the conflict and merge can not happen automatically.
- You have to manually edit the changes, you have to select which changes to keep and which changes to remove.
