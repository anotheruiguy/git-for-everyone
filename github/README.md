# Github

Without a doubt, Git and Github are like peanut butter and jelly. Once you have registered yourself as a user on Github, the next thing you need to do is establish a connection to Github using SSH.

## Generating SSH Keys

[source](https://help.github.com/articles/generating-ssh-keys#platform-all)

We strongly recommend using an SSH connection when interacting with GitHub. SSH keys are a way to identify trusted computers, without involving passwords. The steps below will walk you through generating an SSH key and then adding the public key to your GitHub account.

### Step 1: Check for SSH keys

First, we need to check for existing SSH keys on your computer. Open up the command line and type:

```
$ cd ~/.ssh
$ ls -al
```

### Lists the files in your .ssh directory

Check the directory listing to see if you have files named either `id_rsa.pub` or `id_dsa.pub`. If you don't have either of those files go to **step 2**. Otherwise, you can skip to **step 3**.

## Step 2: Generate a new SSH key

To generate a new SSH key, copy and paste the text below, making sure to substitute in your email. The default settings are preferred, so when you're asked to "enter a file in which to save the key,"" just press enter to continue.

```
$ ssh-keygen -t rsa -C "your_email@example.com"
# Creates a new ssh key using the provided email
Generating public/private rsa key pair.
Enter file in which to save the key (/your_home_path/.ssh/id_rsa):
```

Next, you'll be asked to enter a passphrase.

```
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```

Then add your new key to the ssh-agent:

```
$ ssh-add ~/.ssh/id_rsa
```

## Step 3: Add your SSH key to GitHub

Open the `~/.ssh/id_rsa.pub` file with a text editor. This is your SSH key. Select all and copy to your clipboard.

Or you can also run this from the command line:

```
pbcopy < ~/.ssh/id_rsa.pub
```

Now that you have the key copied, it's time to add it into GitHub:

1. In the user bar in the top-right corner of any page, click Account Settings
1. Click SSH Keys in the left sidebar.
1. Click Add SSH key.
1. In the Title field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
1. Paste your key into the "Key" field.
1. Click Add key.
1. Confirm the action by entering your GitHub password.

## Step 4: Test everything out

To make sure everything is working, you'll now try SSHing to GitHub. When you do this, you will be asked to authenticate this action using your password, which for the passphrase you created earlier.

Open up the command line and type:

```
$ ssh -T git@github.com
# Attempts to ssh to github
```

You may see this warning:

```
The authenticity of host 'github.com (207.97.227.239)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
```

Don't worry! This is supposed to happen. Verify that the fingerprint in your terminal matches the one we've provided up above, and then type "yes."

```
Hi username! You've successfully authenticated, but GitHub does not
# provide shell access.
```

If that username is yours, you've successfully set up your SSH key! Don't worry about the "shell access" thing, you don't want that anyway.

If you receive a message about "access denied," you can [read these instructions for diagnosing the issue](https://help.github.com/articles/error-permission-denied-publickey).

If you're switching from HTTPS to SSH, you'll now need to update your remote repository URLs. For more information, see [Changing a remote's URL](https://help.github.com/articles/changing-a-remote-s-url).
