# Claude Blog Post Workflow
## blog.emen.win - emenblade/blog

Claude checks this file before creating or pushing any post.

---

## Checklist

### 1 - Gather content
- Photos and brief from Alex
- Clarify vibe: story, walkthrough, photo dump

### 2 - Draft
- Alex's voice: casual, dry humor, first person, short and punchy
- No corporate words. No "In conclusion."
- Reference photos naturally
- Get approval before touching the repo

### 3 - Front matter
```yaml
---
title: "Post Title"
date: YYYY-MM-DD
draft: false
description: "One punchy line"
tags:
  - tag1
  - blog
type: gallery
no_toc: true
Image: "/images/post-slug.jpg"
---
```

### 4 - File structure
- `content/posts/post-slug/index.md`
- Body images: `content/posts/post-slug/1-image.jpg`, `2-image.jpg` etc
- Cover image: `assets/images/post-slug.jpg` AND `static/images/post-slug.jpg`

### 5 - After publish
- GitHub Actions builds in ~60s
- Confirm live at https://blog.emen.win/posts/post-slug/
