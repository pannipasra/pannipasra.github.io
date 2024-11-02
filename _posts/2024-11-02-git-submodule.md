---
title: Git Submodule Cheat Sheet
date: 2024-11-02 15:59:50 +/-0900
categories: [git]
tags: [git, cheat_sheet]     # TAG names should always be lowercase
---

## Add submodule
```
git submodule add GIT_REPO_URL PATH/SUBMODULE
```

## Clone a project that contains submodule needs
```
git submodule init
git submodule update
```
or 
```
git clone --recurse-submodules GIT_REPO_URL
```

## Update submodule from ref repo
```
cd PATH/SUBMODULE
git fetch
git merge origin/{BRANCH}
```
or
```
git submodule update --remote --recursive
```


## Remove submodule
the answer copied from: https://gist.github.com/myusuf3/7f645819ded92bda6677

- This seems to be a more modern version (copied from https://stackoverflow.com/a/36593218/2066118):

```
# Remove the submodule entry from .git/config
git submodule deinit -f path/to/submodule

# Remove the submodule directory from the superproject's .git/modules directory
rm -rf .git/modules/path/to/submodule

# Remove the entry in .gitmodules and remove the submodule directory located at path/to/submodule
git rm -f path/to/submodule
```
