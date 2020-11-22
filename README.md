# Bash Script Examples
This is a project to demonstrate how to use bash with common commands, problems and solutions.

# Motivation

I like using bash, but always wanted to have a reference point for some of the common tasks, issues that I encounter so I decided it would be a good idea to create this project, not only for myself, but also for anyone interested in learning about bash.

# Prerequisites

You need to have bash shell on your operating system terminal (I believe on windows this can be achieved by using tools such as Putty or GitBash), but for me I've tested these scripts on CentOS and MacOS Catalina, but all the other *nix based OS's should suffice.

Check if you have the bash shell by typing into the terminal:

```console
$ cat /etc/shells
```

In my case the output looks like the following:

```console
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

NB: You can also verify your bash by inputting into the terminal:

```console
$ bash --version
```

Which will give output similar to the following:

```console
GNU bash, version 3.2.57(1)-release (x86_64-apple-darwin19)
Copyright (C) 2007 Free Software Foundation, Inc.
```

So, we can see that out shells contains bash, and path to the executable is */bin/bash*.

# Conventions

Scripts should be named with the extension that is used for the specific shell that you are using. In the case of the scripts that I'm writing they should work for multiple shells. The convention, however, is to write the extension of the shell script with the extension that the script is supposed to be executed with. For example:

`greeting.sh`  # sh shell script

`greeting.bash` # bash shell script

`greeting.ksh` # ksh shell script

... and so on. I'm undecided if I shall use purely `.bash` in these examples, as they should, as I already mentioned, work for multiple shells (it'slikely that I shall use the .sh extension in all the cases, but lets see how I feel).
