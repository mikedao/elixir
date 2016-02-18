---
title: Dev Environment Setup
---

Before we can do programming, we need to make sure that our computers
are properly configured with a functional development environment. Let's
walk through this process now to make sure that we have what we need.

Here are the basics:

* A text editor. Devlopers need to work with text in a different way than
your average Microsoft Word user. We'll want a text editor that's designed
for software development.
* A system "terminal" for interacting with our computer from the command line.
Fortunately, Mac OS X already ships with one.
* HomeBrew -- This is a "package manager" for installing other developer-
related programs. You can think of it as an "App Store for nerds."
* Git (An application for handling "version control" of our software projects.
* The Elixir programming language.

### Terminal

The terminal is a textual interface to your computer. Before Graphical User
Interfaces were invented, this was the only way one could interact with a computer.

Nowadays, developers still prefer this interface due to its power, flexibility,
and speed.

A Terminal allows you to navigate around folders (called directories) and run programs.
For example, when we run `ruby`, we are running that program from the terminal.

To launch the terminal, open Spotlight using `Command-Spacebar`, type "terminal", then enter.

If this is all new for you, see [Terminal and Editor](https://github.com/turingschool/curriculum/blob/master/source/academy/workshops/terminal_and_editor.markdown)

### Text Editor

We recommend that you use [Atom](https://atom.io/).

#### Setting Up Terminal Access for Atom

One of the things you'll do frequently is open an entire folder (like when working on a project) in your text editor. Let's get that setup:

* Open Atom (`command-spacebar` for Spotlight, type in `Atom`, and hit enter).
* Click the `Atom` menu in the top left corner
* Click `Install Shell Commands`
* Return to your terminal and enter `which atom`. You should get back `/usr/local/bin/atom`
* Enter `atom .` to open your current directory in Atom.
* Experiment with creating a file in Atom and using `ls` in the terminal to see it. Try creating a file in the terminal with `touch` and see if it shows up in Atom.

### Homebrew

[Homebrew](http://brew.sh) is a package management system that makes it easy
to install hundreds of open source projects and compile them from source
for maximum performance on your machine.

Open the Terminal then run the homebrew installation script:

```shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

It will ask you for your password. This is the password to log in to your account on the computer.
It needs this because it installs its packages in a place that all users of this computer can access.

#### Verifying Homebrew

When it has completed the installation run `brew doctor` and it should tell you that everything is fine:

```shell
brew doctor
Your system is ready to brew.
```

#### Modifying your PATH

If you got a warning from Homebrew about your path, do the following:

```shell
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
```

Now run `brew doctor` again and the warning should be gone.

__Aside: `PATH`:__

Your `PATH` is a system configuration
property which tells your computer which places to look for underlying programs
when you want to run a command.

For example, when we type `ruby` at the command line to run a ruby program, our `PATH`
will help the system know where on the system to find ruby. By adding this directory
to our `PATH`, we're telling the system how to find the various applications we will
install using Homebrew

__Aside: `~/.bash_profile`__

When we use our terminal, we're actually using a program called a "Shell" to interact
with the underlying Operating System. Specifically, we're using a shell called [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)).

The file `~/.bash_profile` contains settings and commands to help us configure the shell,
so when we have a bit of configuration code such as setting our `PATH`, it often goes
in our `~/.bash_profile`.

### Git

[Git](http://git-scm.com/) is the version control system of choice in the Ruby community.
XCode installed an older version of Git for you, but let's update it.

```shell
brew install git
==> Downloading http://git-core.googlecode.com/files/git-1.8.3.4.tar.gz
########################################################### 100.0%
```

#### Configuring Git

If you haven't used git before (don't worry, we'll be covering its usage in future classes),
we'll want to configure it with some basic information about us.

We can tell git to configure itself using the `git config` command from our terminal.
Additionally, we're setting "global" configurations for git, so we'll use the `--global` flag
when we provide it with a new piece of configuration.

Tell git your Name and Email address by using the following commands, substituting your
own name and email:

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

### Elixir

Install Elixir by running this following command.

```shell
brew install elixir
```

It is highly recommended to add Elixir’s bin path to your PATH environment variable to ease development.

```shell
echo 'export PATH="$PATH:/path/to/elixir/bin"' >> ~/.bash_profile
source ~/.bash_profile
```

