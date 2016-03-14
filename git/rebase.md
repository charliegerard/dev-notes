# Git pull --rebase

`git pull` = `git fetch` + `git merge` against tracking upstream branch

`git pull --rebase` = `git fetch` + `git rebase` against tracking upstream branch

An easier way to understand the difference is this way:

If you have 3 commits A, B & C.

![commits](http://i.stack.imgur.com/lJRq7.png)

Then developer X creates a commit D and developer Y creates a commit E.

![commits](http://i.stack.imgur.com/pK7Zb.png)

To resolve this conflict, there are 2 ways:

**MERGE**:

![commits](http://i.stack.imgur.com/9Ul5w.png)

Both commits D & E are still there but a merge commit M is created containing the changes from D & E.

**REBASE**:

![commits](http://i.stack.imgur.com/TvXuJ.png)

We create commit R which content is identical to merge commit M, but we get rid of E. Advantage is that diamond shape is avoided and history stays nice in a straight line.
