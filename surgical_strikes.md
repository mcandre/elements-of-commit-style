# Surgical Strikes

A version control systems is a scalpel: powerful, but must be kept clean. To get the most out of your version control system, you need to sterilize each commit. In a DVCS such as git, each commit should be sterilized before pushing to remote repositories.

## Commit only what you need.

Use `git status`, `svn status`, etc., to confirm which modifications might be included in a commit.

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