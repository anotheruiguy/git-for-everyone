# Playing with branches

So far through this demo we have been working on a single `master` branch. The `master` branch is simply a convention for stating what is the core branch of code that everyone should be committing to. Some don't use `master` and use conventions like `stable` and things along those lines.

So, how do we work with branches? Pretty simple really. The first thing we want to know what branches we have and what branch we are on:

```
$ git branch
```

You should see:

```
* master
```

And the word `master` should be highlighted. Great. This means that we have only one branch and that this is the one you are on. Let's make a new branch:

```
$ git checkout -b new-branch
```

What did we do here? `git checkout` is the command to checkout a branch, passing in the `-b` flag is to create and checkout a new branch, then `new-branch` is the name we passed in here. You can name a branch anything, but I suggest keeping is short so that it is easy to type as you will be switching branches a lot.

Ok, now let's see those branches again:

```
  master
* new-branch
```

Cool. We have two branches and since we used the `-b` flag when we created the branch, this also switched us to that new branch right away.
