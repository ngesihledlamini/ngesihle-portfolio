# Project context

Personal portfolio site for Ngesihle Dlamini, built for the FlyRank Front-End Engineering internship (Week 3, Assignment 2: Foundations). The developer is a beginner: explain briefly what you change and why, and keep changes small. Work on one step at a time.

## Stack
- Next.js (App Router), TypeScript, `src/` directory, alias `@/*`
- Tailwind CSS v4 (tokens in `@theme` in `src/app/globals.css`, no tailwind.config file)
- Deployment: Vercel, connected to GitHub. Every push must build and produce a preview URL.

## Rules
- Server Components by default. Add `"use client"` only for interactivity (currently only `MobileMenu.tsx`).
- Use design tokens only (`bg-brand`, `text-muted`, `bg-surface`, `text-ink`, `rounded-card`), never hard-coded hex values in components.
- In dynamic routes, `params` is a Promise: `const { slug } = await params;`
- Only `NEXT_PUBLIC_` env vars reach the browser. Never commit `.env.local` or any secret. Keep `.env.example` updated with names only.
- Responsive at 375px and 1280px, no horizontal scroll. Wrap wide content (e.g. `<pre>`) in `overflow-x-auto`.
- `npm run build` must pass with zero errors before any commit.
- Conventional commit messages (`feat:`, `fix:`, `chore:`).

## Screens (the spec)
| Screen | Route |
|---|---|
| Home | `/` |
| About | `/about` |
| Projects | `/projects` |
| Project detail | `/projects/[slug]` |
| Contact | `/contact` |
| Health check | `/health` |

## Structure
src/app/{layout.tsx, page.tsx, about, projects, projects/[slug], contact, health}
src/components/{Header.tsx (Server), MobileMenu.tsx (Client)}
src/lib/nav.ts (single navLinks array shared by Header and MobileMenu)

## Env vars
NEXT_PUBLIC_SITE_NAME=Ngesihle Dlamini
API_BASE_URL=https://jsonplaceholder.typicode.com

## Assignment requirements
1. Routed placeholder page for every screen, root layout, navigation.
2. Tailwind and base design tokens.
3. Vercel connected, preview deploys on every push, env var structure set up.
4. `/health`: Server Component, fetches `${process.env.API_BASE_URL}/todos/1` with `cache: "no-store"`, renders status and data.
5. Deliverable: live preview URL plus repo link.

Evaluation: preview URL loads with no build errors; every spec screen exists as a route; responsive at 375px and 1280px; no secrets in the repo.

## Progress
- [x] Step 1: project scaffolded and pushed to GitHub
- [ ] Step 2: placeholder pages for all routes
- [ ] Step 3: `nav.ts`, `Header.tsx`, `MobileMenu.tsx`, wired into `layout.tsx`
- [ ] Step 4: design tokens in `globals.css`
- [ ] Step 5: `/health` page, `.env.local`, `.env.example`
- [ ] Step 6: `npm run build`, connect Vercel, add env vars in Vercel
- [ ] Step 7: test preview branch, run checklist, README with Screens section, submit