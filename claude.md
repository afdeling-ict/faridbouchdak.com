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
| `/posts/waarom-ik-twee-werelden-bouw/` | Eerste post NL |
| `/en/` | Homepage EN |
| `/en/posts/` | Blogoverzicht EN |
| `/en/posts/why-i-build-in-two-worlds/` | Eerste post EN |

---

## Bestandsstructuur

```
faridbouchdak/
├── config.toml
├── content/
│   ├── _index.md                          # Homepage NL
│   ├── posts/
│   │   └── waarom-ik-twee-werelden-bouw.md
│   └── en/
│       ├── _index.md                      # Homepage EN
│       └── posts/
│           └── why-i-build-in-two-worlds.md
├── layouts/
│   ├── index.html                         # Homepage NL template
│   ├── _default/
│   │   ├── baseof.html                    # HTML wrapper + scroll JS
│   │   └── single.html                   # Fallback single pagina
│   ├── posts/
│   │   ├── list.html                      # Blogoverzicht NL
│   │   └── single.html                   # Artikelpagina NL
│   ├── en/
│   │   ├── list.html                      # Homepage EN (standalone HTML)
│   │   └── posts/
│   │       ├── list.html                  # Blogoverzicht EN
│   │       └── single.html               # Artikelpagina EN
│   └── partials/
│       ├── nav.html                       # Nav NL
│       ├── nav-en.html                    # Nav EN
│       └── footer.html
└── static/
    ├── css/main.css
    └── img/fb-logo.png
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

## Openstaande taken

1. **Volgende blogpost** schrijven — systeem staat klaar, alleen nieuw `.md` bestand toevoegen aan `content/posts/` en `content/en/posts/`
2. **Homepage updaten** met "Notities" sectie of recente post preview
3. **stickynotes.club** — domein correct ingesteld op de site
4. **askfoundersanything.com** beslissing nemen: bouwen of verkopen
5. **p3nomads.com** prijsstrategie doorvoeren

---

## Werkwijze
Wijzigingen doorvoeren in bestaande map → GitHub Desktop → committen → pushen → Cloudflare bouwt automatisch.