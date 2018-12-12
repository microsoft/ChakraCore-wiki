We welcome community submissions to this Wiki via Pull Requests on this repo!

If you are adding a page, please note that the title of the page is determined by
the file name. Hyphens in the file names will become spaces in the titles of the
pages. Refer to existing files as examples of the naming convention.

Note: Please do not rename this file from README.txt to README.md.
README.txt will not show up in the Wiki view, but README.md will.


# ChakraCore-wiki Maintainers' Workflow

Small changes are often made by the Wiki maintainers directly via the Wiki
interface, and those changes are not automatically mirrored in this repo.

Due to low volume of changes, this repo (the ChakraCore-wiki repo) is manually
(rather than automatically) kept in sync with the Wiki at
https://github.com/Microsoft/ChakraCore/wiki.

It is recommended to configure your remotes as follows to reduce ambiguity:

    git remote add wiki https://<username>:<token>@github.com/Microsoft/ChakraCore.wiki.git
    git remote add repo https://<username>:<token>@github.com/Microsoft/ChakraCore-wiki.git
    git remote add user https://<username>:<token>@github.com/<username>/ChakraCore-wiki.git

The `wiki` remote is updated when maintainers manually make changes through the
GitHub Wiki interface.

The `repo` remote is updated when commits are made directly to this repo.

The `user` remote is the remote to which you will push branches when you want to
make PRs against the `repo` remote. You can also bypass PRs and push directly to
the `wiki` remote, since there is no automation around or checks on the wiki.

To avoid merge conflicts, when possible, before making changes via this repo or
merging any pull requests, please manually sync changes from the `wiki` remote
as follows:

    git checkout master
    git fetch --all
    git merge --ff wiki/master
    git push repo master
    git push user master  # optional, but recommended to keep your user clone in sync

If `wiki` and `repo` have become out of sync and you need to merge them:

    git checkout master  # tracking the last time you pushed repo to wiki
    git fetch --all
    git merge --ff repo/master  # sync to latest repo (keep these changes visible in --first-parent history)
    git merge wiki/master  # merge the wiki changes into the repo
    
    # push all remotes to keep things in sync
    git push repo master
    git push wiki master
    git push user master  # optional, but recommended
