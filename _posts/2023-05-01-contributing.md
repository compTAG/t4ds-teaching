---
title: Instructions for Contributing
layout: post
post-image: "https://comptag.github.io/t4ds-teaching/assets/images/beehive.jpg"
description: How to use the T4DS Workshop materials, or adapt them to your own workshop setting.
tags:
- schedule
---

## Getting Started

This tutorial assumes basic familiarity with `git`, but
we will try to insert the required git commands when they're first
introduced in dropdown commands. If you need help with git,
feel free to ask us or to consult the
[software carpentries tutorial](https://swcarpentry.github.io/git-novice/).

Begin by creating a new repository on github for your project, and cloning the repository
located at this url:

`https://github.com/compTAG/t4ds`

The cleanest way to do this is by mirroring our repository. Do this with a bare clone:

```
$ git clone --bare https://github.com/compTAG/t4ds
$ cd t4ds.git
$ git push --mirror https://github.com/YOUR-GITHUB-USERNAME/NAME-OF-YOUR-REPO.git
```

Where you push to a newly created repo of your own. We would suggest also just calling this repo
`t4ds`, although any name should be fine.

Then you can delete the temporary repo you first cloned:

```
cd ..
rm -rf t4ds.git
```

And clone your newly mirrored github repo (under your user, or organization):

```
git clone https://github.com/YOUR-GITHUB-USERNAME/NAME-OF-YOUR-REPO.git
```

It should start building automatically in your repo. You can see this by inspecting the
`actions` tab in the `gh-pages` branch. It should be located at the following address:

`https://YOUR-GITHUB-USERNAME.github.io/NAME-OF-YOUR-REPO/`

The site is built using Jekyll, hosted by github pages. When making changes to a github pages
site, simply push to the `gh-pages` branch.
If you'd like to build the
site locally, it should work by installing Jekyll, and running
`bundle exec jekyll serve`. Often Jekyll can be tricky to get installed and
working properly, so it is also fine to build live. If you would like to try your luck
with jekyll locally, [here are instructions to get it running](https://jekyllrb.com/docs/installation/).


## Working in the T4DS Repository

For stylistic changes throughout the site, one can customize features either in
`_config.yml` for primary site themes, headings and features, or in the html files
located in `_layouts`. Let's try this together.

### Stylizing the Introductory Page Frontmatter

All of the material for the introductory page standing alone is located in
`_config.yml`. Go ahead and try changing the title, and the description to anything you would like.
If you need ideas, maybe change the title to something like
`My Cool TDA Tutorial`, and change the description to
`
You can try testing your changes by pushing to the `gh-pages` branch.

Likely, you will want to change the heroimage to something specific to your workshop. This can be done by either:
1. Linking to an image somewhere on the internet (for example, we used open source NPS images.)
2. Linking to an image on the internet within the assets of this website
3. Linking to an image using relative path within the directory.

To update the workshop materials themselves, edit the markdown files located in
`_posts`. (Or, create your own new markdown files!)  

---
