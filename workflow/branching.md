# Basic branching

When working with a centralized workflow the concepts are simple, `master` represented the official history and is always deployable. With each now scope of work, aka feature, the developer is to create a new branch. For clarity, make sure to use descriptive names like `transaction-fail-message` or `github-oauth` for your branches.

**#Protip:** Although you may have a feature like 'user login and registration`, this is not considered appropriate to create a feature branch at this level, there is too much work to be done. It is better to break these large deliverables down to smaller bits of work that can be continuously integrated into the project. Remember, commit early and often.

Before you create a branch, be sure you have all the upstream changes from the `origin/master` branch.

## Make sure you are on master

Before I pull, I make sure I am on the right branch. I have GIT Bash autocompletion installed, this tells me the branch in the prompt. Otherwise, the following command is good to know to list out the branches I have locally as well designate which branch I am currently on.

```
$ git branch
```

The checked out branch will have a `*` before the name. If the return designates anything other then `master` then switch to master

```
$ git checkout master
```

Once on master and ready to pull updates, I use the following:

```
$ git pull origin master
```

The `git pull` command combines two other commands, `git fetch` and `git merge`. When doing a `fetch` the resulting commits are stored as remote branch allowing you to review the changes before merging. Merging on the other hand can involve additional steps and flags in the command, but more on that later. For now, I'll stick with `git pull`.

Now that I am all up to date with the remote repo, I'll create a branch. For efficiency, I will use the following:

```
$ git checkout -b my-new-feature-branch
```

This command will create a new branch from `master` as well checkout out that new branch at the same time. Doing a `git branch` will list out the branches in my local repo and place a `*` before the branch that is checked out.

```
  master
* my-new-feature-branch
```

## Do you have to be on master to branch from master?

No. There is a command that allows me to create a new branch from any other branch while having checked out yet another branch. WAT?!

```
$ git checkout -b transaction-fail-message master
```

In that example, say I was in branch  `github-oauth` and I needed to create a new branch and then checkout the new branch? By adding `master` at the end of that command, Git will create a new branch from master and then move me (checkout) to that new branch.

This is a nice command, but make sure you understand what you are doing before you do this. Creating bad branches can cause a real headache when trying to merge back into master.
