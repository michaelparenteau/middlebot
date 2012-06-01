## middlebot

middlebot is a project that I created to generate a new [middleman](http://middlemanapp.com) app with the structure and naming I wanted rather than the default. Also, I wanted to install git, have the option to make a public github repo & have the option to make a heroku app -- all in one command.

## Included in the Repo

### The Middleman Template
* use .haml files intsead of .erb
* use bundler
* use rack
* include Heroku gem in Gemfile
* specify Ruby version in Gemfile (this requires bundler --pre version
  and is necessary for heroku to use Ruby 1.9.3)
* use screen.scss instead of site.scss
* add compass/css3 & compass/reset to screen.scss

### mirb -- _WTF?_

mirb is a bash script. mirb is the brains of middlebot. Running mirb will:

* create a middleman install form the above template
* create a .gitignore file
* create a README.md file
* install git
* add and commit to git
* Ask if you want to create github repo."yes" will: 
  * prompt you for your username/password
  * create remote repo
  * add remote to .git/config
  * git push
* Ask if you want to create a heroku repo. "yes" will: 
  * prompt you for your username/password
  * create heroku app with the project name
  * deploy to heroku

## Usage

You will need to have the following dependencies installed on your machine:

* Ruby & Rubygems
* RVM
* Middleman
* git

If all of the above are installed, you will need to add the .middleman folder to your home directory.

If you cloned this repo, you may:

    cp -r middlebot/.middleman ~/.middleman

You will then need to have mirb on your path and executable. I use a bin directory. If you cloned the repo you may:

    mkdir ~/bin && echo "export PATH=$PATH:$HOME/bin" >> ~/.bash_profile && source ~/.bash_profile
    cp middlebot/mirb ~/bin/mirb && chmod +x ~/bin/mirb

The first command makes the bin folder and adds it to your path. The second command copies the mirb script to you bin folder and makes it executable.

After you have the template in place and the bash script ready to run,
you may cd into your project folder and run:

     mirb [project name]

Enjoy!

## Important Notes

* You will need a github account & heroku account to create those repos with mirb
* There is no failsafe around trying to create repos on github or heroku with names that already exist. You would need to pick up manually from where mirb left off when it failed.

## mirb is open source

**The MIT License (MIT)**

Copyright (c) 2012 Michael Parenteau

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
