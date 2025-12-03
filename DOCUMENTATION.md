# Stories Over Statblocks - Internal Documentation

**This file is excluded from the published site and is for reference only.**

## Table of Contents

1. [Site Overview](#site-overview)
2. [Jekyll Basics](#jekyll-basics)
3. [Theme: Millennial](#theme-millennial)
4. [Creating Blog Posts](#creating-blog-posts)
5. [Creating Pages](#creating-pages)
6. [Front Matter Reference](#front-matter-reference)
7. [File Structure](#file-structure)
8. [Customization Guide](#customization-guide)

---

## Site Overview

This is a Jekyll static site using the **Millennial theme** and hosted on **GitHub Pages** with a custom domain (`storiesoverstatblocks.com`).

- **Site Generator**: Jekyll 4.4.1
- **Theme**: Millennial (local copy, not remote)
- **Hosting**: GitHub Pages
- **Domain**: storiesoverstatblocks.com
- **CMS**: Pages CMS (hosted service at pagescms.org)

---

## Jekyll Basics

### What is Jekyll?

Jekyll is a static site generator that transforms your plain text into a static website. It:
- Processes Markdown files
- Applies Liquid templates
- Generates HTML files
- Runs locally or on GitHub Pages

### Key Concepts

- **Posts**: Blog entries stored in `_posts/` with date-based filenames
- **Pages**: Static pages (like About, Contact) stored in root or `pages/`
- **Layouts**: Templates in `_layouts/` that wrap your content
- **Includes**: Reusable components in `_includes/`
- **Front Matter**: YAML metadata at the top of files (between `---`)

---

## Theme: Millennial

### Theme Features

The Millennial theme provides:
- **Home Layout**: Displays paginated blog posts
- **Post Layout**: Individual blog post pages with sharing, related posts
- **Page Layout**: Simple pages without blog features
- **Category Layout**: Archive pages for categories
- **Responsive Design**: Mobile-friendly
- **Social Sharing**: Built-in share buttons
- **Related Posts**: Automatically shows related content

### Theme Files Location

All theme files are **local** (copied into your repository):
- `_layouts/` - Page templates
- `_includes/` - Reusable components
- `_sass/` - Sass stylesheets
- `assets/` - CSS, images, fonts

The original theme is in `_themes/millennial/` but is not used directly.

---

## Creating Blog Posts

### File Naming Convention

Posts **must** follow this format:
```
YYYY-MM-DD-title-with-dashes.markdown
```

**Examples:**
- `2025-12-03-my-first-post.markdown` ✅
- `2025-12-03-my-first-post.md` ✅
- `my-first-post.markdown` ❌ (missing date)
- `2025-12-3-my-first-post.markdown` ❌ (day needs zero padding)

### Post Location

All posts go in the `_posts/` directory:
```
_posts/
  └── 2025-12-03-my-first-post.markdown
```

### Required Front Matter

Every post needs front matter at the top:

```yaml
---
layout: post
title: "Your Post Title"
date: 2025-12-03 14:30:00 -0500
categories: [category1, category2]
tags: [tag1, tag2, tag3]
---
```

### Optional Front Matter

```yaml
---
layout: post
title: "Your Post Title"
date: 2025-12-03 14:30:00 -0500
categories: [category1, category2]
tags: [tag1, tag2]
image: "image-filename.jpg"  # Image in assets/img/
author: "Author Name"        # If you want to show author
---
```

### Post Content

After the front matter, write your content in Markdown:

```markdown
---
layout: post
title: "My First Post"
date: 2025-12-03 14:30:00 -0500
categories: [blog]
tags: [jekyll, tutorial]
---

This is the beginning of my post. I can use **bold**, *italic*, and [links](https://example.com).

## Heading 2

I can also include code:

```ruby
def hello
  puts "Hello, World!"
end
```

And lists:
- Item 1
- Item 2
- Item 3
```

---

## Creating Pages

### Simple Page

Create a `.markdown` file in the root directory:

**File**: `contact.markdown`

```yaml
---
layout: page
title: Contact
permalink: /contact/
---

Write your contact information here.
```

### Page with Custom Layout

You can use the `post` layout for pages that need blog features:

```yaml
---
layout: post
title: "Special Page"
permalink: /special/
---

This page uses the post layout, so it has sharing buttons and related posts.
```

### Page Front Matter Options

```yaml
---
layout: page          # or "post"
title: "Page Title"
permalink: /page-url/ # URL path (trailing slash recommended)
---
```

**Note**: If you don't specify `permalink`, Jekyll will use the filename.

---

## Front Matter Reference

### Common Fields

| Field | Type | Description | Required |
|-------|------|-------------|----------|
| `layout` | string | Template to use (`post`, `page`, `home`) | Yes |
| `title` | string | Page/post title | Yes |
| `date` | datetime | Publication date (posts only) | Posts: Yes |
| `permalink` | string | Custom URL path | No |
| `categories` | array | Post categories | No |
| `tags` | array | Post tags | No |
| `image` | string | Featured image filename | No |

### Date Format

```yaml
date: 2025-12-03 14:30:00 -0500
# Format: YYYY-MM-DD HH:MM:SS TIMEZONE
```

Common timezones:
- `-0500` (EST)
- `-0800` (PST)
- `+0000` (UTC)

### Categories and Tags

```yaml
# Single category
categories: blog

# Multiple categories
categories: [blog, tutorial, jekyll]

# Tags (always array)
tags: [jekyll, github, pages]
```

---

## File Structure

```
stories-over-statblocks/
├── _config.yml          # Site configuration
├── _data/
│   └── settings.yml     # Theme settings (menu, social links)
├── _includes/           # Reusable components
│   ├── header.html      # Site header/navigation
│   ├── footer.html      # Site footer
│   ├── head.html        # HTML head section
│   └── ...
├── _layouts/            # Page templates
│   ├── default.html     # Base layout
│   ├── home.html        # Homepage layout
│   ├── post.html        # Blog post layout
│   └── page.html        # Static page layout
├── _posts/              # Blog posts
│   └── YYYY-MM-DD-title.markdown
├── _sass/               # Sass stylesheets
├── _site/               # Generated site (don't edit)
├── _themes/             # Original theme (reference only)
├── assets/              # Static assets
│   ├── css/            # Compiled CSS
│   └── img/            # Images
├── about.markdown       # About page
├── index.html           # Homepage
├── CNAME                # Custom domain
└── Gemfile              # Ruby dependencies
```

---

## Customization Guide

### Site-Wide Settings

Edit `_config.yml`:

```yaml
title: Stories Over Statblocks
description: Your site description
url: "https://storiesoverstatblocks.com"
baseurl: ""  # Empty for custom domain
```

### Theme Settings

Edit `_data/settings.yml`:

```yaml
# Navigation menu
menu:
- {name: 'About', url: '/about/'}
- {name: 'Contact', url: '/contact/'}

# Social media links
social:
- {icon: 'github', link: 'https://github.com/nmbr13'}
- {icon: 'twitter', link: 'https://twitter.com/username'}

# Disqus comments (optional)
disqus:
  comments: false
  disqus_shortname: ''

# Google Analytics (optional)
google-ID: ''
```

### Available Social Icons

Font Awesome icons are available. Common ones:
- `github`, `twitter`, `facebook`, `instagram`
- `linkedin`, `envelope`, `rss-square`
- See: https://fontawesome.com/v4/icons/

### Customizing Layouts

To customize a layout, copy it from `_themes/millennial/_layouts/` to `_layouts/` and edit.

**Example**: Customize the post layout:
1. Copy `_themes/millennial/_layouts/post.html` to `_layouts/post.html`
2. Edit `_layouts/post.html` to your needs
3. Jekyll will use your custom version

---

## Markdown Syntax Reference

### Headings

```markdown
# H1
## H2
### H3
#### H4
```

### Text Formatting

```markdown
**bold** or __bold__
*italic* or _italic_
***bold italic***
~~strikethrough~~
```

### Links

```markdown
[Link text](https://example.com)
[Link with title](https://example.com "Title")
```

### Images

```markdown
![Alt text](/assets/img/image.jpg)
![Alt text](/assets/img/image.jpg "Image title")
```

### Lists

```markdown
- Unordered item
- Another item
  - Nested item

1. Ordered item
2. Another item
```

### Code

```markdown
Inline `code`

```language
Code block
```
```

### Blockquotes

```markdown
> This is a blockquote
> It can span multiple lines
```

### Horizontal Rule

```markdown
---
```

---

## Jekyll Liquid Tags

### Site Variables

```liquid
{{ site.title }}           # Site title
{{ site.description }}     # Site description
{{ site.url }}             # Site URL
{{ site.baseurl }}         # Base URL
```

### Page Variables

```liquid
{{ page.title }}           # Page title
{{ page.date }}            # Page date
{{ page.url }}             # Page URL
{{ page.content }}         # Page content
```

### Filters

```liquid
{{ page.title | upcase }}              # Uppercase
{{ page.date | date: "%B %d, %Y" }}   # Format date
{{ "hello" | capitalize }}            # Capitalize
```

### Includes

```liquid
{% include header.html %}
{% include footer.html %}
{% include post-share.html %}
```

### Loops

```liquid
{% for post in site.posts %}
  <h2>{{ post.title }}</h2>
{% endfor %}
```

---

## Common Tasks

### Add a New Page

1. Create `new-page.markdown` in root
2. Add front matter:
   ```yaml
   ---
   layout: page
   title: "New Page"
   permalink: /new-page/
   ---
   ```
3. Add content in Markdown
4. (Optional) Add to menu in `_data/settings.yml`

### Add a New Post

1. Create file: `_posts/2025-12-03-my-post.markdown`
2. Add front matter with `layout: post`
3. Write content
4. Commit and push (or use Pages CMS)

### Add an Image to a Post

1. Upload image to `assets/img/`
2. Reference in front matter:
   ```yaml
   image: "my-image.jpg"
   ```
3. Or use in content:
   ```markdown
   ![Description](/assets/img/my-image.jpg)
   ```

### Change Site Title

Edit `_config.yml`:
```yaml
title: Your New Title
```

### Add Menu Item

Edit `_data/settings.yml`:
```yaml
menu:
- {name: 'Home', url: '/'}
- {name: 'About', url: '/about/'}
- {name: 'New Page', url: '/new-page/'}
```

---

## Troubleshooting

### Post Not Appearing

- Check filename format: `YYYY-MM-DD-title.markdown`
- Check date is not in the future
- Verify front matter has `layout: post`
- Rebuild: `bundle exec jekyll build`

### Page Not Found

- Check `permalink` in front matter
- Verify file is in correct location
- Check for typos in URL

### Styles Not Loading

- Verify `url` and `baseurl` in `_config.yml` are correct
- Check asset paths use `{{ site.url }}{{ site.baseurl }}`
- Clear browser cache

### Changes Not Showing

- Restart Jekyll server: `bundle exec jekyll serve`
- Clear `_site/` directory: `rm -rf _site`
- Rebuild: `bundle exec jekyll build`

---

## Local Development

### Start Server

```bash
bundle exec jekyll serve
```

Visit: http://localhost:4000

### Build Site

```bash
bundle exec jekyll build
```

Output goes to `_site/` directory.

### Watch for Changes

```bash
bundle exec jekyll serve --watch
```

Automatically rebuilds on file changes.

---

## Deployment

### GitHub Pages

1. Push to `main` branch
2. GitHub Actions builds automatically
3. Site updates in 1-2 minutes

### Custom Domain

- Domain: `storiesoverstatblocks.com`
- CNAME file: Contains domain name
- DNS: Points to GitHub Pages IPs

---

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Millennial Theme](https://github.com/LeNPaul/Millennial)
- [Pages CMS](https://pagescms.org)
- [Markdown Guide](https://www.markdownguide.org/)
- [Liquid Template Language](https://shopify.github.io/liquid/)

---

**Last Updated**: December 2025

