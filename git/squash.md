# Squashing all commits of a branch together

```bash
// Make sure your branch is up to date with master
git pull --rebase origin master

// Open the interactive editor with all commits in the branch
git rebase -i master

// Change from 'pick' to 'squash' for the commits you want to squash

// Update the commit message

// Push
git push
```