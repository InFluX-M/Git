# Git Repository & Changes

## Getting a Git Repository
  - You can take a local directory that is currently not under version control, and turn it into a Git repository.
  - You can clone an existing Git repository from elsewhere.

### Initializing a Repository in an Existing Directory
If you have a project directory that is currently not under version control and you want to start controlling it with Git, you first need to go to that project’s directory and type:

```
git init
```

##### Examples:
```
git init                                -> Initialize a Repository in current directory
git init /home/user/my_project          -> Initialize a Repository in /home/user/my_project
git init C:/Users/user/my_project       -> Initialize a Repository in C:/Users/user/my_project
```

> This creates a new subdirectory named .git that contains all of your necessary repository files — a Git repository skeleton. At this point, nothing in your project is tracked yet. See [Git Internals](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain#ch10-git-internals) for more information about exactly what files are contained in the .git directory you just created.

### Cloning an Existing Repository
If you want to get a copy of an existing Git repository — for example, a project you’d like to contribute to — the command you need is:

```
git clone <url>
```

##### Examples:
```
git clone https://github.com/libgit2/libgit2
git clone https://github.com/libgit2/libgit2 mylibgit -> + Rename Repository DirecStoy
```

> Git receives a full copy of nearly all data that the server has. Every version of every file for the history of the project is pulled down by default when you run git clone. In fact, if your server disk gets corrupted, you can often use nearly any of the clones on any client to set the server back to the state it was in when it was cloned (you may lose some server-side hooks and such, but all the versioned data would be there — see [Getting Git on a Server](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain#ch10-git-internals) for more details).


## Recording Changes to the Repository
Remember that each file in your working directory can be in one of two states:
  - tracked: are files that were in the last snapshot, as well as any newly staged files. they can be:
    - unmodified
    - modified: changed them since your last commit.
    - staged: you selectively stage modified files and then commit all those staged changes.
  - untracked: any files in your working directory that were not in your last snapshot and are not in your staging area.

![LifeCycle](../Photos/lifecycle.png)

## Checking the Status of Your Files
The main tool you use to determine which files are in which state is:

```
git status
```

> If you run **git status -s** or **git status --short** you get a far more simplified output from the command. -see more [Short Status](https://stackoverflow.com/questions/51210915/understanding-the-output-of-git-status-with-the-short-flag) 


## Tracking New Files
In order to begin tracking a new file (modified, untracked), you use the command:

```
git add <path>
```

> The git add command takes a path name for either a file or a directory; if it’s a directory, the command adds all the files in that directory recursively.

> git add is a multipurpose command — you use it to begin tracking new files, to stage files, and to do other things like marking merge-conflicted files as resolved. It may be helpful to think of it more as “add precisely this content to the next commit” rather than “add this file to the project”.

> If you modify a file after you run git add, you have to run git add again to stage the latest version of the file.

## Committing Your Changes
- Now that your staging area is set up the way you want it, you can commit your changes. Remember that anything that is still unstaged won’t go into this commit. let’s say that the last time you ran git status, you saw that everything was staged, so you’re ready to commit your changes. 

```
git commit -m "Message"
```

## Skipping the Staging Area
- The staging area is sometimes a bit more complex than you need in your workflow. If you want to skip the staging area, Git provides a simple shortcut. Adding the -a option to the git commit command makes Git automatically stage every file that is already tracked before doing the commit, letting you skip the git add part.

> This is convenient, but be careful; sometimes this flag will cause you to include unwanted changes.