# ci-badge

A shell script that echoes back the link to your repo's CI badges. Never waste time looking up them up on the CI's documentation again!

## Usage

```bash
$ REPO=foo/bar

$ ci-badge -t $REPO
https://travis-ci.org/foo/bar.svg?branch=master

$ ci-badge -a $REPO
https://ci.appveyor.com/api/projects/status/github/foo/bar?branch=master&svg=true

$ ci-badge -tb dev $REPO # Specify the branch
https://travis-ci.org/foo/bar.svg?branch=dev

$ ci-badge -mt $REPO # echo the output as markdown
![](https://travis-ci.org/foo/bar.svg?branch=master)

$ ci-badge -mt $REPO -d 'You can also specify a description.'
![You can also specify a description.](https://travis-ci.org/foo/bar.svg?branch=master)

$ ci-badge -mt $REPO -l # links to a particular URL when the badge is clicked
# default is the CI's status page for your repo
[![](https://travis-ci.org/foo/bar.svg?branch=master)](https://travis-ci.org/foo/bar)
```

## Copying to the clipboard

```bash
# Mac
$ ci-badge -t $REPO | pbcopy

# Linux
$ ci-badge -t $REPO | xclip

# Windows
$ ci-badge -t $REPO | clip
```
