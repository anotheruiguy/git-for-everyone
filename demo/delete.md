# Delete the branch

Now that all our codes are merged, there is no need to keep the `new-branch` branch around. So, let's kill it with fire!

```
$ git branch -D new-branch
```

BOOM! There is no coming back from that easily. But why would we want to keep that around? Once we merge the code, the history and code are all now part of `master` and that's where we want it. Keeping that old branch around us useless to us. When we want to add new code, we will create a new feature branch.

![image](http://i.imgur.com/g4IePiL.png)
