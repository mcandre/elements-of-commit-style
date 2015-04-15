# Including and Excluding files

Think critically about which files you check into version control, and which files you exclude.

## Include small and hand-written files

Anything hand-written that would take time to recreate is a good candidate for checking into version control. 
Example check-in files:

```
src/
  main/
    java/
      us/
        yellosoft/
          HelloHadoop.java
    resources/
      the-complete-works-of-sir-arthor-conan-doyle.txt
  test/
    java/
    resources/
      the-hound-of-the-baskervilles.txt
```

Some binaries should be excluded, but reasonable exceptions include media files such as images, audio, and video; test data; and machine learning data; that may be important resources for your project.

Medium-to-large files that are important resources, but are considered too big for version control, can be kept in online data storage, as long as instructions for obtaining them are clearly indicated in version controlled-documentation.

## Exclude executables and other by-products

Anything computer-built from hand-written files should be excluded from version control. Use `.gitignore`, etc. to keep machine code and other large, computer generated files out of version control.

This keeps version control operations fast, and communicates the project structure to contributors, signalling which files contributors are responsible for hand-writing and which files are by-products of the hand-written files.

Basic `.gitignore` for a Java/Maven project:

```
target/
*.class
*.jar
```

When in doubt, use [gitignore.io](https://www.gitignore.io/) to quickly get a list of file paths to exclude. To remove all traces of a large file, use the BFG:

https://rtyley.github.io/bfg-repo-cleaner/

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