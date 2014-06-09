# Shortcuts using aliases

There are some steps in there that we should just be doing all the time. What about making a single command alias that will cycle through all these commands just so we know things are always in good shape? Yup, we can do that.

## In Bash

Using Git and Bash is like using a zipper and pants. They just go together. Creating a Bash alias is extremely simple. From your Terminal, enter

```
$ open ~/.bash_profile
```

This will open a hidden file in a default text editor. If you have a shortcut command for opening in an editor like Sublime Text, use that to open the file. In the file add the following:

```
alias refresh="git checkout master && dskil && git pull && git fetch -p"
```

The alias `dskil` is useful for removing annoying `.DS_Store` files. You should have a `.gitignore` file that keeps these out of version control, but I like to keep a clean house too. To make that work, add the following:

```
alias dskil="find . -name '*.DS_Store' -type f -delete"
```

With this in your `.bash_profile`, you simply need to enter `refresh` in the command line and POW!

## In Powershell

If you are on Windows and using Powershell, you can use the same aliases, but the set up is different. The article [Windows PowerShell Aliases](http://www.powershellpro.com/powershell-tutorial-introduction/tutorial-powershell-aliases/) is a good tutorial of the process.
