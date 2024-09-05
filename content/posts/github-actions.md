---
author: "Alexandra Cooper"
title: "Github Actions"
date: "2024-09-05"
draft: false
description: "How to Run Github Actions"
tags: [
    "Github Actions",
    "Yaml"
]
---

# What are Github Actions?

CI/CD means continuous integration and continuous delivery/deployment. You can easily add this to your own projects with Github Actions.

A github action triggers when an event occurs, for example someone makes a pull request or pushes code. 

If you're working alone, Github's free tier is most likely sufficient for your needs, but so as to not waste those precious compute seconds, you can pre-run your github action files locally to check they work using act: https://github.com/nektos/act (you also need docker for this).

Can be triggered with Github CLI.

# What sort of things can I use it for?

With Github Actions you can:
1. Run tests when code is pushed or a pull request is made
2. Run a build of the code to check for errors
3. Run a deployment of new code
4. Generate reports
5. Linting
6. Mark & label issues
7. Reproduce an issue and mark it as reproducible or not

# How to add Github Actions to your Project

## Templates
There are a number of template files available so that you don't need to write the actions yourself. These are typically based on common workflows.

https://github.com/actions/starter-workflows

Also check out https://github.com/sdras/awesome-actions for other pre-written actions.

## Setup
You'll need to add your new workflow file to the path below:
```
.github/workflows/<name.yaml>
```
See these example workflows: https://github.com/actions/

## Syntax

Let's take a look at this example issue from the link below:

```
name: Issue assignment <--- All actions need a name

on:
    issues:
        types: [opened] <--- Specifies what type of issue we want to run on

jobs:
    auto-assign: <--- Specify that the job is an auto assignment
        runs-on: ubuntu-latest <--- What OS we're running on
        steps:
            - name: 'Auto-assign issue' <--- Must name individual steps
              uses: pozil/auto-assign-issue@v1.11.0 <--- The code we're using for this action
              with:
                  assignees: phantsure,tiwarishub,anuragc617,vsvipul,bishal-pdmsft 
                  numOfAssignee: 1

```
Most workflows are extremley human-readable. The best way to understand the syntax is to step few a through like this.

The best document to read for syntax: https://docs.github.com/en/actions/writing-workflows/workflow-syntax-for-github-actions

This repository contains the above workflow and most listed above: https://github.com/actions/starter-workflows/tree/main/.github/workflows


You can make some cool stuff with Github actions, like this site!