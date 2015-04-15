# Elementary rules and usage

## Use present tense.

A commit is like a book, timeless. As long as The Hobbit is in a library, the ring is always being picked up by Bilbo. As long as a commit is in a log, the semicolon is always being appended to the Java statement. Commits should be written in present tense, or command form in English.

Bad:

> fixed syntax, added semicolons to statements

Better:

> fix syntax by adding semicolons to statements

In a small project where each commit is essentially set in stone, past vs. present tense may seem a subjective, purely stylistic preference. After all, each commit was once applied to the codebase.

However, as a project grows, commits may need to be picked and pruned. When someone reverts a commit, or merges a branch, or cherry picks specific commits, it's helpful to treat commits as actions that can be performed, or not performed, or undone. This adds clarity to the version control workflow.

## Preserve context.

A little context goes a long way. Code reviewers want to know why a patch should be accepted. Future contributors want to know why ByteString substitutes for String. If you don't say why you committed a change, people might mistakenly revert it!

Bad:

> fixed it

Better:

> fix issue #7

When you commit, you can either illuminate your open source project, or you can leave everyone in the dark, concealing your true intentions. If you follow the Jedi order, Clarity is a powerful Force spell. The Sith order's counterspell is Obfuscation. If you've been pushing secretive Sith commit messages, you may want to revisit the light side.

You can bring balance to the Force