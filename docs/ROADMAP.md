# parkerferguson.xyz — Roadmap

> A living doc. Practical next steps up top, aspirational vision below.
> Update this as things ship or new ideas land.

---

## Phase 0: Deploy (Blocked — needs DNS)

- [ ] **Update DNS at Namecheap** (registrar-servers.com)
  - Change A record: `@` → `76.76.21.21`
  - Add CNAME: `www` → `cname.vercel-dns.com`
  - Add CNAME: `*` → `cname.vercel-dns.com` (wildcard for future subdomains)
  - Add TXT: `_vercel` → (check Vercel dashboard for verification string)
  - Remove old GitHub Pages A records (185.199.x.x)
- [ ] **Verify domain in Vercel dashboard** — will auto-provision SSL
- [ ] **Confirm site loads** at https://parkerferguson.xyz
- [ ] **Connect GitHub repo to Vercel** for auto-deploy on push
  - Vercel dashboard → Project → Settings → Git → connect Fluxuous/parkerferguson-dot-xyz
  - This replaces `vercel --prod` CLI deploys with push-to-deploy

---

## Phase 1: Content — The Bones

The scaffolding is built. These pages need real words.

### About Page
- [ ] Write the 10-second intro (who you are in one sentence)
- [ ] Write the 60-second version (career arc, what you care about, what makes you different)
- [ ] Write the full story (the winding path — Two Sigma, CoinDesk, startups, acquisitions, what you learned)
- [ ] Decide: photo or no photo? If yes, get a good one that feels human, not corporate
- [ ] Add social links (GitHub, Twitter/X, LinkedIn, Bluesky — whatever you actually use)
- [ ] Link to parkerferguson.co consulting site with brief context

### Now Page
- [ ] What are you building right now?
- [ ] What are you thinking about / obsessed with?
- [ ] What are you reading?
- [ ] Any personal stuff worth sharing? (location, life chapter, etc.)
- [ ] Set a reminder to update this monthly

