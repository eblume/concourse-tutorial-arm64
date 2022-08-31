# Concourse tutorial

arm64 variant
-------------

This specific fork of starkandwayne/concourse-tutorial provides an alternate docker compose file which uses arm64 builds
provided by [robinhuiser/concourse-arm64](https://github.com/robinhuiser/concourse-arm64), which allows the Stark &
Wayne tutorial to work on arm64 architectures such as the m-series of Apple computers. Some changes were made to the
course's source, which include but are not limited to:

* Using a different built image of concourse as mentioned above
* Switching all instances of the `docker-image` resource to `repository-image`
* Altering some of the startup options for concourse
* Providing a .tool-versions file for use with the [asdf-concourse](https://github.com/mattysweeps/asdf-concourse)
    plugin.

I don't plan on putting any effort on keeping this fork up to date with upstream, but if you are reading this and wish I
had done so, please file an issue on this project and I will probably be able to take a look at it. If it garners much
interest, I could adopt the project more extensively and contribute patches back upstream to help the main tutorial.

**Please note - some of the instructions in the tutorial will not be exactly compatible with these changes.** In
particular, any reference to Stark & Wayne's repos will need to be redirected to this repo.

Finally, rather than following the tutorial's instructions on installing `fly`, I suggest using asdf-concourse. Assuming
you have asdf installed (perhaps `brew install asdf`), just run this::

    asdf plugin add concourse https://github.com/mattysweeps/asdf-concourse
    asdf install  # Run in this repo's base directory
    concourse --version
    fly --version


Original text
-------------

Learn to use https://concourse-ci.org with this linear sequence of tutorials. Learn each concept that builds on the previous concept.

Read the tutorial at https://concoursetutorial.com

## Thanks

Thanks to Alex Suraci for inventing Concourse CI, and to Pivotal and VMWare for sponsoring him and a team of developers to work since 2014.

At Stark & Wayne we started this tutorial as we were learning Concourse in early 2015, and we've been using Concourse in production since mid-2015 internally and at nearly all client projects.

Thanks to everyone who has worked through this tutorial and found it useful. I love learning that you're enjoying the tutorial and enjoying Concourse.

Thanks for all the pull requests to help fix regressions with some Concourse versions that came out with "backwards incompatible change".

## Getting Started

Read the tutorial at https://concoursetutorial.com

## Local development of tutorial

This tutorial is built using [`mkdocs`](http://www.mkdocs.org/). Please make sure you have python3 and pip3 installed before running mkdocs and they are refenced as python and pip respectively. . Once installed, you can continuously build and serve the tutorial locally with:

```plain
mkdocs serve
```

View the site and live changes at https://localhost:8000.

