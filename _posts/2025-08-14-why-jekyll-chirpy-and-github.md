---
title: Why We Use Jekyll + Chirpy (and GitHub)
description: Secure, static, fast publishing in Markdown — with a transparent, contributor-friendly workflow.
author: bsec
date: 2025-08-14 09:00:00 -0300
categories: [Meta]
tags: [jekyll, chirpy, github, workflow]
pin: true
math: true
mermaid: true
image:
  path: /assets/img/bsec/welcome.webp
  alt: Chirpy theme preview on multiple devices
---

> TL;DR — Jekyll + Chirpy gives us a **secure, static, fast** site where **every post is just Markdown** (so your content is truly yours). We keep it on **GitHub** so the repository stays **public** and every change is tied to your GitHub identity for **visibility** and a clean contribution history.

## Why Jekyll?

- **Secure & low-maintenance:** No database, no server-side runtime. Jekyll prebuilds pages into static HTML, so there’s a tiny attack surface and nothing to patch constantly.
- **Fast by default:** Pre-rendered pages ship quickly and are CDN-friendly. No queries, no templating at request time.
- **Markdown = your content, your format:** Posts are plain `.md` files. They’re portable, diff-able, and future-proof — no lock-in to a proprietary CMS.
- **Version-controlled writing:** Branches, commits, and pull requests make content changes reviewable and reversible.

## Why the Chirpy theme?

Chirpy adds a polished UX and a bunch of batteries-included features without complexity:

- Clean design, dark mode, mobile-first
- Built-in posts list, tags, categories, TOC
- Code highlighting, **Math** (`math: true`), and **Mermaid** diagrams (`mermaid: true`)
- Good defaults for SEO (sitemap, feed), and sensible front matter

## Why GitHub?

- **Public by default:** The repository is (and remains) public, which helps discovery and trust.
- **Attribution & visibility:** Commits are tied to your GitHub account, providing clear authorship and a transparent history.
- **Open collaboration:** Issues and PRs make it easy to propose edits, review content, and discuss changes.

## How to add a new post

1) **Create a branch**

```bash
git checkout -b post/your-title
````


2. **Add yourself to the authors list (once)**

To show proper bylines and optional avatars/links, add your author entry in `_data/authors.yml`.  
The **key** should be your handle (and must match the `author` value in each post’s front matter).

```yaml
bsec:
  name: "Guilherme A."
  bio: "Peel back the layers. See what they missed."
  avatar: /assets/img/authors/bsec.jpg  # optional
  url: https://behindsecurity.com       # optional
````

* Put avatar images in `assets/img/authors/` (e.g., `assets/img/authors/bsec.jpg`).
* In your post front matter use `author: bsec` (the key above).

2. **Add a Markdown file under `_posts/`**

File name format is:

```
YYYY-MM-DD-your-title.md
```

Example:

```
_posts/2019-08-09-getting-started.md
```

3. **Use this front matter header**

```yaml
---
title: Text and Typography
description: Examples of text, typography, math equations, diagrams, flowcharts, pictures, videos, and more.
author: your-handle   # must match a key in _data/authors.yml
date: 2019-08-08 11:33:00 +0800
categories: [Blogging, Demo]
tags: [typography]
pin: true
math: true
mermaid: true
image:
  path: /assets/img/<your-author-name>/your-image.webp
  alt: Short descriptive alt text
---
```

* **`title`**: Post title shown on the site.
* **`description`**: Optional summary for previews/SEO.
* **`date`**: Use your local time zone.
* **`categories` / `tags`**: Organize your content; categories are hierarchical buckets, tags are free-form keywords.
* **`pin`**: `true` pins the post on the home page.
* **`math` / `mermaid`**: Enable LaTeX and Mermaid as needed.
* **`image.path`**: Lead image shown in previews and at the top. **Recommended: 1200 × 630 px**

4. **Add images to** `assets/img/<your-author-name>/`

```
assets/
  img/
    <your-author-name>/
      your-image.webp
```

Reference them in front matter as above, or in the body:

```markdown
![Diagram alt text](/assets/img/<your-author-name>/your-image.webp)
```

5. **Write your content in Markdown**

Use headings, code blocks, lists, and optional extras:

* **Math** example (with `math: true`):

  ```math
  E = mc^2
  ```

* **Mermaid** example (with `mermaid: true`):

  ```mermaid
  flowchart LR
    A[Idea] --> B[Draft]
    B --> C[Review]
    C --> D[Publish]
  ```

6. **Commit and push**

```bash
git add _posts/2025-08-14-why-jekyll-chirpy-and-github.md assets/img/<your-author-name>/your-image.webp
git commit -m "Add post: Why we use Jekyll + Chirpy (and GitHub)"
git push -u origin post/your-title
```

7. **Open a Pull Request to `main`**

* We work with **branches and PRs**. Submit your PR, it'll be reviewed and merged when it’s approved.
* After merge, the site will rebuild and your post will be live.


## Quick Post Template

Copy this as a starting point for any new article:

```markdown
---
title: Your Post Title
description: One-line summary for previews and SEO.
author: your-github-handle
date: 2025-08-14 09:00:00 -0300
categories: [Category, OptionalSubcategory]
tags: [tag1, tag2]
pin: false
math: false
mermaid: false
image:
  path: /assets/img/<your-author-name>/cover.webp
  alt: Brief alt text
---

Intro paragraph.

## Section

Your content here.

```

