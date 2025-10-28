# Growthspan Blog

A modern blog built with [Hexo](https://hexo.io/) using the Clean Blog theme.

## Quick Start

### Installation

```bash
npm install
```

### Development

Start the local development server:

```bash
npm start
# or
npm run server
```

Your blog will be available at http://localhost:4000

### Creating Content

Create a new blog post:

```bash
hexo new post "My Post Title"
```

Create a new page:

```bash
hexo new page "page-name"
```

Posts are created in `source/_posts/` and support Markdown with front matter.

### Using the Visual Editor (Decap CMS)

This blog includes Decap CMS for a visual editing experience. Access it at:

**Production:** https://growthspan-blog.netlify.app/admin

**First Time Setup:**

1. Visit `/admin` on your deployed site
2. Click "Login with GitHub"
3. Authorize the application
4. Start creating and editing posts visually!

**Features:**
- Rich text editor with live preview
- Image upload and management
- Draft/publish workflow
- Edit site settings
- No need to use command line

### Building

Generate static files:

```bash
npm run build
```

Clean generated files:

```bash
npm run clean
```

## Deployment

This blog is configured for automatic deployment on Netlify. When you push to the master branch, Netlify will:

1. Install dependencies with `npm install`
2. Build the site with `npm run build`
3. Publish the `public/` directory

## Project Structure

```
.
├── _config.yml           # Main Hexo configuration
├── source/               # Content source files
│   ├── _posts/          # Blog posts
│   ├── about/           # About page
│   ├── tags/            # Tags page
│   └── categories/      # Categories page
├── themes/
│   └── clean-blog/      # Clean Blog theme
└── public/              # Generated site (git-ignored)
```

## Theme Customization

The Clean Blog theme can be customized by editing `themes/clean-blog/_config.yml`. You can configure:

- Menu items
- Cover images
- Social media links
- Comments (Disqus or Facebook)
- Google Analytics
- And more...

## Documentation

- [Hexo Documentation](https://hexo.io/docs/)
- [Clean Blog Theme](https://github.com/klugjo/hexo-theme-clean-blog)
- See `CLAUDE.md` for development guidance

## License

MIT
