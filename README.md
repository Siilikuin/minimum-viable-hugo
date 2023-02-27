Minimum Viable Hugo 
===================
*[Hugo](https://gohugo.io/) is a web framework which is frequently used to generate content from [Markdown](https://www.markdownguide.org/tools/hugo/). This repository helps new users get started.*


![image](https://user-images.githubusercontent.com/53230903/221623209-8a557a70-b81a-4232-a067-b3b0f1f1c577.png)

4 out of 5 web devs have experienced the following:

    "Hugo sounds great! Let me try it out!"
    "Okay, I made a new theme and a page in content/!!"
    "Running hugo server -D now!!! ... Where is it!!!!"

This repo aims to fix that.

# Quickstart

```bash
# Start a new site.
# We --force because this will complain
# if *anything* else is in the directory,
# even something so meek as a freshborn .git/.
hugo new site . --force

# Make a new theme. Tell Hugo we want to use it.
hugo new theme minimum-viable-hugo
echo "theme = 'minimum-viable-hugo'" >> config.toml

# GOTCHA #1: Your root page is called _index.md.
mkdir content/
hugo new _index.md
echo "Lorem ipsum dolor sit amet" >> content/_index.md

# GOTCHA #2: Hugo needs to be explicitly told to
# serve content from _index.md.
echo "{{ .Content }}" >> themes/minimum-viable-hugo/layouts/index.html

# Serve the site. Don't leave out the -D yet.
hugo server -D
```

Then go to `localhost:####` in your browser and you should see it.

If you look at `content/_index.md`, it will look like

```markdown
---
title: ""
date: 2023-02-27T18:21:50+02:00
draft: true
---

Lorem ipsum dolor sit amet
```

Change `draft` to `false`. Then you'll be able to run your site with just

```bash
hugo server
```

# TODO

- Turn this repo into a submodule you can pull in for this.
