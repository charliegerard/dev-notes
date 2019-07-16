# Remove file/folder permanently with git filter-branch

If you've committed a sensitive file or folder by default (credentials, API keys, etc...), you can remove it permanently from the git history with the following commands:

* 1:

```git filter-branch --tree-filter 'rm -rf <folder>' HEAD```

* 2:

```git gc```

* 3:

```git push --force-with-lease```