# Elementary rules and usage

## Preserve context.

A little context goes a long way. The more people read your code, the more they want to know why you make each change. If you don't say why you committed a change, people might mistakenly revert it!

Bad:

> use ByteString

Better:

> use ByteString for optimization

When you commit, you can choose to illuminate your open source project, or you can leave everyone in the dark, concealing your true intentions. If you follow the Jedi order, Clarity is a powerful Force spell. The Sith order's counterspell is Obfuscation. If you've been pushing secretive Sith commit messages, you may want to revisit the light side.

## Encourage linking.

"Google it" is helpful advice for general tech problems. For more specific conversations, providing links to relevant tools and tickets helps everyone out.

Bad:

> tune up code

Better:

> tune up code with jshint

Better still:

> per issue #4, tune up code with jshint. http://jshint.com/
>
> in particular, https://jslinterrors.com/the-array-literal-notation-is-preferrable

The more you link, the less people have to page you for answers. And, ironically, linking makes Googling work better as well.

## Use present tense.

A commit is like a book, timeless. As long as The Hobbit is in a library, the ring is always being picked up by Bilbo. As long as a commit is in a log, the semicolon is always being appended to the Java statement. Commits should be written in present tense, or command form in English.

Bad:

> fixed syntax, added semicolons to statements

Better:

> fix syntax by adding semicolons to statements

In a small project where each commit is essentially set in stone, past vs. present tense may seem a subjective, purely stylistic preference. After all, each commit was once applied to the codebase.

However, as a project grows, commits may need to be picked and pruned. When someone reverts a commit, or merges a branch, or cherry picks specific commits, it's helpful to treat commits as actions that can be performed, or not performed, or undone. This adds clarity to the version control workflow.