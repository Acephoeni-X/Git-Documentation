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
