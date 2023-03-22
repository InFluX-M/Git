# Commit History & Undoing Things

## Viewing the Commit History
- After you have created several commits, or if you have cloned a repository with an existing commit history, you’ll probably want to look back to see what has happened. The most basic and powerful tool to do this is the git log command.

##### Examples:
```
$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Mar 17 21:52:11 2008 -0700

    Change version number

commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 16:40:33 2008 -0700

    Remove unnecessary test

commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 10:31:28 2008 -0700

    Initial commit
```
> By default, with no arguments, git log lists the commits made in that repository in reverse chronological order.
> This command lists each commit with its SHA-1 checksum, the author’s name and email, the date written, and the commit message.

- A huge number and variety of options to the git log command are available to show you exactly what you’re looking for. -see more [Git Log Options](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

## Undoing Things
- At any stage, you may want to undo something. Here, we’ll review a few basic tools for undoing changes that you’ve made. 

### Last Commit
- One of the common undos takes place when you commit too early and possibly forget to add some files, or you mess up your commit message. If you want to redo that commit, make the additional changes you forgot, stage them, and commit again using the --amend option:
```
$ git commit --amend
```

### Unstaging a Staged File
- For example, let’s say you’ve changed two files and want to commit them as two separate changes, but you accidentally type git add * and stage them both. How can you unstage one of the two?
```
$ git reset HEAD <file>
```

### Unmodifying a Modified File
- What if you realize that you don’t want to keep your changes to the file? How can you easily unmodify it — revert it back to what it looked like when you last committed (or initially cloned, or however you got it into your working directory)?
```
$ git checkout -- <file>
```

### Undoing things with git restore
-Git version 2.23.0 introduced a new command: git restore. It’s basically an alternative to git reset which we just covered. From Git version 2.23.0 onwards, Git will use git restore instead of git reset for many undo operations.

Let’s retrace our steps, and undo things with git restore instead of git reset.
#### Unstaging a Staged File with git restore
```
$ git restore --staged <file>
```

#### Unmodifying a Modified File with git restore
```
$ git restore <file>
```
