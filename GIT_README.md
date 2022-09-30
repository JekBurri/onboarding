# Version Control with Git

<br>

## What is Version Control?

<br>

Version or source control refers to tracking, and managing the changes made to a software codebase. 

This is done to ensure that the current published version is **stable and functional**. Something that takes on a greater importance when relating to a public facing product.

The tools that enable this to occur are

<br>

- **Branching:** Duplicating a portion of a repository (source code)

- **Merging:** Adding or re-integrating code into a repository

<br>

Branching allows the developer to make changes without directly affecting the source code.

Merging allows the developer to update the source code with their changes.

Together they provide an infrasructure for updating code that minimizes the risk to the project as much as possible. 

<br>

## What is Git?

<br>

Git is first and foremost a **language specialized in managing version control** for projects of any size. 

When learned properly it allows you to ensure the integrity of your code base efficiently. This is done in two ways: 

<br>

- Tracking changes in the codebase of your project. 

- Enabling branching and merging through the CLI (Command Line Interface)

<br>

As you can see, Git's functionality is a 1:1 mirror of what version control entails. The two come hand in hand, which is largely why it is the industry standard today.

<br>

## What is GitHub?

<br>

GitHub is an online service that hosts repositories being managed by Git. 

As it functions on the usage of Git, GitHub inherits all of Git's capabilities. Though it dresses them up with a simple, intuitive user interface. GitHub's major advantage however is that it also **stores your repository on the cloud**.

Collaborating on a project can be done without being connected to the same server or network. Instead GitHub serves as the central storage point for the client-facing version of the project.

<br>

## What Git Commands do I Need to Know?

<br>

### `git init` - initiate a repository

- Creates an empty repository

- `.git` directory with no additions or changes

<br>

#### What is a `.git` Directory?

<br>

The `.git` directory is ignored by Git and contains all the info necessary for version controlling a project. Examples are information relating to changes in the source code, and the address for the remote repository.

<br>

### `git add filepath/here` - add a file to your respository

- Adds the contents of a file to the index

<br>

#### What is the Index?

<br>

The Git Index is the "staging area" for changes on your local system before they are sent out to the remote repository.

<br>

### `git commit -m <msg>` - capture a snapshot of current changes alongside a message

- Groups changes in the index under a label

- Saves these changes so that they can be reverted back to if needed

<br>

#### How do I Write a Good Commit Message?

<br>

- Describe why a change is being made in one sentence

    - If you can't do this it generally means you should have committed earlier

- How does it address the issue?

- What effects does it have?

<br>

### `git push` - push local commits to a remote repository
- **Important:** We won't push to the main repository for any club activities

- Integrates all commits into the remote repository

<br>

#### Why Avoid `git push` ?

<br>

Git push allows you to seamlessly integrate changes into your cloud stored version of the code. This is an excellent tool for personal programming projects. 

However it is counterproductive in the lens of learning to create projects as a team. Part of this experience is learning to review and quality assure each other's code.

Paid accounts on GitHub allow you to set conditions before a push can occur. However we unfortunately do not have that luxury.

**Proposed Countermeasure**

1. All changes must be pushed to a branch named "Development-DevName"

2. When they are ready to integrate a merge request is made instead

3. When the code associated to the merge request is cleared by 3 others, the code is then merged into the repository

<br>

### `git checkout -b new-branch` - create and move to new branch
- Clones the repository and shifts your development environment to it

- Provides you a replica that is safe to experiment and develop on

- To create a branch but not move to it use `git branch <branch_name>`

- To move to a pre-existing branch use `git checkout [branch-name]`

<br>

### `git merge` - incorporates changes from commits to current branch
- Gathers all labeled commits from local branch of repository

- Integrates all labelled commits into the remote repository

<br>

### `git pull` - pull latest changes from remote repository
- Incorporates changes in the remote repository into your local repository

- Allows you to update your local repository to match recent developments in the client-facing project

- Ensures you are developing and testing your code in an up-to-date environment

<br>

### `git log` - displays all commits in a repository's history
- Provides a changelog for work done on a repository
    - Only works if you label your commits well!

<br>

### `git diff` - display changes between index and current file
- Provides a changelog for the work done since your last commit

- Once you commit the changes become part of the "snapshot" produced by that Git command 

<br>

## What is a Merge Conflict?

<br>

A merge conflict occurs when there are competing changes made to the same line of a file. Or when one developer edits a file that another has deleted.

These may seem like extreme cases. However when there are multiple heads working on a complex problem, logic is not always universal.

A merge conflict stops competing updates from intermingling and gives the developers a chance to work out the resolution.

It may seem harsh, but a merge conflict is a failure in communication. This is not to say that there is an expectation for projects to reach completion with no merge conflicts. But rather to say that they should be treated as what they are: 

**A blip in communications over what the next steps are that needs to be resolved.**

Merge conflicts should never be ignored and should be addressed with an open mind. Work with your team to isolate the conflict and find a solution that suits all of you. A good place to start is these three commands:

1. `git status`

2. `git log --merge`

3. `git diff`