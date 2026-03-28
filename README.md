<div align="center">

<img src="https://raw.githubusercontent.com/webhousecode/cms/main/logo/webhouse.app-dark.svg" alt="webhouse.app" width="240" />

<br /><br />

# Next.js Boilerplate

**Next.js 16 + React 19 + Tailwind CSS v4 starter template powered by [webhouse.app](https://webhouse.app)** — filesystem adapter, server components, full SEO.

[![Built with webhouse.app](https://img.shields.io/badge/built%20with-webhouse.app-F7BB2E?style=for-the-badge)](https://webhouse.app)
&nbsp;
[![npm](https://img.shields.io/badge/@webhouse/cms-npm-CB3837?style=for-the-badge&logo=npm)](https://www.npmjs.com/package/@webhouse/cms)

</div>

---

## About

A production-ready Next.js starter template built on **[@webhouse/cms](https://github.com/webhousecode/cms)**. Content is stored as JSON files on the filesystem and rendered with React Server Components. Includes blocks, richtext, maps, dark mode, and full SEO out of the box.

### Key Features

- **App Router** — Next.js 16 with React Server Components by default
- **Blocks** — Hero sections, feature grids, and call-to-action blocks
- **Richtext** — Markdown content rendered with [react-markdown](https://github.com/remarkjs/react-markdown)
- **Maps** — OpenStreetMap/Leaflet embeds from `map` fields
- **SEO** — `generateMetadata` from `_seo` fields, JSON-LD, OpenGraph, sitemap, robots.txt
- **Dark mode** — CSS `prefers-color-scheme` with manual toggle in the navbar
- **Sitemap + robots.txt** — auto-generated from content

## Quick Start

```bash
# Clone this boilerplate
git clone https://github.com/webhousecode/nextjs-boilerplate.git my-site
cd my-site

# Install dependencies
npm install

# Start the dev server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to see your site.

## Project Structure

```
cms.config.ts              # Collections, blocks, and field definitions
src/
  app/
    layout.tsx             # Root layout (navbar, footer, theme)
    page.tsx               # Homepage (reads pages/home.json)
    [slug]/page.tsx        # Dynamic pages (about, contact, etc.)
    blog/
      page.tsx             # Blog listing
      [slug]/page.tsx      # Blog post detail
    sitemap.ts             # Auto-generated sitemap.xml
    robots.ts              # robots.txt
    globals.css            # Tailwind v4 imports + theme + prose
  components/
    article-body.tsx       # Richtext renderer (react-markdown)
    block-renderer.tsx     # Hero, Features, CTA blocks
    navbar.tsx             # Responsive navigation + theme toggle
    footer.tsx             # Site footer
    map-embed.tsx          # OpenStreetMap via Leaflet
  lib/
    content.ts             # getCollection(), getDocument(), readGlobal()
content/
  global/global.json       # Site title, nav links, footer
  pages/
    home.json              # Homepage
    about.json             # About page
    contact.json           # Contact page with map
  posts/
    getting-started.json   # Sample blog post
    using-blocks.json      # Sample blog post
public/
  uploads/                 # Media files (images, PDFs)
```

## Collections

| Collection | Description | Fields |
|-----------|-------------|--------|
| **global** | Site-wide settings | Site title, meta description, navigation links, footer text |
| **pages** | Static pages | Title, block sections (hero/features/CTA), richtext, map, SEO |
| **posts** | Blog posts | Title, excerpt, richtext content, date, author, cover image, tags |

## How It Works

| | |
|---|---|
| **Content** | JSON files in `content/` — edit manually or use the [webhouse.app](https://webhouse.app) admin UI |
| **Rendering** | React Server Components read content via `fs` at build/request time |
| **Routing** | App Router with `generateStaticParams` for static generation |
| **SEO** | `generateMetadata` exports per page, JSON-LD for blog posts and pages |
| **Styling** | Tailwind CSS v4 with `@theme` directive in `globals.css` — no tailwind.config.ts |

## Tech Stack

| Layer | Technology |
|-------|-----------|
| CMS | [@webhouse/cms](https://www.npmjs.com/package/@webhouse/cms) |
| Framework | [Next.js 16](https://nextjs.org/) + [React 19](https://react.dev/) |
| Styling | [Tailwind CSS v4](https://tailwindcss.com/) |
| Markdown | [react-markdown](https://github.com/remarkjs/react-markdown) + [remark-gfm](https://github.com/remarkjs/remark-gfm) |
| Language | TypeScript |

## Scripts

```bash
npm run dev       # Start development server
npm run build     # Production build
npm start         # Start production server
npm run lint      # Run ESLint
```

## Deployment

Works with any Next.js hosting provider:

- **Vercel** — `npx vercel` (zero config)
- **Netlify** — connect repo, build command `npm run build`
- **Docker** — add `output: "standalone"` to `next.config.ts`, use a Dockerfile
- **Fly.io** — Dockerfile + `fly.toml` with `primary_region = "arn"`

## Managing Content with webhouse.app

Instead of editing JSON files by hand, use the **webhouse.app admin UI**:

```bash
npx @webhouse/cms-admin-cli
```

This launches a local admin interface where you can visually edit pages, posts, and blocks. Changes are saved back to your `content/` directory as JSON files.

---

<div align="center">

**[webhouse.app](https://webhouse.app)** — the CMS that builds itself.

<sub>[@webhouse/cms](https://github.com/webhousecode/cms) &middot; [npm](https://www.npmjs.com/package/@webhouse/cms) &middot; [docs](https://github.com/webhousecode/cms/tree/main/docs/ai-guide)</sub>

</div>
