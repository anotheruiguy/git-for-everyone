# The folder

On your `/Desktop` let's create a folder and call it `gitDemo`. The following steps will make sure that you are on the Desktop of your computer, make a new directory and change into that directory.

```
$ cd ~/Desktop
$ mkdir gitDemo
$ cd gitDemo/
```

Now that we have the folder we can make this into a Git repository. Any directory at any level can be made into a Git repository (or repo for short). If at any point you are unaware of the status of the repo:

```
$ git status
```

Running the `status` command inside the `gitDemo/` dir should produce the following:

```
fatal: Not a git repository (or any of the parent directories): .git
```

This simply means that this dir is not a properly set up Git repo. To make this a repo, simply run the following command:

```
$ git init
```

Running this command you should see something similar to the following:

```
Initialized empty Git repository in /Users/<username>/Desktop/gitDemo/.git/
```

Running the `status` command here will now produce a completely different response:

```
# On branch master
#
# Initial commit
#
nothing to commit (create/copy files and use "git add" to track)
```

That is a little bit of a mouthful, but nothing to be concerned with. Simply, what this means is, you are on the `master` branch and there is nothing yet to commit.
