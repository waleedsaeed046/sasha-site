
# Sasha Nexus — Next.js Site

A production-ready multi-page website for **Sasha Nexus** built with Next.js (App Router), TypeScript, Tailwind, and a Markdown blog. Includes SEO metadata, sitemap/robots, and a contact form wired to send emails via **Resend** with optional **HubSpot CRM** integration.

## Quickstart

```bash
pnpm i   # or npm i / yarn
cp .env.example .env
pnpm dev # http://localhost:3000
```

- Update `NEXT_PUBLIC_SITE_URL` in `.env` when deploying.
- Put your Resend key in `.env` to enable email sending.
- (Optional) Add a HubSpot Private App access token to also create leads.

## Commands

- `pnpm dev` — run locally
- `pnpm build` — production build
- `pnpm start` — start production server

## Blog

- Markdown posts live in `content/blog/*.md` with frontmatter: `title`, `date`, `excerpt`, `tag`.
- Create a new post: `content/blog/my-post.md` and it will appear on `/blog`.

## Contact Form (Email + CRM)

- API route: `app/api/contact/route.ts`
- Uses **Resend** to email submissions to `RESEND_TO_EMAIL`.
- If `HUBSPOT_ACCESS_TOKEN` is present, it also creates/updates a contact.

## Theming & Brand

- Replace `/public/logo.png` with your official logo (already imported from the image you provided).
- Edit brand text and links in `lib/site.ts`.
- Global styles live in `app/globals.css`.

## Deploy

- Vercel (recommended): import the repo, set environment variables, deploy.
- PM2/Docker: `pnpm build && pnpm start` behind a reverse proxy (Nginx/Caddy).
- Don’t forget to set `NEXT_PUBLIC_SITE_URL` for correct Open Graph / sitemap links.
