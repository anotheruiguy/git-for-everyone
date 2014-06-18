# Setting up GIT Bash autocompletion

Run the following command:

```bash
curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash > ~/.git-completion.bash
```

This should create the `.git-completion.bash` file in your home dir.

Then add the following to your `~/.bashrc` or `~/.bash_profile` after `PATH`:

```bash
# Set the base PS1
export PS1="\t: \W$ "

# Source the git bash completion file
if [ -f ~/.git-completion.bash ]; then
    source ~/.git-completion.bash
    GIT_PS1_SHOWDIRTYSTATE=true
    GIT_PS1_SHOWSTASHSTATE=true
    GIT_PS1_SHOWUPSTREAM="auto"
    PS1='\t:\[\033[32m\]$(__git_ps1 " (%s)")\[\033[00m\] \W$ '
fi

export PS1
```

### -bash: __git_ps1: command not found

If you are seeing this error, this is because the `__git_ps1` function from the completion functionality was moved into a new file (`git-prompt.sh`).

You can either source the `git-prompt.sh` that comes with your installed version of Git, if it has it, or you can download and install a new one.

```bash
curl -o ~/.git-prompt.sh https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
```

... and add the following line to your `~/.bash_profile`:

```bash
source ~/.git-prompt.sh
```

### Git status

This will display the branch name next to the folder name in the bash prompt.

Symbols after the branch name indicate additional information about the repo state:

* `*`: The branch has modifications
* `$`: There are stashed changes
* `=`: The branch is equal with the remote branch
* `<`: The branch is behind the remote branch (can be fast-forwarded)
* `>`: The branch is ahead of the remote branch (remote branch can be fast-forwarded)
* `<>`: The branch and remote branch have diverged (will need merge)
