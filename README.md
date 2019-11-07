# USC CS Course Website Template

The course webiste uses the [Jekyll] static website generator to render its content. It works with the [receiver script](https://github.com/usc-cs/md_receiver) to compile and serve from the [http://bits.usc.edu](http://bits.usc.edu).

You can edit the course website by commiting to this repository. This repository uses [Post-Receive Hooks](https://help.github.com/articles/post-receive-hooks) to automatically push changes to the course account on [www-scf](http://www-scf.usc.edu/~csci104/).

You can easily use GitHub's [web-based editor](https://github.com/blog/905-edit-like-an-ace) to edit the website online. That is if you don't want to edit your files locally.

###Can We Discontinue the Use of Jekyll
It is understandable that not everybody would be comfortable using [Jekyll]. Therefore, if the teaching staff would like stop using this way to develop the website, they could simple stop using this repository and directly edit the files on `aludra`. It may be a good idea to remove the post-receive hook in this case so any changes to the repo don't override the website.

##Setting-up Website Development Environment
The server that sets the website up once a commit is made to the repository will use [Jekyll] to render the website. So, there is no real need to install [Jekyll] locally unless you wish to test things out before commiting to the repo.

To work on the website locally a using Jekyll, you need to:
####1. Setup Jekyll Development Environment
  1. Install [Ruby](http://www.ruby-lang.org/en/downloads/)

  1. Install [Ruby Gems](http://rubygems.org/)

  1. Install [Jekyll] using the following command:
```sh
gem install jekyll
```

  1. Install the latest version of [redcarpet](https://github.com/vmg/redcarpet) the Markdown to (X)HTML converter
```sh
gem install redcarpet
```

  1. Install [Pygments] for code syntax highlighting
```sh
pip install pygments
```

Note for system wide installs, you need to use `sudo` for these commands if you are on a linux system.

####2. Clone the Website Repository
```bash
git clone git@github.com:usc-csci104-spring2014/course_website.git
cd course_website
```

####3. Launch Jekyll
The easiest way to activly work with Jykell is to have the Jykell builder and web server watch the repository for any changes. You can achieve that by
```bash
jekyll build --watch
jekyll serve --watch
```

Then, point your web browser to [http://localhost:4000](http://localhost:4000) to see a live rendering of the website.

####Notes & Hints
#####Generating CSS for Syntax Highliting
You may need to update the css generating to perform syntax highliting for code blocks. To do that, you run [Pygments]
```sh
pygmentize -S default -f html > css/pygments.css
```


[Jekyll]: http://jekyllrb.com/ "Jekyll Blog Aware Static Website Generator"
[Pygments]: http://pygments.org/ "Python Pygments"
