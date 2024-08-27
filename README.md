# Gitflow Workflow Project

## Table of Contents
1. [Project Setup](#project-setup)
2. [Branching and Merging](#branching-and-merging)
3. [Tags and Releases](#tags-and-releases)
4. [Summary](#summary)

## Project Setup

1. **Initialize the repository**
    ```cmd
    mkdir gitflow-workflow
    cd gitflow-workflow
    git init
    ```

2. **Create and commit the README file**
    ```cmd
    echo gitflow-workflow's README > README.md
    git add README.md
    git commit -m "add README.md"
    ```

3. **Create and switch to the `develop` branch**
    ```cmd
    git checkout -b develop
    ```

4. **Add `fileA.txt` and commit**
    ```cmd
    echo. > fileA.txt
    git add fileA.txt
    git commit -m "add fileA.txt"
    ```

## Branching and Merging

5. **Create and switch to the `feature` branch**
    ```cmd
    git checkout -b feature
    ```

6. **Work on `feature` and commit changes**
    ```cmd
    echo feature 1 wip > fileA.txt
    git add fileA.txt
    git commit -m "feature 1 wip"
    
    echo feature 1 with 2 bugs > fileA.txt
    git add fileA.txt
    git commit -m "feature 1 with 2 bugs"
    ```

7. **Merge `feature` into `develop`**
    ```cmd
    git checkout develop
    git merge --no-ff feature -m "Merge feature 1 into develop"
    ```

8. **Delete the `feature` branch**
    ```cmd
    git branch -d feature
    ```

9. **Create and switch to the `feature2` branch**
    ```cmd
    git checkout -b feature2
    ```

10. **Work on `feature2` and commit changes**
    ```cmd
    echo feature 1 with 2 bugs^feature 2 wip > fileA.txt
    git add fileA.txt
    git commit -m "add feature 2 wip"
    ```

11. **Create and switch to the `release1` branch**
    ```cmd
    git checkout -b release1
    ```

12. **Work on `release1` and commit changes**
    ```cmd
    echo feature 1 with one bug > fileA.txt
    git add fileA.txt
    git commit -m "fix feature 1 bugX"
    ```

13. **Merge `release1` into `master` and tag it**
    ```cmd
    git checkout master
    git merge --no-ff release1 -m "merge branch release1"
    git tag -a v1.00 -m "version 1"
    ```

14. **Merge `release1` into `develop`**
    ```cmd
    git checkout develop
    git merge --no-ff release1 -m "merge release 1 into develop"
    ```

15. **Delete the `release1` branch**
    ```cmd
    git branch -d release1
    ```

16. **Rebase `feature2` onto `develop`**
    ```cmd
    git checkout feature2
    git rebase develop
    ```

17. **Create and switch to the `hotfix1` branch**
    ```cmd
    git checkout master
    git checkout -b hotfix1
    ```

18. **Work on `hotfix1` and commit changes**
    ```cmd
    echo feature 1 > fileA.txt
    git add fileA.txt
    git commit -m "fix feature 1 with bug Y"
    ```

19. **Merge `hotfix1` into `master` and tag it**
    ```cmd
    git checkout master
    git merge --no-ff hotfix1 -m "merge branch hotfix1"
    git tag -a v1.01 -m "fixed feature 1"
    ```

20. **Merge `hotfix1` into `develop`**
    ```cmd
    git checkout develop
    git merge --no-ff hotfix1 -m "merge branch hotfix1 into develop"
    ```

21. **Delete the `hotfix1` branch**
    ```cmd
    git branch -d hotfix1
    ```

22. **Rebase `feature2` onto `develop` again**
    ```cmd
    git checkout feature2
    git rebase develop
    ```

## Tags and Releases

- **Tags**
  - `v1.00`: Tag for release version 1.00.
  - `v1.01`: Tag for hotfix version 1.01.

## Summary

This repository demonstrates the use of the Gitflow workflow for managing feature development, releases, and hotfixes. The provided commands cover branch creation, merging, rebasing, and tagging processes.

Feel free to explore the repository and review the commit history for a practical understanding of the Gitflow workflow.

