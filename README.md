# Jekyll Step By Step

Me following through the step-by-step quickstart guide found here: <https://jekyllrb.com/docs/step-by-step/01-setup/>.

## Getting Jekyll Installed on Debian

Fun fact: running `sudo apt install ruby gem` doesn't work because the `ruby` package doesn't include the Ruby development kit. Instead you have to run:

    sudo apt install ruby-dev gem

Then you need Jekyll and bundle

    sudo gem install jekyll bundle

where `bundle` allows you to add dependencies to the site (including Jekyll itself, which isn't necessary but ensures you have a consistent version).

## Creating the Repo From Scratch

These are the instructions for starting with an empty directory. There's also a quick project builder described below. To get bundle working you need to run:

    bundle init

Then you add the following to the created Gemfile

    gem "jekyll"

Then it should be possible to run the following to build the site:

    bundle exec jekyll build

Or, to use the site-wide installed version rather than the bundled version:

    jekyll build

## Doing It Quickly With the Built-In Jekyll Script

    jekyll new myblog

This creates a new directory called `myblog` with the following files and directories:

- 404.html
- about.markdown
- config.yml
- Gemfile
- Gemfile.lock
- index.markdown
- _posts

## Running it

To just build:  

    jekyll build

To build and run it locally:

    jekyll serve

Note that when the server running, it will automatically rebuild whenever you make a change to the directory, so no need to restart.

Even better, pass the `--livereload` option and the browser itself will refresh whenever there's a change!

    jekyll server --livereload
