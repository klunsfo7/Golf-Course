# Chatuge Shores Golf Course — Website

A brand-new, modern, responsive **multi-page** marketing website for **Chatuge Shores Golf Course** in Hayesville, NC, rebuilt from the content of the existing site (`chatugeshoresgolf.com`).

It is a fast, dependency-free **static site** (plain HTML, CSS, and JavaScript) — no build step, no framework, easy to host anywhere.

## Pages

| File | Page |
|------|------|
| `index.html` | Home (hero, amenities, quick links, calls to action) |
| `course.html` | The Course + scorecard, ratings, slope & yardages |
| `rates.html` | Rates + online booking |
| `membership.html` | Membership & leagues |
| `instruction.html` | Golf instruction (lessons with Don Cathy) |
| `outings.html` | Tournaments & outings |
| `staff.html` | Meet the staff (with real photos) |
| `careers.html` | Careers / employment |
| `contact.html` | Contact & directions (embedded map) |

## Features

- Modern, mobile-first responsive design with a golf/mountain-lake theme
- Shared sticky navigation with a **Book Tee Time** button and click-to-call
- Active-page highlighting in the nav, animated mobile menu, scroll-reveal animations
- **Online booking** wired throughout to the course's TeeItUp page
- Real staff photos pulled from the original website
- Embedded Google Map + one-tap directions on the Contact page
- Accessible (skip link, semantic landmarks, keyboard-friendly menu, reduced-motion support)
- SEO-ready: per-page titles/descriptions, Open Graph tags, and `GolfCourse` structured data

## Project structure

```
golf_Course/
├── index.html, course.html, rates.html, membership.html,
│   instruction.html, outings.html, staff.html, careers.html, contact.html
├── styles/style.css     # Design system + responsive styles
├── scripts/main.js      # Nav, mobile menu, active link, scroll reveal
├── assets/
│   ├── logo.png (official logo), favicon.svg, hero.svg,
│   │   course-map.png, course-layout.png
│   └── staff/           # bill, tom, claudia, mel, ariel (real photos)
└── README.md
```

## Booking link

The **Book Tee Time** buttons point to the course's live booking page:

```
https://chatuge-shores-golf-course.book.teeitup.com/?course=8101
```

The date is intentionally left off so it always defaults to the current day.

## Run it locally

```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000
```

Or just open `index.html` in a browser (all navigation is relative, so it works from the file system too).

## Deploy

Because it is static, you can drop it on any host:

- **Netlify / Vercel / Cloudflare Pages** — drag-and-drop the folder or connect the repo
- **GitHub Pages** — push and enable Pages on the branch
- **Traditional hosting** — upload the folder via FTP to your web root

## Content notes / things to confirm

All copy was taken from the current website and reviewed for accuracy:

- **Video lessons removed.** The old site listed "video lessons" under instruction; per the course, that isn't offered, so the Lessons page now covers full swing and short game only.
- **Rates** — the original site published rates as images without machine-readable prices. The Rates page is laid out and directs visitors to the live online booking page (which always shows current pricing) or to call. Drop in exact dollar amounts anytime if you'd prefer them listed on-page.
- **Staff** — photos and bios reflect the current site (Bill Rinaldo, Tom Legate, Claudia Rinaldo, Mel Buckingham, Ariel Thompson). Update as the team changes.
- **Contacts** — Course: `828-389-8940`, `chatugeshoresgolf@gmail.com`; Instruction (Don Cathy): `678-642-0346`.

## Customizing

- **Colors & fonts:** edit the CSS variables at the top of `styles/style.css` (`:root`).
- **Swap the hero background:** replace `assets/hero.svg` (used by the home hero and every interior page banner) with real course photography (a wide `.jpg` works too — just update the `url(...)` in the `.hero-media` / `.page-banner::before` rules).
- **Add/rename pages:** copy an existing page, update the `<main>` content, and add a link to the shared nav in each page's header.

## Adding drone footage & course photos (the media package)

The home hero is already wired for an **aerial drone flyover video**:

1. Export the video as `assets/flyover.mp4` (and, ideally, `assets/flyover.webm` for smaller file size / broad support). Keep it short (15–30s), muted-friendly, and ~1080p.
2. In `index.html`, find the `DRONE FLYOVER READY` comment in the hero and remove the `<!-- ... -->` wrapper around the `<video>` element.
3. That's it — the video autoplays muted, loops behind the headline, and falls back to the mountain artwork (`hero.svg`) as its poster while it loads or on unsupported devices.

Tips for best results:
- Keep the video subtle and slow-moving so the headline stays readable.
- Provide `flyover.webm` (VP9/AV1) in addition to `flyover.mp4` (H.264) for the best size/quality/compatibility trade-off.

**Course photo gallery:** the layout is ready to add a photo gallery section (e.g. on the home page or a new `gallery.html`). Once aerial/course photos are shot, they can be dropped into `assets/gallery/` and displayed in a responsive grid — ask and this can be wired up.
# Golf-Course
