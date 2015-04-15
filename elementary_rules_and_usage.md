# Elementary rules and usage

## Use present tense.

A commit is like a book, timeless. As long as The Hobbit is in a library, the ring is always being picked up by Bilbo. As long as a commit is in a log, the semicolon is always being appended to the Java statement. Commits should be written in present tense, or command form in English.

Bad:

> fixed syntax, added semicolons to statements

Better:

> fix syntax by adding semicolons to statements

In a small project, past vs. present tense may seem a subjective, purely stylistic preference. However, as a project grows, commits may need to be picked and pruned on branches. When someone reverts a commit, or merges a branch, or cherry picks specific commits, reading commits as actions that can be performed, or not performed, or undone, adds clarity to the version control workflow.