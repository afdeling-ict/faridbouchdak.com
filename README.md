# faridbouchdak.com

Personal site. Hugo + Cloudflare Pages. Bilingual (NL/EN).

## Stack

- **Generator**: Hugo (static site, multilingual)
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
├── config.toml                  # Hugo multilingual config (NL + EN)
├── i18n/
│   ├── nl.yaml                  # UI strings NL
│   └── en.yaml                  # UI strings EN
├── content/
│   ├── nl/                      # NL content (default language)
│   │   ├── _index.md
│   │   └── posts/
│   └── en/                      # EN content
│       ├── _index.md
│       └── posts/
├── layouts/
│   ├── index.html               # Homepage NL
│   ├── index.en.html            # Homepage EN
│   ├── _default/
│   │   ├── baseof.html          # Base HTML wrapper (lang-aware)
│   │   └── single.html          # Fallback single page
│   ├── posts/
│   │   ├── list.html            # Post list (NL + EN, one template)
│   │   └── single.html          # Post page (NL + EN, one template)
│   └── partials/
│       ├── nav.html             # Nav (NL + EN)
│       ├── footer.html          # Footer (NL + EN)
│       └── scripts.html         # Scroll + animation JS
└── static/
    ├── css/main.css
    ├── img/
    │   └── social-preview.png   # OG/Twitter Card image (1200×630)
    ├── robots.txt
    └── llms.txt
```

## Adding a new post

1. Create `content/nl/posts/[slug-nl].md` with `translationKey: "[key]"`
2. Create `content/en/posts/[slug-en].md` with the same `translationKey`
3. Hugo auto-links translations — language switcher works without extra config

## Languages

| URL | Content |
|-----|---------|
| `/` | Homepage NL |
| `/posts/` | Post list NL |
| `/en/` | Homepage EN |
| `/en/posts/` | Post list EN |
