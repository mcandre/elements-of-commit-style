# READMEs

At the top level of each project, include a README file describing the project in terms a new user or contributor can understand.

## Describe the purpose of the project.

Give a brief summary of the project's purpose.

Example README:

```
# vcdetect - detect which version control software manages a file path

vcdetect identifies which version control program, if any, is managing a project directory.

Assumes version control data is stored on the file system in plain, unambiguous, per-project fashion. This precludes the ability to detect arcane and offbeat version control software such as cvsnt, svk, and vss.
```

Many repositories, especially corporate subsystems, neglect to include a project description, at the expense of contributions from new and unfamiliar developers.

## Demonstrate example usages.

Show new users how to use your project. Command line programs should include a few example runs. Graphical programs should include a few screenshots.

Example README:

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

Example README:

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

Example README:

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