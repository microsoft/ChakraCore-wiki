We ask that PRs, in most cases, should be a single commit based on a reasonably recent commit
(though not necessarily the latest) from the target branch, with no merge commits.


# Getting starting and creating a PR

Following the usual Git convention, the following examples assume the remote referring to your fork [username/ChakraCore](https://github.com/username/ChakraCore), which you cloned from, is named `origin`, and [Microsoft/ChakraCore](https://github.com/Microsoft/ChakraCore) is named `upstream`.

Assume that your PR branch is named `feature` which you've pushed to your fork (`origin`), such that your pull request branch (locally) is `origin/feature`.

For various reasons, including simplifying instructions, we recommend not working directly in the `master` branch. Instead, check out a new branch before you start working:

```sh
(git:master)$ git checkout -b feature # check out a new branch called `feature`
(git:feature)$ # make some changes
(git:feature *)$ git commit -m "Short description of change."
(git:feature)$ git push origin feature # push your changes to your fork (origin) so that you can open a PR.
```


# ChakraCore Jenkins CI and auto-merging

Due to the speed that changes come in versus the time it takes for Jenkins CI checks to complete,
we do not enforce that the commit is based on the latest commit.
Therefore, please feel free to ignore the following message, which comes from GitHub itself,
rather than from ChakraCore policy or Jenkins.

> This branch is out-of-date with the base branch.
>
> Merge the latest changes from `master` into this branch.

The above message is simply saying that `master` has moved ahead of where it was when you started
working on your feature branch. There are no conflicts.
In this case, clicking the button to merge `master` into your branch will cause Jenkins checks
to start over and will delay your pull request from being merged.

Generally, there is no value in updating your PR in this case, unless you expect that the changes
added to the target branch (e.g. `master`) might cause your change to break,
even though there are no code conflicts.

However, if you get the following message:

> This branch has conflicts that must be resolved
>
> Use the web editor or the command line to resolve conflicts.

In this case you must resolve the conflicts and update your PR.
When you update your PR, we prefer that you rebase or squash your PR (see below)
to ensure that there are no merge commits.


# Rebasing your PR

Rather than merging the target branch into your PR,
we ask that you rebase your PR on top of the latest version of the target branch.
If your target branch is `master`, the simplest way will look something like the following:

```sh
(git:master)$ git checkout feature
(git:feature)$ git fetch upstream # get the latest commits from upstream (including upstream/master)
(git:feature)$ git rebase upstream/master # follow the prompts to complete the rebase
(git:feature)$ git push --force origin feature # force-push the PR branch to update
```


# Squashing your PR

While you are still iterating on your PR and getting code reviews, feel free to push additional commits to your PR;
however, before merging your PR, we will generally ask that you squash your PR to a single commit, to simplify history.

Squashing is similar to rebasing except that the result is exactly one commit.
This is the simplest way to reduce many commits into a single commit.
It is especially helpful in untangling complex history caused by multiple merges into your feature branch
Think of a squash commit as taking your entire PR branch and making a single commit out of the sum of those changes.

```sh
(git:feature)$ git branch -m feature-saved # rename the current branch so that your work is saved
(git:feature-saved)$ git fetch upstream
(git:feature-saved)$ git checkout -B master upstream/master # forcibly check out a new copy of upstream/master
(git:master)$ git checkout -b feature # create a new branch named 'feature' to match your PR branch
(git:feature)$ git merge --squash feature-saved
(git:feature *)$ git commit # Remove "squashed commit of the following" and subsequent lines.
(git:feature)$ git push --force origin feature # force-push your PR branch to update your PR
```

