# Tagging
- Git has the ability to tag specific points in a repository’s history as being important. Typically, people use this functionality to mark release points (v1.0, v2.0 and so on). 

## Listing Your Tags
- Listing the existing tags in Git is straightforward. Just type git tag.
##### Examples:
```
$ git tag
v1.0
v2.0
```

## Creating Tags
- Git supports two types of tags: lightweight and annotated.

- A lightweight tag  it’s just a pointer to a specific commit.
- Annotated tags, however, are stored as full objects in the Git database. They’re checksummed; contain the tagger name, email, and date; have a tagging message; and can be signed and verified with GNU Privacy Guard (GPG).

### Annotated Tags
- Creating an annotated tag in Git is simple. The easiest way is to specify -a when you run the tag command.

##### Examples:
```
$ git tag -a v1.4 -m "my version 1.4"
$ git tag
v0.1
v1.3
v1.4
```

> You can see the tag data along with the commit that was tagged by using the git show command:
```
$ git show <tag>
```

### Lightweight Tags
- To create a lightweight tag, just provide a tag name:

##### Examples:
```
$ git tag v1.4-lw
$ git tag
v0.1
v1.3
v1.4
v1.4-lw
```

> This time, if you run git show on the tag, you don’t see the extra tag information. The command just shows the commit.

## Tagging Later
- You can also tag commits after you’ve moved past them:
```
$ git tag -a <tagname> <commit checksum>
```

## Deleting Tags
- To delete a tag on your local repository, use:
```
$ git tag -d <tagname>
```