+++
date = '2025-06-20T10:46:02+07:00'
draft = false
title = 'Building My Blog with Hugo, GitHub Pages, and Cloudflare'
tags = ["blog"]
topics = ["blog"]
my_taxonomies = ["value"]
+++

I've been meaning to create a space to document my experiments and learnings in tech. Nothing fancy — just a clean, personal site where I can write things down and share what I discover.

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

I wanted to use my own domain (not the default github.io URL), so I connected it through [Cloudflare](https://www.cloudflare.com/).

Cloudflare handles:
- DNS (domain pointing)
- Free HTTPS with SSL
- Performance optimization with global caching

It's a helpful layer that sits between my domain and GitHub Pages to make everything faster and more secure.


## How Everything Connects

Here's a diagram that shows how these pieces fit together:

![Diagram of blog setup with GitHub Pages, Cloudflare, and domain](/images/blog-setup.png)

- Hugo builds the blog as static files.
- GitHub Pages hosts those files.
- Cloudflare handles traffic, caching, and HTTPS.
- My domain points to Cloudflare.

## Setting Up Hugo Locally

To get started, I installed Hugo and created a new site:

```bash
hugo new site my-blog
cd my-blog
```

Then I picked a theme from themes.gohugo.io and added a few sample posts.

To preview the blog locally:

```bash
hugo server -D
```

That launches a local server at http://localhost:1313/.

## Automating Deployment with GitHub Actions

Instead of manually uploading files, I set up a GitHub Action. Every time I push changes, it automatically:

Builds the Hugo site

Deploys it to the gh-pages branch (used by GitHub Pages)

Once this is configured, publishing is as simple as:

```bash
git add .
git commit -m "New post"
git push
```

## Setting Up GitHub Pages
In my GitHub repository:

- I enabled GitHub Pages under the repo's settings

- I set the source to the gh-pages branch

- I added a CNAME file to define my custom domain

GitHub Pages now serves my blog whenever new content is pushed.

## Setting Up Cloudflare
To connect my domain:

- I added my domain to Cloudflare

- Updated my domain registrar to use Cloudflare's nameservers

- Created DNS records that point to GitHub Pages

- Enabled "Always Use HTTPS" and caching rules

Within minutes, my blog was live on my custom domain with HTTPS.

## Writing Blog Posts
Here's what creating a new post looks like:
```bash
hugo new posts/my-first-post.md
```
Then I just write the post in Markdown, save it, commit, and push. That's it — the blog updates itself.

## Final Thoughts
This setup is exactly what I was looking for: a fast, free, and elegant way to share my thoughts and projects without managing servers or logins.

If you're thinking of starting a tech blog — whether for notes, tutorials, or side projects — I highly recommend giving Hugo + GitHub Pages + Cloudflare a try. It's simple, efficient, and it just works.