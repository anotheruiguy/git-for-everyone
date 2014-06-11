# The files

Now that we have a dir that is a properly formatted Git repo, let's create a few new files for a demo web app that we can being to add to version control.

First, let's add the `index.html` file:

```
$ touch index.html
```

Great. But we need some more stuff for our demo web app. We need our primary CSS and Js files too. To do this we need to create the proper dir for each:

```
$ mkdir stylesheets
$ mkdir javascripts
```

Using the `cd` command, we need to change directory into each dir and add a `app.js` and a `app.css` file:

```
$ cd stylesheets && touch app.css && cd ../
$ cd javascripts && touch app.js && cd ../
```

What's up with those commands? It's simple really, in Terminal you can string together commands using the `&&` operator. If you were to take this apart:

1. Change directory into `stylesheets/`
1. Create the new `app.css` file
1. Change directory back up a level to where we started from

Pretty cool, huh?

Now that we have that set up, run the `status` command again and you should see the following:

```
# On branch master
#
# Initial commit
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
# index.html
# javascripts/
# stylesheets/
nothing added to commit but untracked files present (use "git add" to track)
```

GREAT! Ok, we are still on the `master` branch, nothing is ready to commit, but we have new `Untracked files` in the output. Take note that we have files in the `javascripts/` and `stylesheets/` dirs but they are not listed out? This is because when you add a new dir and create new files, unless you tell Git not to, it will simply gobble up all the files in the dir, so there is no need to list them individually.

**Interesting experiment:** Let's create a new dir and NOT put anything inside it and then run the `status` command again:

```
$ mkdir foo
$ git status
```

What's this? The new dir `foo` is not in the output? That's weird? No, it's not really. Git tracks files, not directories. So, if you create a directory and don't put in any files, even if they are empty files, Git will pass on the empty dir all together.

Ok, let's remove that `foo` dir:

```
$ rm -rf foo
```