### Projects Page
- [ ] Audit current projects — what's worth listing publicly?
- [ ] Write real descriptions for each (what it is, why it exists, what's interesting about it)
- [ ] Add links/repos where applicable
- [ ] Decide on status labels (active / shipped / archived / idea)
- [ ] Consider: do any projects deserve their own dedicated page with more detail?

### Blog
- [ ] Migrate existing "Depression.ai" post from old site?
- [ ] Write a proper first post (doesn't have to be long — could be "why this site exists")
- [ ] Brainstorm post ideas (see Ideas section below)
- [ ] Decide on publishing cadence — or explicitly decide there isn't one

### Links
- [ ] Seed with 5-10 interesting links you'd actually recommend
- [ ] Decide: is this a "link blog" (commentary on each) or a "bookmarks" feed (lightweight)?

---

## Phase 2: Polish — Make It Yours

### Design & Feel
- [ ] Color palette — the current indigo accent works but might want something more personal
- [ ] Decide on light/dark mode behavior (currently follows system preference)
- [ ] Consider a custom favicon beyond the "P" square
- [ ] Open Graph / social preview image — what shows when someone shares a link
- [ ] Overall vibe check: does it feel like *you* or like a template?

### Interactive Features
- [ ] Port the hover-preview system from the old .xyz site (the tooltip link previews)
- [ ] Reading time estimates on blog posts
- [ ] Table of contents for longer posts
- [ ] Code syntax highlighting theme that matches the site aesthetic

### SEO & Discovery
- [ ] Verify sitemap is generating correctly (already built, just verify)
- [ ] Submit sitemap to Google Search Console
- [ ] Add structured data / JSON-LD for person schema
- [ ] Verify RSS feed works in a reader
- [ ] Add canonical URLs for any cross-posted content

### Analytics
- [ ] Set up privacy-respecting analytics (Plausible, Fathom, or Vercel Analytics)
- [ ] No cookie banners needed if using privacy-first option

---

## Phase 3: Growth — Subdomains & Hosting One-Off Projects

The wildcard DNS (`*.parkerferguson.xyz`) is set up for this.

### Architecture Decisions
- [ ] How to route subdomains on Vercel (separate projects? or Vercel rewrites/middleware?)
- [ ] Template for spinning up a new subdomain project quickly
- [ ] Shared design tokens / components across subdomain projects? Or fully independent?

### Potential Subdomain Uses
- `demos.parkerferguson.xyz` — interactive demos, prototypes, proof-of-concepts
- `tools.parkerferguson.xyz` — small utilities you've built
- `lab.parkerferguson.xyz` — experiments, half-baked ideas
- Or per-project: `manifest.parkerferguson.xyz`, `[project].parkerferguson.xyz`

### When to Use Subdomains vs Subdirectories
- **Subdirectories** (`/projects/thing`) — content about a project, write-ups, case studies → builds main domain SEO
- **Subdomains** (`thing.parkerferguson.xyz`) — the actual running app/demo → separate deployment, separate stack

---

## Phase 4: Syndication & Outreach

### Cross-Posting Strategy
- [ ] Blog posts → syndicate to Medium, Dev.to, LinkedIn articles?
- [ ] Canonical URL always points back to parkerferguson.xyz
- [ ] RSS feed as the single source of truth

### Newsletter
- [ ] Worth it? Only if you'll actually write regularly
- [ ] If yes: Buttondown (simple, developer-friendly) or Substack (built-in audience)
- [ ] If no: RSS is enough for the people who care

### Social Presence
- [ ] Consistent bio/links across platforms pointing back to .xyz
- [ ] Share new posts/projects on social when they ship
- [ ] .xyz is the canonical "home" — everything else links back here

---

## Ideas Parking Lot

Stuff that might become blog posts, projects, or pages. No commitment, just capturing.

### Blog Post Ideas
- _Why I built this site (and what I learned about personal branding as someone who hates personal branding)_
- _The consulting model: one person, team-level output_
- _What 20 years in tech actually teaches you_
- _Agentic AI: what's real and what's hype_
- _Building in public vs. building in private_
- _(add more here)_

### Page Ideas
- `/uses` — tools, hardware, software stack (popular format, see uses.tech)
- `/reading` — books that shaped your thinking, with notes
- `/talks` — if you speak publicly, list them
- `/principles` — operating principles, how you think about decisions
- `/timeline` — visual career timeline (Karpathy-style)

### Feature Ideas
- Search across all content (Pagefind — static search, no server needed)
- Tag-based filtering across blog + projects + links
- "Related posts" at the bottom of blog entries
- Email signup for rare, high-signal updates
- Dark/light mode toggle (explicit, not just system preference)
- View count or "popular posts" section

---

## Reference

### Current Tech Stack
- **Framework**: Astro v5
- **Styling**: Tailwind CSS v3
- **Content**: Markdown/MDX via Astro Content Collections
- **Fonts**: Inter (body), JetBrains Mono (code)
- **Hosting**: Vercel
- **Repo**: github.com/Fluxuous/parkerferguson-dot-xyz

### Site Map (Current)
```
parkerferguson.xyz
├── /              Home (intro + recent projects + recent posts)
├── /about         Tiered bio (10s / 60s / full)
├── /now           What I'm doing right now
├── /projects      Showcase, grouped by status
├── /blog          Writing index, grouped by year
├── /blog/[slug]   Individual posts
├── /links         Curated interesting finds
├── /colophon      How this site is built
├── /rss.xml       RSS feed
└── /sitemap.xml   Auto-generated sitemap
```

### Design Inspirations
Sites researched during planning:
- **Patrick Collison** (patrickcollison.com) — 23+ thematic sections, curiosity as identity
- **Andrej Karpathy** (karpathy.ai) — timeline + projects, playful tone, "0 frameworks"
- **Derek Sivers** (sive.rs) — "me in 10 seconds", /now page, tiered engagement depth
- **Simon Willison** (simonwillison.net) — multiple content streams at different effort levels
- **Julia Evans** (jvns.ca) — 30+ topic categories, favorites as entry point
- **Chris Olah** (colah.github.io) — personal essays alongside technical work
- **Dan Abramov** (overreacted.io) — radical simplicity, post titles do the work
- **Gwern** (gwern.net) — knowledge archive, intellectual autobiography
- **Paul Graham** (paulgraham.com) — extreme minimalism, authority through restraint
