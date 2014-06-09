# Push your branch

When working with feature branches on a team, it is typically not appropriate to merge your own code into master. Although this is up to your team as how to manage these expectations, but the norm is to make use of pull requests. Pull requests require that you push your branch to the remote repo.

To push the new feature branch to the remote repo, simply do the following:

```
$ git push origin my-new-feature-brach
```

As far as Git is concerned, there is no real difference between `master` and a feature branch. So, all the same Git features apply.

## My branch was rejected?

This is a special case when working on a team and the branch I am are pushing is out of sync with the remote. To address this, it's simple, pull the latest changes:

```
$ git pull origin my-new-feature-branch
```

This will fetch and merge any changes on the remote repo into my local brach with the changes, thus now allowing you to push.


## Working on remote feature branches

When I am are creating the feature branch, this is all pretty simple. But when I need to work on a co-workers branch, there are a few additional steps that I follow.

### Tracking remote branches

My local `.git/` directory will of course manage all my local branches, but my local repo is not always aware of any remote branches. To see what knowledge my local branch has of the remote branch index, adding the `-r` flag to `git branch` will return a list.

```
$ git branch -r
```

To keep my local repo 100% in sync with deleted remote branches, I make use of this command:

```
$ git fetch -p
```

The `-p` or `--prune` flag, after fetching, will remove any remote-tracking branches which no longer exist.

### Switching to a new remote feature branch

Doing a `git pull` or `git fetch` will update my local repo's index of remote branches. As long as co-workers have pushed their branch, my local repo will have knowledge of that feature branch. By doing a `git branch` you will see a list of my local branches. By doing a `git branch -r` I will see a list of remote branches. There is a good chance that the new feature branch is not in my list of local branches.

The process of making this remote branch a local branch to work on is easy, simply checkout the branch.

```
$ git checkout new-remote-feature-branch
```

This command will pull it's knowledge of the remote branch and create a local instance for me to work on.
