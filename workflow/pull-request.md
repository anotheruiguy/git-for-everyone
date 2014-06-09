# The Pull request

The pull request is where the rubber meets the road. As stated previously, one of the key points of the feature branch workflow is that the developer who wrote the code does not merge the code with master until there has been a peer review. Leveraging Github's pull request features, once you have completed the feature branch and pushed it to the repo, there will be an option to review the diff and create a pull request.

In essence, a pull request is a notification of the new code in an experience that allows a peer developer to review the individual updates within context of the update. For example, if the update was on line 18 of `header.haml`, then you will only see `header.haml` and a few lines before and after line 18.

This experience also allows the peer reviewer to place a comment on any line within the update. This will be communicated back to the editor of origin. This review experience really allows for everyone on the team to be actively involved in each update.

Once the reviewer has approved the editors updates, there are two ways to merge in the code. One from the Github interface and another from the command line.
