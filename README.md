# T4DS Workshop

## Instructions for Contribution:

1. After cloning the repo, add tutorials in the `_posts/` directory. Posts are in markdown and built into the site automatically.
2. Title posts in the format: `yyyy-mm-dd-postname.md` For example, `2023-04-17-awesome-topology-stuff.md`
3. When you're happy with your changes, push to the `gh-pages` directory

### Writing a Post

Every post starts with a header so that the site can incorporate it properly. This is in the format:

```
---
title: Topology, Woohoo!
layout: post
post-image: "any link to an image, must be url, either within our site or somewhere else"
description: Doing nifty stuff with topology in a time crunch
tags:
- tutorials
- topology
- yadayadayada
---
```

See any of the existing pages for examples.

## Other Fun .md Formatting Tips for Tutorials:

If you have question/answer stuff and want to hide answers, consider using a dropdown:

<details>
<summary>How do I dropdown?</summary>
<br>
This is how you dropdown.

```
<details>
<summary>How do I dropdown?</summary>
<br>
This is how you dropdown.
</details>
```

</details>

If you want to put text in a box, try this html:

___
**Objectives**
> - Learn stuff
> - Have fun
> - Eat bagels
___


If you want to see the built site, check it out 
[here](https://comptag.github.io/t4ds/). It normally takes 3 ish minutes to build.
You can also do this locally using jekyll, though it's not the easiest to set up. 
In a time crunch, I recommend just doing this online.

---

Dependencies: Uses **WhatATheme**, an awesome Jekyll theme. You can checkout the [**Demo Here**](https://thedevslot.github.io/WhatATheme/) :boom:
