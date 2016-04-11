# How to find which commit introduced a bug

When you realise a bug has been introduced somewhere in your app but you don't know how long it has been there for and/or in which part of the code it was actually written, you can use the command `git bisect`.

`git bisect` is a tool that helps you find the commit that introduced a bug. You'll need to find a commit where the code works and a commit where it doesn't.
From there, you start `git bisect` like this:

```
#start up git bisect
git bisect start

#give a commit where the code works
git bisect good a1b2c3

#and another commit where it doesn't anymore
git bisect bad d4e5f6
```

When you start this, it will start splitting the revisions, loading them up and asking you if the commit is good or bad.
You will need to answer either `git bisect bad` or `git bisect good` depending if the commit loaded contains the bug or not.
It will execute a binary search to help you narrow down the commit you're looking for.

You can also automate the process by executing a script against each revision that is loaded.

To do so:

```
#Do the same steps as above
git bisect start
git bisect good a1b2c3
git bisect bad d4e5f6

# command to run against each commit
git bisect run rspec spec/my_test.rb
```
