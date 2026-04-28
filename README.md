# Leela Vigil Solutions — Single HTML Website

Everything is in **one file**: `index.html`. All images are bundled in the `images/` folder.

---

## How to use

### Option 1 — Open locally
Double-click `index.html` → opens in your browser. Done.

### Option 2 — Upload to ANY web host
Works on every web host because there's no server / database / build step:

| Host | How |
|---|---|
| **Cloudflare Pages** | Sign in → Workers & Pages → Create → Pages → **Upload assets** → drag the entire folder. Live in 30 sec. |
| **Netlify** | Open https://app.netlify.com/drop → drag the folder. Instant URL. |
| **GitHub Pages** | Push folder to a repo → Settings → Pages → enable. |
| **Hostinger / GoDaddy / Bluehost / cPanel** | FTP / File Manager → upload the folder contents into `public_html/`. |
| **Firebase Hosting** | `firebase init hosting` → `firebase deploy`. |
| **Any shared hosting** | Just upload `index.html` + `images/` folder via FTP. |

---

## What's inside

```
leela-vigil-html/
├── index.html          ← entire website (HTML + inline CSS + inline JS)
└── images/
    ├── logo.jpeg
    ├── hero-bg.png
    ├── service-cctv.png
    ├── service-lan.png
    ├── service-biometric.png
    ├── service-fire.png
    ├── service-door.png
    ├── service-shutter.png
    └── service-motion.png
```

---

## Features included

- Same dark navy + neon green/cyan theme
- Header with logo, navigation, "Get Quote" CTA
- Hero with surveillance-camera HUD (radar, scan-lines, REC indicator, corner brackets)
- Stats row (6+ years, 500+ sites, 24/7, 99.9%)
- Animated client marquee
- About section with 4 feature cards
- 7 service cards with hover-lift effect, each opens its own detail page
- Each service detail page: hero, tagline, features, use cases, embedded quote form, "Other services" + **Back to home** button
- Contact section with email, phones, address, **office hours Mon–Sat 9:30 AM – 6:30 PM, Sunday Closed**
- Quote form that opens **WhatsApp** (+91 63625 54499) AND your **email app** (to contact@leelavigils.com & leelavigils@gmail.com) with everything pre-filled
- Floating WhatsApp button with radar pulse animation
- Hash-based routing: `index.html#service/cctv-surveillance` works

Only external dependencies (loaded from CDN, need internet first time):
- Google Fonts (Space Grotesk, Manrope, JetBrains Mono)
- Font Awesome icons

If you need a fully offline version, let me know — I can swap fonts to system fallbacks.

---

## How to edit content

Open `index.html` in any text editor (Notepad, VS Code, anything). Use Find & Replace:

| Find                           | Replace with                       |
|--------------------------------|------------------------------------|
| `916362554499`                 | Your WhatsApp number (no +/spaces) |
| `+91 97436 26883`, `+91 63625 54499`, `+91 99800 91299` | Your phones |
| `contact@leelavigils.com`      | Your email                         |
| `leelavigils@gmail.com`        | Your second email                  |
| `22 Chikkaharadanahalli, Jayanagar, Mysuru, Karnataka — 570034` | Your address |
| `9:30 AM – 6:30 PM`            | Your office hours                  |
| `Bharath Kumar CM`, `Arjun J`  | Owner names                        |

To change service text:
- Search for `const SERVICES = [` in the file
- Each entry has `title`, `short`, `tagline`, `overview`, `features`, `useCases` — edit the strings.

To change images:
- Replace files in `images/` folder, keeping the same filenames.

To change theme colors:
- Search for `--neon-green: #00ff9c;` near the top of the file → change to your brand color.
- Same for `--neon-cyan: #00cfff;`.

---

## Form submission — how it works

When a visitor submits the quote form:
1. **WhatsApp** opens in a new tab with the message pre-filled — they tap Send.
2. **Their email app** opens with `contact@leelavigils.com` and `leelavigils@gmail.com` as recipients, subject and body pre-filled — they tap Send.

Because this is a static site (no server), the visitor has to actually hit Send in WhatsApp/email. If you want **automatic background submission** to email/database, you need either:
- The full-stack version (FastAPI + MongoDB + Resend) — separate zip
- A free form-to-email service like **FormSubmit.co** or **Formspree** — drop-in replacement, takes 2 min.

If you'd like the FormSubmit version, just say the word.

---

That's it. One folder, deploy anywhere, edit in any text editor.
