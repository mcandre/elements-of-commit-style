# Branching

The larger the project, the more things tend to spiral into chaos. Branches reign the chaos back in, keeping development in established lanes for branching and merging code changes.

## Use feature branches.

For each feature, issue, or ticket, dedicate a specific branch; don't just work on trunk or master. In a large, many-developer, many-feature project, feature branches isolate changes, making features easier to test, maintain, deploy, and roll back. Feature branches are especially good for git users, as git branches are computationally inexpensive.

Name feature branches after the feature, issue, or ticket number. For example:

* issue-3 for adding Google authentication
* issue-8 for publishing to Hackage
* issue-122 for resolving Tom's Unicode error

When the feature/issue/ticket is resolved, merge the code into a more official branch such as `dev` for development, or `master` if you're using an *unstable master* branch workflow.

## Establish a branch workflow.

There are myriad ways of branching and merging. Document how contributors should interact with branches, or adopt [Git Flow](http://nvie.com/posts/a-successful-git-branching-model/), the de facto standard for working with branches on git projects.