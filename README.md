# Unsupervised — Company Website

Jekyll-based website for [unsupervisedrobotics.ai](https://unsupervisedrobotics.ai).

## Prerequisites

Ruby dev headers and build tools are required (one-time system install):

```bash
sudo apt-get install -y ruby-dev build-essential
```

Install Bundler (if not already installed):

```bash
gem install bundler --user-install
```

Add Bundler to your PATH (add this line to `~/.bashrc` to make it permanent):

```bash
export PATH="$HOME/.local/share/gem/ruby/3.2.0/bin:$PATH"
```

## Setup

```bash
cd /home/gberseth/playground/Unsupervise_site
bundle config set --local path 'vendor/bundle'
bundle install
```

## Local Development

```bash
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000) in your browser.

## Adding a Blog Post

Create a new file in `_posts/` named `YYYY-MM-DD-your-title.md`:

```markdown
---
layout: post
title: "Your Post Title"
date: 2026-04-15
categories: [company]
description: "A short description for SEO."
---

Your content here in Markdown.
```

Jekyll will automatically pick it up and list it on the `/blog` page.

## Site Structure

```
_config.yml          ← site settings (URL, email, social links)
index.html           ← homepage (all main sections)
blog.html            ← blog listing page
_posts/              ← blog posts (Markdown)
_layouts/
  default.html       ← base layout (header + footer wrapping all pages)
  post.html          ← blog post layout
  page.html          ← generic page layout
_includes/
  header.html        ← sticky navigation bar
  footer.html        ← site footer
assets/css/style.css ← all styles (brand colors, typography, layout)
Gemfile              ← Ruby gem dependencies
```

## Deploying

Build the static site:

```bash
bundle exec jekyll build
```

The output is in `_site/`. Upload the contents of `_site/` to your hosting server.
