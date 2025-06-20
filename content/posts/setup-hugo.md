+++
date = '2025-06-20T10:46:02+07:00'
draft = true
title = 'Building My Blog with Hugo, GitHub Pages, and Cloudflare'
tags = ["hugo", "blog setup", "github pages", "cloudflare", "static site"]
+++

I’ve been meaning to create a space to document my experiments and learnings in tech. Nothing fancy — just a clean, personal site where I can write things down and share what I discover.

This post outlines how I set up this blog using **Hugo**, **GitHub Pages**, and **Cloudflare**. The entire setup is free to run, easy to maintain, and fast to load.

## Why Hugo?

[Hugo](https://gohugo.io/) is a static site generator. It takes simple text files and turns them into a fully working website.

Why I chose it:
- No need for a database or backend
- Fast build times
- Easy to write posts in Markdown
- Lots of community-supported themes

Since this blog is mostly for notes, write-ups, and guides, Hugo keeps things simple and organized.


## Hosting with GitHub Pages

After Hugo builds the site, I needed a way to put it online.

[GitHub Pages](https://pages.github.com/) was the perfect choice:
- Free hosting
- Directly integrates with GitHub repositories
- Supports automation via GitHub Actions

Once set up, all I have to do is push changes — GitHub builds and publishes the blog automatically.


## Domain and Cloudflare

I wanted to use my own domain (not the default `github.io` URL), so I connected it through [Cloudflare](https://www.cloudflare.com/).

Cloudflare handles:
- DNS (domain pointing)
- Free HTTPS with SSL
- Performance optimization with global caching

It’s a helpful layer that sits between my domain and GitHub Pages to make everything faster and more secure.


## How Everything Connects

Here’s a diagram that shows how these pieces fit together:

![Diagram of blog setup with GitHub Pages, Cloudflare, and domain](../images/blog-setup.png)

- Hugo builds the blog as static files.
- GitHub Pages hosts those files.
- Cloudflare handles traffic, caching, and HTTPS.
- My domain points to Cloudflare.

---

## Setting Up Hugo Locally

To get started, I installed Hugo and created a new site:

```bash
hugo new site my-blog
cd my-blog
```