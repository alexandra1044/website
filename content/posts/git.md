---
author: "Alexandra Cooper"
title: "Git"
date: "2024-08-25"
draft: false
description: "A basic explaination of version control and some useful commands (so I can find them easily!)"
tags: [
    "Git",
    "Version Control"
]
---

# Basic Explaination
Git is version control software which lets you easily save and undo specific changes to your work. All successful software projects use version control of some kind.

Github or Codeberg are git hosting services that can store your source code. Multiple people can contribute to the same project. You can also use Github actions to run scripts when code is submitted (pushed, see below).

![Git Diagram showing the individual nodes](/static/images/git.svg)

You can think of git history like a chain, with each node on the chain being its own commit (with an individual commit hash for the purposes of identification).

You can branch off each node into a new branch with the original node as the base for a new branch.

You can make a pull request to merge your code changes into the chain which adds a new node with a new commit hash.

# Useful Commands

## Gitignore

A gitignore lists files that git should, well, ignore. When adding and pushing these files will not be included. 

```
touch .gitignore
```

## Making a Commit and Pushing
A commit contains a 'diff' of your changes, i.e the difference between the most recent commit and your change.

First you need to stage your changes. You can see them with the status command.

```
git status
```

To stage everything:

```
git add .
```
To be more specific

```
git add <filename>
```

Then we want to make a commit and give it a small description:
```
git commit -m "some amazing text here"
```

Then we want to push to the upstream branch if we're happy:
```
git push
```
or
```
git push <remote> <branch>
```

After this, we might want to make a pull request and ask people to check our code in a review before we merge this to master/main.

## Undoing Mistakes
Primarily, this is done with the reset command. The reset command moves HEAD which you can think of as the most recent node in the chain. 

To see the log and thus the commit hashes:
```
git log
```

Undo and discard all changes:

```
git reset --hard <commit hash>
```

Undo without discarding:
```
git reset <commit hash> 
```

## Branches

To make a new branch:

```
git checkout -b <branch name>
```

To switch to the branch you just made:

```
git checkout <branch name>
```
or
```
git switch <branch name>
```

Sometimes when you make a branch, you'll want to specify which upstream it should point to so that your changes go there. To do this:

```
git checkout -b <branch name> origin/example_upstream
```


## Patching
Sometimes you want to make a patch file containing all your changes for a given branch to be applied somewhere else. To do this as a single file:
```
git format-patch project/branch --stdout > example.patch
```
Then apply the patch:
```
git am example.patch
```

## Remote Branches
To grab all new changes from the upstream:
```
git fetch
```

## Github Actions
Github actions is an excellent feature you can take advantage of for free. It's especially good for ensuring committed code is quality, as you can automatically run a variety of tests.

## Forking

A fork is a copy of someone else's repository that belongs to you that you can freely modify and make your own without being related to their original project. There is a dropdown menu.

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo