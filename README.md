# Blog Using Python Pelican

Experimenting with the static site generator Pelican.


## Background

I've been writing my own in Flask, but the work is getting in the way of the content.
Rather than continuing to build a site using Flask, experiment with some static site generators.
To get a feel for things, write a few blog posts.


## Setup

Create a virtual environment.

Install
```
$ pip install pelican markdown
```


## Create Project

```
$ pelican-quickstart
```


## Write Content

Go make some pages.
Put `.md` files in `content/` - these are your posts.
Put regular pages in `content/pages`.


## Generate Content

```
$ pelican
```

You can also generate individual files.


## Deploy

Use the provided Makefile:

```
$ make devserver
```

This deploys to port `8000`.
It will regenerate pages when it detects changes.

The most basic way to host locally is to use python's built-in http server:

```
$ cd output
$ python -m http.server
```
