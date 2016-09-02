We welcome community submissions to this Wiki via Pull Requests on this repo!

If you are adding a page, please note that the title of the page is determined by
the file name. Hyphens in the file names will become spaces in the titles of the
pages. Refer to existing files as examples of the naming convention.


# ChakraCore Maintainers' Workflow

Small changes are often made by the Wiki maintainers directly via the Wiki
interface, and those changes are not automatically mirrored in this repo.

Due to low volume of changes, this repo (the ChakraCore-wiki repo) is manually
kept in sync with the Wiki at https://github.com/Microsoft/ChakraCore/wiki.

It is recommended to configure your remotes as follows to reduce ambiguity:

    git remote add repo https://<username>:<token>@github.com/Microsoft/ChakraCore-wiki.git
    git remote add wiki https://<username>:<token>@github.com/Microsoft/ChakraCore.wiki.git

The `wiki` remote is updated when maintainers manually make changes through the
GitHub Wiki interface.

The `repo` remote is updated when commits are made directly to this repo.

To avoid merge conflicts, before making changes via this repo or merging any
pull requests, please manually sync changes from the `wiki` remote as follows:

    git checkout master
    git fetch --all
    git merge --ff wiki/master
    git push repo master

Note: Please do not rename this file from README.txt to README.md.
README.txt will not show up in the Wiki view, but README.md will.
