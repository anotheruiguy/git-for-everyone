# The content

At this phase we have the dir, it's a repo and it has folders and files. Great. Now to add some content. Open each file and add the following:

**HTML**
```html
<h1>Hello World</h1>
```

**CSS**
```css
h1 {
  font-size: 8em;
}
```

**JavaScript**
```javascript
var today = new Date()
```

Looking good. Having done this, let's look at our `status` again. Anything different? Nope. While Git does track every single turned bit in these documents, it does not display this in the `status` output.

It's time to get things tracking, so let's use the `add` function and then append a statement to this `commit`:

```
$ git add .
```

Whoa, wait right there. Check the `status` now, you should see something like the following:

```
# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
# new file:   index.html
# new file:   javascripts/js.css
# new file:   stylesheets/app.css
#
```

What does `unstage` mean? And if everything is working correctly the new files should be `yellow`. What this means is that when we ran the `git add .` command, this updated the status of all the files in that directory to be `staged`. This means that the edits you have added are not yet committed to the repo.

If you were to try and push code or switch branches at this time, these changes would not do what you expect them to do. In order to commit these changes to the branch, we need to run the `commit` command.

There are a few parts of this we should talk about. There is the `commit` command that initiates the function and then there is the `-m` flag that we need to pass in so that you can add a commit message. This is important as you need these messages added to the log, or the individual commit messages are meaningless. We add the message at the end of the command sequence using quotes `" "`:

```
$ git commit -m "update to function ..."
```

After running this command sequence, you should see the following in your Terminal:

```
# On branch master
nothing to commit, working directory clean
```

Great! All the code has been updated and committed to the `master` branch!

### A word on commit messages

When writing a commit message, you want to phrase things in the present tense. Meaning, the code you committed will not do things in the future and they did not do things in the past. Examples of poor messages are:

```
$ git commit -m "added the new background image to the header"
```

or

```
$ git commit -m "will add new background image to the header"
```

or

```
$ git commit -m "SLAAAAAAAAAAAAAAYER!"
```

In both these cases, these messages when read by the other developers in the log send a confusing message. And the last one ... well o_O

Think of things in this way, "This commit will ..."

```
$ git commit -m "add new background image to the header"
```

Make sense?

## Commit history

Ok now that we have committed some code, let's see the history of these events.

```
$ git log
```

You will see:

  * the commit hash ID
  * author of the commit
  * the date of the commit
  * the commit message

```
commit 15d42d592fff5abe101e5985be0830d1bd03a1f1
Author: Dale Sande <dale.sande@gmail.com>
Date:   Tue Jun 10 18:25:26 2014 -0700

    update to function ...
```

Cool, now we know things about the code being committed to the repo. Want to know more?

```
$ git blame index.html
```

Yes, `blame` is the function and `index.html` is what we want to know about. This is a great way to see who did what on a given file when things go a little left.

```
^15d42d5 (Dale Sande 2014-06-10 18:25:26 -0700 1) <h1>Hello World</h1>
```

You can see the initial part of the hash, the time stamp and the code that was modified. NICE!
