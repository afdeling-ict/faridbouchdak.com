# faridbouchdak.com

Personal site. Hugo + Cloudflare Pages.

## Stack
- **Generator**: Hugo (static site)
- **Hosting**: Cloudflare Pages
- **Deploy**: Auto-deploy on push to `main`

## Local development

```bash
# Install Hugo (if not installed)
brew install hugo          # macOS
# or: https://gohugo.io/installation/

# Run dev server
hugo server -D

# Build
hugo
# Output → public/
```

## Cloudflare Pages settings

| Setting           | Value    |
|-------------------|----------|
| Build command     | `hugo`   |
| Build output dir  | `public` |
| Production branch | `main`   |

## Structure

```
faridbouchdak/
├── config.toml           # Site config
├── content/
│   └── _index.md         # Homepage content
├── layouts/
│   ├── index.html        # Homepage template
│   ├── _default/
│   │   ├── baseof.html   # Base HTML wrapper
│   │   └── single.html   # Single page template
│   └── partials/
│       ├── nav.html
│       └── footer.html
└── static/
    └── css/
        └── main.css      # All styles
```

## Adding content

To update projects or text: edit `layouts/index.html` directly.
For future blog posts: add `.md` files to `content/posts/`.
