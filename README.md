# voku’s dotfiles

![Screenshot of my shell prompt](http://suckup.de/wp-content/uploads/2014/06/bash_prompt.png)

## Installation

### Using Git and the bootstrap script

You can clone the repository wherever you want. (I like to keep it in `~/Projects/dotfiles`, with `~/dotfiles` as a symlink.) The bootstrapper script will pull in the latest version and copy the files to your home folder.

```bash
cd ~ && git clone https://github.com/voku/dotfiles.git && cd dotfiles && source bootstrap.sh
```

To update, `cd` into your local `dotfiles` repository and then:

```bash
git pull
./bootstrap.sh
```

### Add custom commands without creating a new fork

If `~/.config_dotfiles` does not exists, the "bootstrap.sh"-script will create a default config for you.

My `~/.config_dotfiles` looks something like this:

```bash
#!/bin/bash

CONFIG_DEFAULT_USER="lars"
CONFIG_TMUX=false
CONFIG_OH_MY_ZSH_PLUGINS="(git bower composer)"
CONFIG_CHARSET_UTF8=true
CONFIG_LANG="de_DE"
```

If `~/.extra` exists, it will be sourced along with the other files. You can use this to add a few custom commands without the need to fork this entire repository, or to add commands you don’t want to commit to a public repository.

My `~/.extra` looks something like this:

```bash
#!/bin/bash
GIT_AUTHOR_NAME="Lars Moelleken"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="lars@moelleken.org"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
git config --global user.email "$GIT_AUTHOR_EMAIL"
git config --global push.default simple

# java - example
export JAVA_HOME=/usr/lib/jvm/java-7-oracle
export JDK_HOME=$JAVA_HOME
export JRE_HOME=$JAVA_HOME
export PATH=$JAVA_HOME/bin:$PATH

# android - example
export ANDROID_SDK_ROOT=/usr/local/android-sdk/
#export ANDROID_NDK=/usr/local/android-ndk/
export ANDROID_HOME=$ANDROID_SDK_ROOT
export PATH=$ANDROID_SDK_ROOT/tools/:$ANDROID_SDK_ROOT/platform-tools/:$ANDROID_SDK_ROOT/build-tools/19.1.0/:$PATH
```

You could also use `~/.extra` to override settings, functions and aliases from my dotfiles repository. It’s probably better to [fork this repository](https://github.com/voku/dotfiles/fork) instead, though.

```bash
```

### Install needed packages

When setting up a new Debian, you may want to install some extra packages:

```bash
bash ~/dotfiles/.firstInstall.sh
```

## Feedback

Suggestions/improvements
[welcome](https://github.com/voku/dotfiles/issues)!

## Thanks to…

* [DrVanScott](https://github.com/DrVanScott/dotfiles/)
* [TuxCoder](https://github.com/TuxCoder/dotfiles/)
* [Mathias Bynens](https://github.com/mathiasbynens/dotfiles/)
* [@ptb and his _OS X Lion Setup_ repository](https://github.com/ptb/Mac-OS-X-Lion-Setup)
* [Ben Alman](http://benalman.com/) and his [dotfiles repository](https://github.com/cowboy/dotfiles)
* [Chris Gerke](http://www.randomsquared.com/) and his [tutorial on creating an OS X SOE master image](http://chris-gerke.blogspot.com/2012/04/mac-osx-soe-master-image-day-7.html) + [_Insta_ repository](https://github.com/cgerke/Insta)
* [Cãtãlin Mariş](https://github.com/alrra) and his [dotfiles repository](https://github.com/alrra/dotfiles)
* [Gianni Chiappetta](http://gf3.ca/) for sharing his [amazing collection of dotfiles](https://github.com/gf3/dotfiles)
* [Jan Moesen](http://jan.moesen.nu/) and his [ancient `.bash_profile`](https://gist.github.com/1156154) + [shiny _tilde_ repository](https://github.com/janmoesen/tilde)
* [Lauri ‘Lri’ Ranta](http://lri.me/) for sharing [loads of hidden preferences](http://osxnotes.net/defaults.html)
* [Matijs Brinkhuis](http://hotfusion.nl/) and his [dotfiles repository](https://github.com/matijs/dotfiles)
* [Nicolas Gallagher](http://nicolasgallagher.com/) and his [dotfiles repository](https://github.com/necolas/dotfiles)
* [Sindre Sorhus](http://sindresorhus.com/)
* [Tom Ryder](http://blog.sanctum.geek.nz/) and his [dotfiles repository](https://github.com/tejr/dotfiles)
* [Kevin Suttle](http://kevinsuttle.com/) and his [dotfiles repository](https://github.com/kevinSuttle/dotfiles) and [OSXDefaults project](https://github.com/kevinSuttle/OSXDefaults), which aims to provide better documentation for [`~/.osx`](http://mths.be/osx)
* [Haralan Dobrev](http://hkdobrev.com/)

* anyone who [contributed a patch](https://github.com/voku/dotfiles/contributors) or [made a helpful suggestion](https://github.com/mathiasbynens/dotfiles/issues)
