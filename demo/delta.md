# The delta

These next steps will demonstrate how we can make some edits in this branch, commit them and then switch to see the delta between the branches.

First, let's update some code in the `index.html` file. Open this up in your favorite text editor and add the following code:

```html
<p>goodnight moon</p>
```

Cool. Now open the `app.css` file and add the following:

```css
p {
  font-size: 2em;
}
```

Cool, now we have a diff between what was originally in this branch and what we edited. Here there are a couple of things we can do, bit for now let's get out status:

```
$ git status
```

And we should see:

```
# On branch new-branch
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
# modified:   index.html
# modified:   stylesheets/app.css
#
no changes added to commit (use "git add" and/or "git commit -a")
```

Ok, the next thing we want to do is commit these changes to THIS branch and switch back to the `master` branch:

```
$ git add .
$ git commit -m "update content and styles"
```

Doing a `git status` here we will see that there is nothing to commit and the working directory is clean. Cool! Now, let's switch back to the `master` branch:

```
$ git checkout master
```

Great. Now open the `index.html` and `app.css` files. The code we just added and committed are GONE!!!! Ok, don't panic, it's not really gone, it's just on the other branch. Let's switch back to make sure.

```
$ git checkout new-branch
```

Blamo! All the code should be back. But, we need that code in `master`?
