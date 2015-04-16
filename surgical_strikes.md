# Surgical Strikes

A version control system is a scalpel: precise and powerful, but useless when dirty. To get the most out of your version control system, you need to sterilize each commit. In a DVCS such as git, each commit should be sterilized before pushing to remote repositories.

## Sterilize your working directory.

Use `git status`, etc. to ensure your operating area is clean. If you have modifications, you may want to `git commit` or `git stash` them before continuing with other git operations.

## Synchronize local and remote repositories.

Decentralized version control systems such as git require constant, manual synchronization between local and remote repositories. If your local repo gets too out of date, you risk merge conflicts when you try to push new changes upstream. Push early, push often. (And pull early, pull often.)

## Commit only what you need.

Use `git status`, etc., to confirm which modifications might be included in a commit.

For example, split import statement reordering from logging improvements. Stage one of these as a commit dedicated to import statement reordering, and follow up with a second commit for logging improvements.

Example:

```
$ git add -p
...
$ git commit -m 'alphabetize imports'

$ git add -p
...
$ git commit -m 'log warnings'
```

## Rebase branches after releases.

A common problem: dev and issue-3 branches have fallen behind master since release v2.1. The next time dev and issue-3 attempt to merge to master, there could be merge conflicts, a messy situation. How can we improve this?

When a repository gets a new release, with a new set of master commits, other branches that will continue to be worked on should be cleaned up as if they had been developed from master.

One way to do this would be to delete the branches and do the coding work from scratch, but this is wasteful and hazardous to others attempting to use those branches.

A safer way to clean up these branches is to rebase them from master. This edits the history of those branches, placing the new master commits before the feature branch work, in a clean way.

```
 (master) $ git checkout dev
    (dev) $ git rebase master
    (dev) $ git push

    (dev) $ git checkout issue-3
(issue-3) $ git rebase master
(issue-3) $ git push
```

If there are no merge conflicts, this works very smoothly. On the other hand, merge conflicts may crop up. Better these be resolved early in the sprint work for a branch than later, towards release time.

## Squash related commits.

Several minor changes that constitute one logical code change, such as a few changes that together make a unit test pass, can be combined together into a single commit. Use `git rebase -i HEAD~<n>` to edit the last n commits.

```
$ git rebase -i HEAD~3
pick c0a5ae55 balance parentheses
squash acaca4ed correct off-by-one error
squash 866a527d fix broken unit test ArithmeticTest
...
```

This ensures other developers, and continuous integration, will only see a single passing commit rather than several failing commits.

Rebasing can do other powerful edits to the commit history, including deleting commits, and splitting commits into several commits. See [Pro Git](http://git-scm.com/book/en/v2/Git-Branching-Rebasing) for more information.

While developing a feature, it's useful to keep commits separate / unsquashed, and merge them as a squashed commit into more integrated branches like master or develop. Use `git merge --squash` to do this.