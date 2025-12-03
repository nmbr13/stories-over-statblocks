# Stories Over Statblocks

A minimalist Jekyll blog powered by the [Millennial theme](https://github.com/LeNPaul/Millennial) and [Decap CMS](https://decapcms.org/) for easy content management.

## Features

- 🎨 **Millennial Theme** - Clean, minimalist design focused on content
- 📝 **Pages CMS** - User-friendly admin interface for managing content (via pagescms.org)
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

## Content Management with Pages CMS

### Accessing the CMS

Pages CMS is a hosted service that connects directly to your GitHub repository. To use it:

1. **Visit Pages CMS:**
   - Go to: https://pagescms.org
   - Sign in with your GitHub account
   - Grant access to your `stories-over-statblocks` repository

2. **Start Editing:**
   - Select your repository
   - Browse and edit your content files
   - Changes are committed directly to GitHub

### Managing Content

Pages CMS allows you to:
- ✏️ Create and edit blog posts in `_posts/`
- 📄 Create and edit pages
- 🖼️ Upload and manage images
- 🏷️ Edit front matter (categories, tags, etc.)
- 📝 Edit any file in your repository

**Note:** Pages CMS works entirely through GitHub - no files need to be added to your repository. It's a web-based editor that connects to your GitHub repo.

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
- [Pages CMS](https://pagescms.org/) - Content management system for GitHub
- [GitHub Pages](https://pages.github.com/) - Hosting

## License

This project uses the Millennial theme, which is licensed under the MIT License.

## Contributing

Feel free to submit issues or pull requests!

---

Built with ❤️ using Jekyll and GitHub Pages
