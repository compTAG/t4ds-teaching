---
title: Instructions for Contributing to the T4DS Site Template
layout: post
post-image: "https://comptag.github.io/t4ds-training/assets/images/beehive.jpg"
description: How to use the T4DS Workshop materials, or adapt them to your own workshop setting.
tags:
- schedule
---

## Getting Started

This tutorial assumes basic familiarity with git, but
we will try to insert the required git commands when they're first
introduced in dropdown commands. If you need help with git and github,
feel free to ask us or to consult the
[software carpentries tutorial](https://swcarpentry.github.io/git-novice/).

Begin by forking the T4DS github repository, located at this address:

[https://github.com/compTAG/t4ds](https://github.com/compTAG/t4ds])

![fork](https://comptag.github.io/t4ds-training/assets/images/fork.jpg)

This should create a version of the T4DS repository that you can edit independently.

Move to your desired working directory, and clone your new repo (under your user, or organization) to work locally:

```
git clone https://github.com/YOUR-GITHUB-USERNAME/NAME-OF-YOUR-REPO.git
cd NAME-OF-YOUR-REPO
```

The site is built using Jekyll, hosted by github pages. When making changes to a github pages
site, we will push to the `gh-pages` branch.
Make sure you're working on this branch by running:
```git checkout gh-pages```

The github pages site will likely not build right away after forking, and instead
builds after your first commit. Make a minor edit to `README.md` locally,
and commit and push your changes.

For example, rename the readme header to `My T4DS Workshop`, and then push to the
gh-pages branch. As a reminder, this is done with:

```
git add README.md
git commit -m "First commit to t4ds fork"
git push origin gh-pages
```

The site should then build within a minute or two.
You can see the result by inspecting the
`actions` tab in the `gh-pages` branch. It should be located at the following address:

`https://YOUR-GITHUB-USERNAME.github.io/NAME-OF-YOUR-REPO/`

<details>
<summary style="color:blue">Expected Github Actions Result</summary>
<br>
<pre style="background-color:lightblue">
<img src="https://comptag.github.io/t4ds-training/assets/images/built.jpg" alt="pts pairs">
</pre>
</details>

If you'd like to build the
site locally, it should work by installing Jekyll, and running
`bundle exec jekyll serve`. Often Jekyll can be tricky to get installed and
working properly, so it is also fine to build live. If you would like to try your 
luck with jekyll locally, 
[here are instructions to get it running](https://jekyllrb.com/docs/installation/).

## Working in the T4DS Repository

For stylistic changes throughout the site, one can customize features either in
`_config.yml` for primary site themes, headings and features, or in the html files
located in `_layouts`. Let's try this together.

### Stylizing the Introductory Page Frontmatter

All of the material for the introductory page standing alone is located in
`_config.yml`. Go ahead and try changing the title, and the description to anything you would like.
If you need ideas, maybe change the title to something like
`My Awesome TDA Workshop`, and change the description to
`Triangles, filtrations, and diagrams, oh my!`.

You can try testing your changes by pushing to the `gh-pages` branch. They should be updated in a minute or two.

<details>
<summary style="color:blue">Expected Build Result</summary>
<br>
<pre style="background-color:lightblue">
<img src="https://comptag.github.io/t4ds-training/assets/images/title.jpg" alt="pts pairs">
</pre>
</details>

Likely, you will want to change the heroimage to something specific to your workshop. This can be done by either:
1. Linking to an image somewhere on the internet (for example, we used open source NPS images.)
2. Linking to an image on the internet within the assets of this website
3. Linking to an image using relative path within the directory.

In our experience, options 1 and 2 are preferable, as option 3 (relative path) 
is often
inconsistent and dependent on unknown build settings, the chosen theme, various 
versions of jekyll, and perhaps even the weather.

Try changing the heroimage to an (open source) image on the internet of your choice. For example, you could try
this image from the NPS of a utah rock with interesting topology:

`https://www.nps.gov/npgallery/GetAsset/1FE16D77-155D-451F-67BEAA70882EBD52/proxy/hires?`

<details>
<summary style="color:blue">Expected Build Result</summary>
<br>
<pre style="background-color:lightblue">
<img src="https://comptag.github.io/t4ds-training/assets/images/heroimage.jpg" alt="pts pairs">
</pre>
</details>

Somemtimes the new heroimage can sometimes take a minute to show up correctly.
If it is not appearing, try changing another variable in the `_config.yml`, such as
the author name, or proceed patiently. Your background will change eventually,
patience is one of the unfortunate requirements of working with Jekyll.

### Changes to Site Structure

If you would like to make changes affecting the broader site structure,
edits need to be made to html files in the `_includes` folder. A common thing one might
need to do is change the names of navbar tabs. To demonstrate this, let's change the name of the
`WORKSHOP MATERIALS` tab to `MY NEW TUTORIALS`. Edit the corresponding text in `navbar.html`,
and push your changes.

<details>
<summary style="color:blue">Expected Build Result</summary>
<br>
<pre style="background-color:lightblue">
<img src="https://comptag.github.io/t4ds-training/assets/images/navbar1.jpg" alt="pts pairs">
</pre>
</details>

It is sometimes useful to link to specific pages in the navbar. In particular,
our tutorial materials are entirely generated by `.md` files in the `_posts`
directory, which we can link using preassigned variables from `_config.yml`.

For example, let's create a new tab linking to the first T4DS tutorial.
Insert the following `<a>` element in the corresponding
`<div>` element in `navbar.html`:

```
<a class="navbar-item" href="{{site.url}}{{site.baseurl}}/blog/intro-to-topology">FIRST TUTORIAL</a>
```

After committing and pushing, you should see your site update with a new tab, linking to the first tutorial.

<details>
<summary style="color:blue">Expected Build Result</summary>
<br>
<pre style="background-color:lightblue">
<img src="https://comptag.github.io/t4ds-training/assets/images/navbar2.jpg" alt="pts pairs">
</pre>
</details>

During this process, you might have noticed a few things:

1. The base site url is populated by variables set in the `_config.yml` file, which gives build instructions.
2. It is possible to use logic based on variables set in `_config.yml` (We can even use loops, see line 42 of `footer.html`).
3. Our workshop materials are populated by `.md` files in the `/blog/` subdirectory, named by the title of the `.md` file.

In general, everything in this template is readily customizable, and accessible via the suspected `.html` file in `_includes`.
Variables are changed, removed, or created in the `_config.yml` file. Beware when making edits to this file, they can
affect the entire site!

If you would like more practice making these kinds of edits, we suggest customizing the site footer.
Perhaps try changing the links in the site footer from MSU associated websites to your own.

### Writing Workshop Materials

You are welcome to edit, reuse, or get rid of any T4DS content when 
running your own workshop, 
being sure to cite materials appropriately. The entirety of the 
workshop materials can be edited in `.md` files in the `_posts` directory.

The structure of these posts is as follows:

#### Title

The `.md` files used to generate workshop materials
are titled in the format `yyyy-mm-dd-title.md`.

The choice in date matters for nothing other than assembling the order
of blog posts under the `WORKSHOP MATERIALS` tab (which you locally changed to 
`MY NEW TUTORIALS`). This type of ordering by date is the native Jekyll format, so we 
ran with it. As you might notice, posts are ordered starting with the most recent
date, and ending with the furthest in the past. We chose dates accordingly to give
the desired order.

#### Markdown Header

The header of a tutorial is designated by the following variables:

```
---
title: Insert Page Title
layout: post
post-image: "https://www.link-to-image.com"
description: Description of what the tutorial hopes to accomplish
tags:
- related topics to this tutorial
- and another
- etc
---
```

Otherwise, the tutorials use standard Markdown syntax. If you need a review of that,
the [markdown syntax guide](https://www.markdownguide.org/basic-syntax/) might be
helpful.

Aside from the standard Markdown syntax, the only nontrivial addition we made was to
have dropdowns throughout our tutorials using embedded html.

The syntax for these dropdowns is as follows. We used blue dropdowns for helpful notes,
orange for additional information on a topic, and red was for answers to activity
questions.

```
<details>
<summary style="color:blue">A Blue Dropdown</summary>
<br>
<pre style="background-color:lightblue">
The insightful text inside a blue dropdown. We normally use these for helpful notes.
</pre>
</details>
```

Which will render as:

<details>
<summary style="color:blue">A Blue Dropdown</summary>
<br>
<pre style="background-color:lightblue">
The insightful text inside a blue dropdown. We normally use these for helpful notes.
</pre>
</details>


Along with text, it is also possible to embed an image in a dropdown:

```
<details>
<summary style="color:red">A Red Dropdown</summary>
<br>
<pre style="background-color:lightcoral">
<img src="https://comptag.github.io/t4ds/assets/images/pts-weight.jpg " alt="pts pairs">
</pre>
</details>
```

Which will render as:

<details>
<summary style="color:red">A Red Dropdown</summary>
<br>
<pre style="background-color:lightcoral">
<img src="https://comptag.github.io/t4ds/assets/images/pts-weight.jpg " alt="pts pairs">
</pre>
</details>

We can even embded code in a dropdown:

```
<details>
<summary style="color:DarkOrange">More Info</summary>
<br>
<pre style="background-color:Gold">
<code>
Diag1966 <- gridDiag(X=dfGlac, FUNvalues = distances, maxdimension = 1, sublevel = TRUE, printProgress = TRUE)
</code>
</pre>
</details>
```

Which will render as:

<details>
<summary style="color:DarkOrange">An Orange Dropdown</summary>
<br>
<pre style="background-color:Gold">
<code>
Diag1966 <- gridDiag(X=dfGlac, FUNvalues = distances, maxdimension = 1, sublevel = TRUE, printProgress = TRUE)
</code>
</pre>
</details>

If you need to write math, the standard latex syntax should work
(even in a dropdown):

`$\mathbb{M}\mathcal{A}\mathcal{T}\mathcal{H}$`

Which will render as:

$\mathbb{M}\mathcal{A}\mathcal{T}\mathcal{H}$

### Make Your Own Post!

As a concluding activity, in breakout rooms we will have you make a new
post together.
Title the file `2023-06-21-example.md`. 
Where will this post appear in the `MY NEW TUTORIALS` tab?

Pick any title, image, and description you would like, and start adding text
in the markdown document. If you need inspiration, the following url contains
another good image from the NPS you could base the post on (and link to as an image):

[https://www.nps.gov/npgallery/GetAsset/F35A177B-1DD8-B71B-0B13407634E7DE52/proxy/hires?](https://www.nps.gov/npgallery/GetAsset/F35A177B-1DD8-B71B-0B13407634E7DE52/proxy/hires?)

Perhaps try adding a markdown header (using `#` syntax), a dropdown, and a 
mathematical equation.

## Credits

- All linked images are open source from the National Parks Service, or taken by Ben Holmgren.

---
