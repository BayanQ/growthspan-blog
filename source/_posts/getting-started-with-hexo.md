---
title: Getting Started with Hexo
subtitle: A quick guide to building your blog with Hexo
date: 2025-10-27 14:30:00
author: Growthspan Team
tags:
  - hexo
  - tutorial
  - blogging
categories:
  - Technical
---

## Introduction to Hexo

Hexo is a fast, simple, and powerful blog framework powered by Node.js. This blog is built using Hexo with the Clean Blog theme.

### Why Hexo?

Here are some reasons why Hexo is a great choice for blogging:

1. **Fast Generation**: Hexo generates static files in seconds
2. **Markdown Support**: Write posts in Markdown with ease
3. **One-Command Deployment**: Deploy to various platforms with a single command
4. **Extensible**: Hundreds of themes and plugins available

### Creating a New Post

To create a new post, simply run:

```bash
hexo new post "My New Post"
```

This will create a new Markdown file in the `source/_posts` directory.

### Writing Content

You can use front-matter to configure your posts:

```yaml
---
title: My Post Title
subtitle: A catchy subtitle
date: 2025-10-27
author: Your Name
tags:
  - tag1
  - tag2
categories:
  - Category Name
---
```

### Building and Deploying

Generate static files:

```bash
hexo generate
```

Start a local server to preview:

```bash
hexo server
```

That's it! Happy blogging!
