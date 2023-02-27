Minimum Viable Hugo 
===================


4 out of 5 web devs have experienced the following:

    "Hugo sounds great! Let me try it out!"
    "Okay, I made a new theme and a page in content/!!"
    "Running hugo server -D now!!! ... Where is it!!!!"

This repo aims to fix that.

# Quickstart

```bash
# Start a new site.
hugo new site .

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

Add something like
```yaml
---
draft: false
---
```
to the top of `_index.md` to serve it without the `-D`raft flag.

# TODO

- Turn this repo into a submodule you can pull in for this.
