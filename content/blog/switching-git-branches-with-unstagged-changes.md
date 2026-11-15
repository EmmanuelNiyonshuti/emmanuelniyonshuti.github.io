+++
title = "switching git branches with unstaged changes"
slug = "switching-git-branches-with-unstaged-changes"
date = 2026-11-12
description = "git checkout --merge branch-name"
taxonomies.categories = ["git"]
draft = false
+++

This probably should have been a TIL, but it's a short option on git checkout that
I have been using for few months and thought was worth taking a note of here! 

Do you ever play around with something on main or master branch and after get it working the way you want, and then want to move those changes to the other branch, only to realize you can't simply git checkout into that branch because you have unstaged changes?

Is this familiar?:
```sh
error: Your local changes to the following files would be overwritten by checkout:
        project_name/some_file.py
Please commit your changes or stash them before you switch branches.
Aborting
```
What I normally do is stash my changes `git stash`, switch branch and pop the stash `git stash pop`.
Often, I don't have to look up a particular stash with git stash list, because git stash pop attempts to apply my most recent stash and removes it from the stash list.

While this has worked for me for a while, I've found that using this option is cleaner than doing the whole stashing dance:
```sh
git checkout -m branch-name
```
You can use this with git switch as well. `-m` is short for `--merge`, and it carries my local unstaged changes over to the branch I'm checking out.

bye!
