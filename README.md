# Stories Over Statblocks

A minimalist Jekyll blog powered by the [Millennial theme](https://github.com/LeNPaul/Millennial) and [Decap CMS](https://decapcms.org/) for easy content management.

## Features

- 🎨 **Millennial Theme** - Clean, minimalist design focused on content
- 📝 **Decap CMS** - User-friendly admin interface for managing content
- 🚀 **GitHub Pages** - Automatic deployment via GitHub
- 📱 **Responsive** - Mobile-friendly design
- 🔍 **SEO Optimized** - Built-in SEO tags and sitemap generation
- 📡 **RSS Feed** - Automatic RSS feed generation

## Local Development

### Prerequisites

- Ruby 3.4+ (installed via Homebrew)
- Bundler gem

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/nmbr13/stories-over-statblocks.git
   cd stories-over-statblocks
   ```

2. **Install dependencies**
   ```bash
   bundle install
   ```

3. **Run the development server**
   ```bash
   bundle exec jekyll serve
   ```

4. **View your site**
   - Open [http://localhost:4000](http://localhost:4000) in your browser

## Content Management with Decap CMS

### Accessing the CMS

1. **For production (GitHub Pages):**
   - Visit: `https://nmbr13.github.io/stories-over-statblocks/admin/`
   - Authenticate with GitHub

2. **For local development:**
   - Uncomment `local_backend: true` in `admin/config.yml`
   - Run `npx netlify-cms-proxy-server` in a separate terminal
   - Visit: `http://localhost:4000/admin/`

### Managing Content

The CMS allows you to:
- ✏️ Create and edit blog posts
- 📄 Create and edit pages
- 🖼️ Upload images (stored in `assets/img/uploads/`)
- 🏷️ Manage categories and tags

## Project Structure

```
stories-over-statblocks/
├── _config.yml          # Jekyll configuration
├── _data/
│   └── settings.yml     # Theme settings (menu, social links, etc.)
├── _includes/           # Reusable components
├── _layouts/            # Page templates
├── _posts/              # Blog posts (YYYY-MM-DD-title.markdown)
├── _sass/               # Sass stylesheets
├── admin/               # Decap CMS files
│   ├── config.yml       # CMS configuration
│   └── index.html       # CMS entry point
├── assets/              # Static assets (CSS, images)
└── Gemfile              # Ruby dependencies
```

## Customization

### Site Settings

Edit `_config.yml` to customize:
- Site title and description
- Base URL
- Social media usernames
- Jekyll plugins

### Theme Settings

Edit `_data/settings.yml` to customize:
- Navigation menu items
- Social media links
- Disqus comments (if enabled)
- Google Analytics (if enabled)

### Adding Content

**Blog Posts:**
- Create files in `_posts/` with format: `YYYY-MM-DD-title.markdown`
- Or use Decap CMS at `/admin/`

**Pages:**
- Create `.markdown` files in the root directory
- Or use Decap CMS at `/admin/`

## Deployment

This site is configured for GitHub Pages:

1. **Enable GitHub Pages:**
   - Go to repository Settings → Pages
   - Select branch: `main`, folder: `/ (root)`
   - Save

2. **Your site will be live at:**
   - `https://nmbr13.github.io/stories-over-statblocks/`

3. **CMS Admin:**
   - `https://nmbr13.github.io/stories-over-statblocks/admin/`

## Technologies

- [Jekyll](https://jekyllrb.com/) - Static site generator
- [Millennial Theme](https://github.com/LeNPaul/Millennial) - Jekyll theme
- [Decap CMS](https://decapcms.org/) - Content management system
- [GitHub Pages](https://pages.github.com/) - Hosting

## License

This project uses the Millennial theme, which is licensed under the MIT License.

## Contributing

Feel free to submit issues or pull requests!

---

Built with ❤️ using Jekyll and GitHub Pages
