# Open and edit files using VI
Ok, gonna get a little rough here, but I am sure you can do it. Let's add some color to your Terminal experience. To do this, we need to add some code to your `.bash_profile`. The trick here is that it's difficult to open hidden files using most editors that rely on a typical finder. UNIX comes with a text editor called VI built in that you can access from the Terminal.

To get started, make sure that you are in your home directory:

```
$ cd ~
```

Now, open the file in VI:

```
$ vi .bash_profile
```

In your Terminal, you will have open this file in VI mode, so things are a little different. In order to add content, you need to hit the `i` key. This open the `-- INSERT --` mode and add the following:

```
export CLICOLOR=1
export LSCLOLOLORS=GxFxCxDxBxegedabagaced
```

![image](http://i.imgur.com/DwqHxrg.png)

To save these edits, hit the `esc` key. To exit VI mode, type `:wq`. I know, all a little weird, but that's how it works. Welcome to VI.

Ok, for the fun part. If you do a `ls -p` here, there will be no change. To get updated to the `.bash_profile` to take effect, you have to do what is called 'sourcing'. To do this, run:

```
$ source ~/.bash_profile
```

Now, enter `ls -p` and your directories will be a different color from your files.

![image](http://i.imgur.com/hMIApeO.png)
