# Branch management

As I am working on my new feature branch, it is a good idea to commit often. This allows me to move forward without fear that if something goes wrong, or you have to back out for some reason, I don't lose too much work. Think of committing like that save button habit you have so well programed into you.

Each commit also tells a little bit about what I just worked on. That's important when other devs on the team are reviewing my code. It's better to have more commits with messages that explain the step versus one large commit that glosses over important details.

## Commit your code

As I am creating changes in my project, these are all unseated updates. With each commit there most likely will be additions, and there will also be deletions from time to time. To get a baring of the updates I have made, lets get the status.

```
$ git status
```

This command will give you a list of all the updated, added and deleted files.

To add files, I can add them individually or I can add all at once. From the root of the project I can use:

```
$ git add .
```

In order to remove deleted files from the version control, I can again either remove individually or from the root address them all like so:

```
$ git add -u
```

I'm lazy, I don't want to think, so the following command I make heavy use of to address all additions and deletions.

```
$ git add --all
```

All the preceding commands will stage the updates for commitment. If I run a `git status` at this point, I will see my updates presented differently, typically under the heading of `Changes to be committed:`. At this point, the changes are only staged and not yet committed to the branch. To commit, do the following:

```
$ git commit -m "a commit message in the present tense"
```

It is considered best to illustrate your comment in the tense that this will do something to the code. It didn't do something in the past and it won't do something in the future. The commit is doing something now.

A bad example would be:

```
$ git commit -m "fixed bug with login feature"
```

A good example would be:

```
$ git commit -m "update app config to address login bug"
```

Comments are cheap. For more on how to write expressive commit messages, read [5 Useful Tips For A Better Commit Message](http://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message).
