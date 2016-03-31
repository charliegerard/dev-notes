# Git commit --amend

If you realise you've commited something and want to edit the commit message or made some additional changes and want to add it to the most recent commit, you can use the command `git commit --amend`

If you do not have any staged changes, this will allow you to edit the commit message without altering the commit.
If you have some additional staged changes, this command will replace the most recent commit with the combination of your staged changes + commited ones.
