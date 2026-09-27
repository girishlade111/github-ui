# GitHub UI Clone

A **GitHub repository page UI clone** — a faithful recreation of GitHub's repo interface (file explorer, issues, pull requests, actions, projects, wiki, settings pages) built with Next.js 14, Tailwind CSS, and shadcn/ui. Pure front-end mock: all data is local, no API calls, no backend.

## What it does

Recreates the full GitHub repository browsing experience as static pages:

- **Code tab** — file explorer with breadcrumb navigation, README section, repo sidebar (about, releases, contributors)
- **Issues tab** — issue list with labels, assignees, and state filters
- **Pull requests tab** — PR list with branch and status info
- **Actions tab** — workflow run list UI
- **Projects tab** — project board view
- **Wiki tab** — wiki page layout
- **Settings tab** — repository settings form UI
- **GitHub header** — global nav with search bar, notifications, profile menu
- **Dark/light mode** with GitHub-accurate color tokens

## Features

- ✅ Multi-page app with GitHub's exact tab structure
- ✅ Interactive file explorer (folders expand, breadcrumb trail)
- ✅ Issue/PR lists with filter chips and label badges
- ✅ Fully responsive layout (mobile → desktop)
- ✅ Dark mode via `next-themes`
- ✅ Static-site friendly — exports to pure HTML/CSS/JS

## Tech stack

| Layer | Tech |
|---|---|
| Framework | Next.js 14 (App Router) |
| UI | React 18, shadcn/ui (Radix primitives), Tailwind CSS v4 |
| Icons | lucide-react |
| Fonts | Geist, JetBrains Mono |
| Theming | next-themes |
| Language | TypeScript |

## Quick start

```bash
# 1. Install dependencies
npm install

# 2. Run the dev server
npm run dev
# open http://localhost:3000
```

```bash
# Production build (static export)
npm run build
# output lands in ./out — serve it with any static host
npx serve out
```

## Project structure

```
github-ui/
├── app/
│   ├── page.tsx            # Redirects to /code
│   ├── layout.tsx          # Root layout: fonts, header, theme
│   ├── code/page.tsx       # Code tab — file explorer + README + sidebar
│   ├── issues/page.tsx     # Issues tab
│   ├── pull-requests/      # Pull requests tab
│   ├── actions/page.tsx    # Actions tab
│   ├── projects/page.tsx   # Projects tab
│   ├── wiki/page.tsx       # Wiki tab
│   ├── settings/page.tsx   # Settings tab
│   └── globals.css
├── components/
│   ├── github-header.tsx       # Global top nav
│   ├── repository-header.tsx   # Repo title + tab bar (active tab from path)
│   ├── file-explorer.tsx       # File tree with breadcrumbs
│   ├── readme-section.tsx      # README preview panel
│   ├── repository-sidebar.tsx  # About / releases / contributors
│   ├── theme-provider.tsx
│   └── ui/                     # shadcn/ui primitives
├── lib/utils.ts
├── public/                     # Static assets
└── next.config.mjs            # output: 'export' for static hosting
```

## Environment variables

None required. All data is mocked locally in the components.

## Deployment

- **GitHub Pages:** a static build is published from the `gh-pages` branch —
  https://girishlade111.github.io/github-ui/
- **Any static host** (Vercel, Netlify, Cloudflare Pages): run `npm run build` and serve the `out/` directory.

> Note: this repo is deployed at the `/github-ui/` subpath, so `next.config.mjs` sets
> `basePath: '/github-ui'`. If you deploy it at a domain root (e.g. Vercel), remove the
> `basePath` line.

## Credits

Built by Girish Lade — https://ladestack.in

Originally generated with [v0.app](https://v0.app) and refined into a standalone static project.
