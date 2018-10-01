---
title: Merging vs Rebasing in git
date: 2017-09-28 14:17:15
tags: Others
---
## Overview
The first thing to understand about git rebase is that it solves the same problem as git merge. Both of these commands are designed to integrate changes from one branch into another branch—they just do it in very different ways.
<img src="https://github.com/chen-zhi/notes/blob/master/img/git/01.png?raw=true">

## Merge

Merge the master branch into the feature branch:
```
git checkout feature
git merge master
```
Or:
```
git merge master feature
```
This creates a new “merge commit” in the feature branch that ties together the histories of both branches, giving you a branch structure that looks like this:
<img src="https://github.com/chen-zhi/notes/blob/master/img/git/02.png?raw=true">
Merging is nice because it’s a non-destructive operation.
If master is very active, this can pollute your feature branch’s history quite a bit.

## Rebase
Rebase the feature branch onto master:
```
git checkout feature
git rebase master
```
This moves the entire feature branch to begin **on the tip of the master branch**.
<img src="https://github.com/chen-zhi/notes/blob/master/img/git/03.png?raw=true">
The major benefit of rebasing is that you get a much cleaner project history. 
But, there are two trade-offs for this pristine commit history: safety and traceability.

## Read more
Read more [here](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)