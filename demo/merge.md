# The merge

Getting your branched code merged into `master` is not a magical process, it's pretty simple really. What do we know? We know that we have a version of code on `master` and that we have more code in a brach called `new-branch`. It is the new code that we want merged into `master. To get started, let's checkout `master`:

```
$ git checkout master
```

Ok, now we want to merge, but let's do a little check first. We can do a quick check to see what branches are merged and not merged into `master`

```
$ git branch --merged
```

At this point, we should only see the `master` branched listed. So then run this:

```
$ git branch --no-merged
```

This should return the `new-branch` in the list. Ok, let's merge these two. BUT, we need pass in the `--no-ff` flag. What does this do?

The `--no-ff` flag prevents `git merge` from executing a "fast-forward" if it detects that your current HEAD is an ancestor of the commit you're trying to merge. A fast-forward is when, instead of constructing a merge commit, git just moves your branch pointer to point at the incoming commit.

Occasionally you want to prevent this behavior from happening, typically because you want to maintain a specific branch topology (e.g. you're merging in a topic branch and you want to ensure it looks that way when reading history). In order to do that, you can pass the `--no-ff` flag and `git merge` will always construct a merge instead of fast-forwarding.

```
$ git merge new-branch --no-ff
```

Ok, but this may have just got weird and will freak you out.

![image](http://i.imgur.com/bt7ja6S.png)

You may be seeing something like this:

```
Merge branch 'new-branch'

# Please enter a commit message to explain why this merge is necessary,
# especially if it merges an updated upstream into a topic branch.
#
# Lines starting with '#' will be ignored, and an empty message aborts
# the commit.
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
".git/MERGE_MSG" 7L, 253C
```

Nothing to worry about there. Remember what I said about the `--no-ff` flag? It's a merge. But when we made this merge, we didn't add a commit message. This is Git telling us that we didn't leave a commit message and it's asking us for one now.

If we don't leave a message, then Git will insert one for us. So, do the following:

```
:wq
```

Weird, but trust me. Now you should see the following:

```
Merge made by the 'recursive' strategy.
 index.html          | 2 ++
 stylesheets/app.css | 4 ++++
 2 files changed, 6 insertions(+)
```

Here is your confirmation that `index.html` and `app.css` added some code to the `master` branch.

Just to confirm that everything is all merged up, run this:

```
$ git branch --merged
```

You should see both our branches in this list.

### The before and after

That's it, we are all merged up. Here is what our repo looked like before we merged

![image](http://i.imgur.com/X783GF8.png)

And here it is after

![image](http://i.imgur.com/GqugLd0.png)

You may notice the out branch that we created when we created our feature branch and then it links back into the `master` branch. This is EXACTLY what we are looking for. This is the merge technique we want when using the `--no-ff` flag. If we had not used that technique, we would see a single branch of code and that can be misleading when we are reviewing our project history.
