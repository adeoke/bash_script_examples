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

# Basic information

By default scripts are not executable. Users and groups in the operating system should be enabled to read the scrips by default. However, they wont be able to execute them, and executing scripts is our goal.

You can check the permissions of each script by changing into the directory and listing all the files and then examining the permission for each file. For example, lets examine the permissions of the README.md file in this directory:

```console
$ ls -al

drwxr-xr-x    5 myusername  staff   160 22 Nov 18:53 .
drwx------+ 223 myusername  staff  7136 22 Nov 18:53 ..
drwxr-xr-x   13 myusername  staff   416 22 Nov 19:28 .git
-rw-r--r--    1 myusername  staff  1064 22 Nov 18:53 LICENSE
-rw-r--r--    1 myusername  staff  2077 22 Nov 19:29 README.md
```

In this case we can see the `README.md` permissions are `-rw-r--r--`.

The first hyphen is used to indicate if the item is a file or a directory, `d` indicates a directory (in the above output we can see that `.git` is a directory), but for README.md it has a hyphen, which means it's NOT a directory.

The next three chars represent the current users permissions for the particular item: `rw-`, which means the user can read and write the file only.

The next three chars after that represents the items group permissions
`r--`, which in this case is read only.

Finally, the last three characters after that represents all other users permissions, again in this case is
`r--`, and so again only read  permissions for `all other` users.


In order to make the file runnable we need to change the permissions for the item.
A simple way to do this is with the chmod command.

in the terminal if you input `chmod a+x particular_file.sh` (replacing particular_file.sh with your desired file) then you will enable execute permission for the file for the the current user, the group that user belongs to and all other users as well. At this point you are ready to get started with running the script.
