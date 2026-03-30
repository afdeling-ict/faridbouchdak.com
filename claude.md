# Projectsamenvatting — faridbouchdak.com

## Context
Dit is een persoonlijk merkproject voor Farid Bouchdak. De centrale positionering: **"Ik bouw infrastructuur. Fysiek en digitaal."** — PPP-adviseur voor overheden én digitaal founder. De persoonlijke site is de spin in het web van alle andere domeinen.

---

## Tech stack
- **Generator:** Hugo (statische site, Markdown-content, output naar `public/`)
- **Hosting:** Cloudflare Pages
- **Repository:** GitHub — organisatie `afdeling-ict`, repo `faridbouchdak.com`
- **Deploy:** automatisch bij elke push naar `main`
- **Domein:** `faridbouchdak.com` gekoppeld via Cloudflare Custom Domains

---

## Sitemap & URL-structuur

| URL | Inhoud |
|---|---|
| `/` | Homepage NL |
| `/posts/` | Blogoverzicht NL |
| `/posts/waarom-ik-twee-werelden-bouw/` | Post 1 NL — translationKey: "two-worlds" |
| `/posts/p3nomads-het-verhaal/` | Post 2 NL — translationKey: "p3nomads-story" |
| `/en/` | Homepage EN |
| `/en/posts/` | Blogoverzicht EN |
| `/en/posts/why-i-build-in-two-worlds/` | Post 1 EN — translationKey: "two-worlds" |
| `/en/posts/p3nomads-the-story/` | Post 2 EN — translationKey: "p3nomads-story" |

---

## Bestandsstructuur

```
faridbouchdak/
├── config.toml                            # Hugo multilingual config ([languages.nl] + [languages.en])
├── i18n/
│   ├── nl.yaml                            # UI-strings NL (Notities, Projecten, etc.)
│   └── en.yaml                            # UI-strings EN (Notes, Projects, etc.)
├── content/
│   ├── nl/                                # contentDir voor NL (default taal)
│   │   ├── _index.md
│   │   └── posts/
│   │       ├── waarom-ik-twee-werelden-bouw.md   # translationKey: "two-worlds"
│   │       └── p3nomads-het-verhaal.md           # translationKey: "p3nomads-story"
│   └── en/                                # contentDir voor EN
│       ├── _index.md
│       └── posts/
│           ├── why-i-build-in-two-worlds.md      # translationKey: "two-worlds"
│           └── p3nomads-the-story.md             # translationKey: "p3nomads-story"
├── layouts/
│   ├── index.html                         # Homepage NL template
│   ├── _default/
│   │   ├── baseof.html                    # HTML wrapper — taal via .Language.Lang
│   │   └── single.html                   # Fallback single pagina
│   ├── posts/
│   │   ├── list.html                      # Blogoverzicht NL + EN (één template, i18n)
│   │   └── single.html                   # Artikelpagina NL + EN (één template, i18n + .Translations)
│   ├── index.en.html                      # Homepage EN (standalone HTML, Hugo multilingual lookup)
│   └── partials/
│       ├── nav.html                       # Nav NL + EN (één partial, taaldetectie + .Translations)
│       ├── footer.html                    # Footer NL + EN (i18n tagline)
│       └── scripts.html                   # Scroll + animatie JS
└── static/
    ├── css/main.css
    ├── img/
    │   └── social-preview.png             # OG/Twitter Card preview (1200×630)
    ├── _headers                           # Cloudflare Pages HTTP security headers (HSTS, CSP, COOP, X-Frame)
    ├── robots.txt                         # Crawler instructies incl. AI bots
    └── llms.txt                           # LLM/AI crawler optimization
```

---

## Design

- **Stijl:** Work.co geïnspireerd — strak, typografisch, geen visueel lawaai
- **Fonts:** DM Serif Display (display) + DM Mono (body/ui)
- **Kleurenpalet:** `#f5f4f0` achtergrond, `#0a0a0a` tekst, `#6b6b6b` muted, `#d8d5cf` lijnen
- **Cursor:** crosshair door hele site
- **Animaties:** fadeUp bij page load, scroll-reveal via IntersectionObserver
- **Nav:** fixed, blur-on-scroll (`backdrop-filter`) na 20px scrollen
- **Responsive:** breakpoints op 1024px, 768px, 480px, 360px — volledig uitgewerkt

## SEO / GEO / AI-optimalisatie

- **hreflang:** aanwezig op alle pagina's — NL/EN + x-default
- **Schema.org JSON-LD:** `Person` op homepages, `Article` op postpagina's
- **Open Graph:** title, description, type, url, locale, image (1200×630)
- **Twitter Card:** `summary_large_image` op alle pagina's
- **robots.txt:** `/static/robots.txt` — AI bots expliciet toegestaan
- **llms.txt:** `/static/llms.txt` — machine-readable siteoverzicht voor LLMs
- **Sitemap:** Hugo genereert automatisch `/sitemap.xml` bij elke build
- **Social preview:** `/static/img/social-preview.png` — vervangen door eigen afbeelding indien gewenst

---

## Andere domeinen — strategie (nog niet uitgevoerd)

| Domein | Status | Plan |
|---|---|---|
| `p3nomads.com` | Actief, revenue | Prijs verhogen naar €750-950, in-company variant toevoegen (€4.500-6.500), "884 days" counter verwijderen |
| `afdeling-ict.nl` | Rebranding bezig (apart Claude project) | Vaste maandpakketten introduceren |
| `askfoundersanything.com` | Shell, waitlist | Beslissing vereist: bouwen (Claude API integreren) óf verkopen als domein |
| `legoggles.com` | Skeleton | Affiliate SEO — VR niche, Amazon/Bol.com affiliate |
| `stickynotes.club` | Actief | Live domein — in gebruik op de site |
| `bouchdak.com` | E-mail only | Cloudflare Redirect Rule → `faridbouchdak.com` (301, al ingesteld) |

---

## Nieuwe post toevoegen (werkwijze na multilingual migratie)

1. Maak `content/nl/posts/[slug-nl].md` aan met `translationKey: "[unieke-key]"`
2. Maak `content/en/posts/[slug-en].md` aan met dezelfde `translationKey`
3. Hugo koppelt vertalingen automatisch — taalwisselknop in nav en post-footer werkt zonder extra configuratie

---

## Openstaande taken

1. **askfoundersanything.com** beslissing nemen: bouwen (Claude API integreren) óf verkopen als domein
2. **p3nomads.com** prijsstrategie doorvoeren — prijs verhogen naar €750-950, in-company variant toevoegen (€4.500-6.500)

---

## Werkwijze
Wijzigingen doorvoeren in bestaande map → GitHub Desktop → committen → pushen → Cloudflare bouwt automatisch.