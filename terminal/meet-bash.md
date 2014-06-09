# Meet Bash

Ok, now that you have your Terminal window looking nice, the fun really starts as we get to know what is inside.

Meet Bash. Terminal is the app that runs Bash on your computer. What is Bash?

> ... an acronym for the ‘Bourne-Again SHell’, a pun on Stephen Bourne, the author of the direct ancestor of the current Unix shell

That's not very useful, but it is interesting. What you really need to know is that when you are looking up more information on how to do things in Terminal, you will more then likely find references to this thing called Bash. Don't get confused as the answer you are looking for is most likely there.

Also, keep in mind that Bash is a fully featured environment that is able to run applications and completely interact with it's host OS. This is extremely powerful and maybe you are seeing why developers prefer this.

But pay that no mind at this point. For our purposes, we are going to only go as far as the features that we need to understand.


### .bashrc, .bash_profile

Probably one of the more confusing things of working with Terminal and Bash is how they are configured. Bash uses two (dot) files that are located in your computer's home directory. They are `.bashrc` and `.bash_profile`.

BTW, a (dot) file is any file in the computer's file system where the name's first character is a dot. As in `.bashrc`. The service this provides is that the file is hidden from normal view.

OSX keeps you from being able to rename a folder or file in the standard GUI for this reason. But ... we can do this from Bash.

> **.bash_profile** : read and the commands in it executed by Bash every time you log in to the system

> **.bashrc** : read and executed by Bash every time you start a subshell

When using these files, there are some actions best suited for the `.bashrc` and others in the `.bash_profile`. Keeping this straight can drive you a little crazy.

Luckily, there is a way that makes this all easy to manage. Simply put all your stuff in the `.bash_profile` file. In order to get this to work, the two files need to be linked, we do this through what is called sourcing. By placing the following code in your `.bash_profile`, as Terminal loads the `.bash_profile` it will also loop in the `.bashrc` file.

```
if [ -f ~/.bashrc ]; then
  source ~/.bashrc
fi
```

Ok, at this time we will just let that sit there. At this point we haven't discussed how to find files in Terminal or how to open and edit files either. Further down this tutorial I will illustrate how to edit the content of these files from within the Terminal.
