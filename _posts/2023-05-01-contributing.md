---
title: Instructions for Contributing
layout: post
post-image: "https://comptag.github.io/t4ds-teaching/assets/images/beehive.jpg"
description: How to use the T4DS Workshop materials, or adapt them to your own workshop setting.
tags:
- schedule
---

## Getting Started

Begin by forking the repository located at the following url:

`https://github.com/compTAG/t4ds`

The site is built using Jekyll, hosted by github pages. If you'd like to build the
site locally, it should work by installing Jekyll, and running
`bundle exec jekyll serve`. Often Jekyll can be a bit tricky to get installed and
working properly, so it is also fine to build live. If you would like to try your luck
with jekyll locally, [here are instructions to get it running](https://jekyllrb.com/docs/installation/).
Otherwise, you can build live by pushing to the `gh-pages` branch. After doing so, github will build
the site automatically in a couple minutes.

## Working in the T4DS Repository

For stylistic changes throughout the site, one can customize features either in
`_config.yml` for primary site themes, headings and features, or in the html files
located in `_layouts`. Let's try this together.

### Stylizing the Introductory Page Frontmatter

All of the material for the introductory page standing alone is located in
`_config.yml`. Go ahead and try changing the title, the description, and the author image in there.
You can try testing your changes by pushing to the `gh-pages` branch.

To update the workshop materials themselves, edit the markdown files located in
`_posts`. (Or, create your own new markdown files!)  

---
