# Ascend CRM — Website

Static marketing site for Ascend CRM. No build step, no dependencies — plain HTML, inline styles, and one small runtime file.

## Deploying to Vercel

1. Push this folder to a GitHub repository (it should be the **repository root**).
2. In Vercel: **Add New… → Project → Import** the repo.
3. Framework Preset: **Other**. Leave Build Command empty. Output Directory: leave empty (root).
4. Deploy.

`vercel.json` turns on `cleanUrls`, so `/about.html` is served at `/about`.

## Pages

| URL | File | Title |
| --- | --- | --- |
| `/` | `index.html` | Home |
| `/about` | `about.html` | About — Joshua Munoz |
| `/services` | `services.html` | Services overview |
| `/database-reactivation-system` | `database-reactivation-system.html` | Database Reactivation System |
| `/5-star-review-system` | `5-star-review-system.html` | 5-Star Review System |
| `/ai-employee` | `ai-employee.html` | 24/7 AI Employee |
| `/automated-referral-system` | `automated-referral-system.html` | Automated Referral System |
| `/meta-ads` | `meta-ads.html` | Meta Ads |
| `/full-crm-service` | `full-crm-service.html` | Full CRM Service |
| `/contact` | `contact.html` | Contact |
| `/book-strategy-call` | `book-strategy-call.html` | Book Your Free Strategy Call |

## Redirects

Old paths from the previous site are 301'd in `vercel.json`:

- `/revenue-revival` → `/database-reactivation-system`
- `/reputation-accelerator` → `/5-star-review-system`
- `/referral-growth-system` → `/automated-referral-system`
- `/call-booking-page` → `/book-strategy-call`
- `/home` → `/`

## Structure

```
├── index.html               # one file per page, self-contained
├── …
├── assets/                  # images, logo, photos
├── support.js               # small client runtime (required — do not remove)
├── vercel.json              # clean URLs, redirects, cache headers
├── robots.txt
└── sitemap.xml
```

## Domain

All canonical URLs, `og:url`, and the sitemap point at **https://www.ascendcrm.io**. If you deploy to a different domain, find-and-replace that string across the HTML files, `robots.txt`, and `sitemap.xml`.

## Editing

- **Copy and styles** live inline in each page's HTML — edit directly.
- **Repeated lists** (client logos, industries, service accordion) live in the `<script>` block at the bottom of each page.
- **Header, footer, and mobile menu** markup is duplicated per page. A change to nav or footer needs to be applied to all 11 files.
- **Images**: drop into `assets/` and reference as `/assets/filename.png`.

## Third-party embeds

- Booking calendar (`book-strategy-call.html`) — iframe from `link.ascendcrm.io`
- Hero and service videos — Vimeo players
- Testimonial videos — YouTube thumbnails linking out
