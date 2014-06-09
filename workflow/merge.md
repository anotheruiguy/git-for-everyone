# Merging the code

Although I can merge from Github's interface, it is preferred to do it from the command line. After all, what happens if Github merging tools are broken? It can happen.

So let's assume that I created a feature branch, edited code and pushed it to the repo. I initiated a pull request and the code update was approved. Here are the steps I will go through to merge the new code. Keep in mind, this illustration is simply managing code, this is not including running tests, while it can be worked into this workflow, that is a separate concern.

### Latest version

Make sure that I have the latest version of the feature branch from the remote repo

```
$ git checkout my-feature-branch
$ git pull origin my-feature-branch
```

### Branch is up to date

Make sure that the feature branch is up to date with `master`, while in the feature branch, execrate the following:

```
$ git pull origin master
```

If there are any conflicts, best to address them here.

### Merge the branches

Now that I know that the feature branch is up to date with the remote repo and that it has the latest code from `master`, I can now merge these branches. I also need to make sure that my local `master` branch is up to date as well.

```
$ git checkout master
$ git pull origin master
$ git merge --no-ff my-feature-branch
```

Notice the `--no-ff` flag in the merge command. This flag keeps the repo branching history from flattening out. If I were to look at the history of this branch, using GitX for example, when using the `--no-ff` flag, I will see the appropriate bump illustrating the history of the feature branch. This is helpful information. If I didn't use this flag, then Git will move the commit pointer forward.

I can either enter the `--no-ff` flag each time I merge or I can set this as my default. I prefer the default option. Running the following command will update the global gitconfig.

```
$ git config --global merge.ff false
```

And of course, setting the bit back to `true`, will return the default setting to fast forward with merging.

**NOTE:** there is a mild side-effect that will happen when you set this flag to `false`. Every time you do a `pull` this will not fast forward your local repo and basically make this a new commit. That's ok, but you will see this in the commit logs

```
Merge branch 'master' of github.com: ...

and

# Your branch is ahead of 'origin/master' by 1 commit.
```

If you are ok with this, then keep the flag. If this annoys or bothers you, do not use the flag and set `--no-ff` manually with each merge.

### Delete the local branch

Now that I have merged the code, the feature branch by definition is obsolete. First, delete the branch from the local repo.

```
$ git branch -d my-feature-branch
```

The `-d` flag for delete will typically delete any branch. Remember, you can't delete a branch you have checked out.

If you happen to see the following error when deleting a branch, then simply replace the `-d` with `-D` to force the delete.

```
error: The branch 'name-of-branch' is not an ancestor of your current HEAD.
```

### Delete the remote branch

If the feature branch was pushed to the repo, as it should have been per the workflow we described, you will want to delete this from the remote repo as well.

```
$ git push origin --delete my-feature-branch
```
