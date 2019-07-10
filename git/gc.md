# Git gc

`gc` stands for **garbage collection**.
While doing some operations like `git reset` or `git rebase`, the history can be altered and Git accumulates various types of garbage like innaccessible commits, that can still be checked out, cherry-picked etc...

`git gc` will clean detached commit and also compress stored Git objects, freeing disk space.

`git gc` is run automatically on commands such as `git pull`, `git merge`, `git rebase` and `git commit` but running it manually is needed for frequently updated multi-users repos.

A similar command is `git prune`. `git gc` is a parent of `git prune`.
