# READMEs

At the top level of each project, include a README file describing the project in terms a new user or contributor can understand.

## Describe the purpose of the project.

Give a brief summary of the project's purpose. Too often, developers neglect to include a project description in the README, infecting users with fear, uncertainty, and doubt. The treatment is a few, plain English sentences.

Example:

```
# vcdetect - detect which version control software manages a file path

vcdetect identifies which version control program, if any, is managing a project directory.

Assumes version control data is stored on the file system in plain, unambiguous, per-project fashion. This precludes the ability to detect arcane and offbeat version control software such as cvsnt, svk, and vss.
```

## Demonstrate example usages.

Show new users how to use your project. Command line programs should include a few example runs. Graphical programs should include a few screenshots.

Example:

```
# EXAMPLES

    $ vcdetect examples/larry/
    examples/larry/: hg
    
    $ vcdetect examples/moe/
    examples/moe/: svn
    
    $ vcdetect examples/curly/
    examples/curly/: cvs
    
    $ vcdetect examples/curly/README.md
    examples/curly/README.md: cvs
    
    $ vcdetect ~
    /Users/andrew: unknown
```

## Detail depedencies.

If your project depends on any other software packages or configuration, link to or include instructions for setting these up.

Example:

```
# REQUIREMENTS

* [Ruby](https://www.ruby-lang.org/) 1.9+
* [Guard](http://guardgem.org/)

Example:

    $ curl -s https://get.rvm.io | bash
    $ rvm install 2.0 && rvm use 2.0
    $ bundle install
```

## Detail build instructions.

Programming newbies may not know how to build, install, and run the project from source. Include basic instructions for a local build.

Example:

```
# BUILD

    $ mvn package
    $ rm -rf output/
    $ hadoop \
        jar \
        target/wordcount-0.0.0.jar \
        us.yellosoft.WordCount resources/ \
        output/
```

Keeping build documentation up to date also helps when configurint continuous integration; you will likely copy and paste the same steps into Jenkins or Travis CI.

## Use Markdown format.

READMEs and other documentation can be written in any text format, but Markdown represents a local maximum of several factors:

* Markdown can make clickable hyperlinks and show images, whereas `txt` files can only show plain text.
* Markdown is supported by many code hosts, including GitHub, GitLab, and BitBucket.
* Markdown is easier to learn than HTML.

http://daringfireball.net/projects/markdown/syntax

Modern code hosts automatically look for `README.md` files and render these as clickable HTML pages. Alternative formats such as Textile and reStructuredText are often supported, but Markdown is the premiere format that most open source projects tend to use.