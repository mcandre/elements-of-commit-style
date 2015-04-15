# Excluding file paths

## Exclude executables and other by-products

Use `.gitignore`, etc. to keep machine code and other large, computer generated files out of version control. This keeps version control operations fast, and communicates which files contributors are responsible for hand-writing and which files are by-products of the hand-written files.

Basic `.gitignore` for a Java/Maven project:

```
target/
*.class
*.jar
```

When in doubt, use [gitignore.io](https://www.gitignore.io/) to quickly get a list of file paths to exclude. To remove all traces of a large file, use the BFG:

https://rtyley.github.io/bfg-repo-cleaner/

Not all binaries should be excluded. Reasonable exceptions include media files such as images, audio, and video; test data; and machine learning data; that may be important resources for your project.

## Exclude operating system junk files

Don't let folder thumbnails and other constantly changing junk files creep into version control.

Basic `.gitignore` for a Windows/Mac OS X project:

```
Thumbs.db
.DS_Store
```

## Exclude text-editor metadata

Emacs, Vim, SublimeText, IntelliJ, and many other text editors produce cache files by default, for temporarily managing project file backups. In a version controlled project, these files are largely redundant, and should not be checked into version control.

Basic `.gitignore` for a project with many contributors and text editors:

```
*~
*.swp
*.sublime-workspace
*.iml
```