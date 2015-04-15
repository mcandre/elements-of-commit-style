# Branching and Tagging

The larger the project, the more things tend to spiral into chaos. Branches and tags reign the chaos back in, keeping development in established lanes for branching and merging code changes.

## Establish a branch workflow.

There are myriad ways of branching and merging. Document how contributors should interact with branches, or adopt [Git Flow](http://nvie.com/posts/a-successful-git-branching-model/), the de facto standard for working with branches on git projects.

## Use feature branches.

For each feature, issue, or ticket, dedicate a specific branch; don't just work on trunk or master. In a large, many-developer, many-feature project, feature branches isolate changes, making features easier to test, maintain, deploy, and roll back. Feature branches are especially good for git users, as git branches are computationally inexpensive.

Name feature branches after the feature, issue, or ticket number. For example:

* issue-3 for adding Google authentication
* issue-8 for publishing to Hackage
* issue-122 for resolving Tom's Unicode error

When the feature/issue/ticket is resolved, merge the code into a more official branch such as `dev` for development, or `master` if you're using an *unstable master* branch workflow.

## Tag releases.

When a milestone has been reached, like a set of features and bugfixes implemented, create a version control tag. For example, engineers may want to compare code between versions to diagnose a bug. Tagging helps people later check out the code at a specific point in time, in terms of a given version number, to help answer these sorts of questions about a codebase.

Example:

```
$ echo '{ "version": "1.0" }' > version.json
$ git commit -am 'bump to v1.0'
$ git tag -a 'v1.0' -m 'v1.0'
$ git push --tags
```