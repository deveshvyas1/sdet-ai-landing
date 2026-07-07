# sdet-ai.tech — landing site

Static marketing site for **SDET-AI** (AI-assisted Playwright test generation). No build step — plain HTML/CSS/JS.

## Structure

```
index.html          Landing page
privacy.html        Privacy policy
terms.html          Terms of service
404.html            Not-found page
css/styles.css      All styles
js/main.js          Nav, tabs, typing animation, waitlist form, particles
assets/             Favicon, apple-touch-icon, OG image
robots.txt          Crawler rules
sitemap.xml         Sitemap (update lastmod when pages change)
```

## Before going live — checklist

1. **Wire up the waitlist form (required).**
   Create a free form at [formspree.io](https://formspree.io), then in `js/main.js` replace
   `YOUR_FORM_ID` in `WAITLIST_ENDPOINT` with your real form ID.
   Until then, the form shows a "not wired up yet" message with a mailto fallback —
   it never fakes a success.
2. **Personalize the founder note** in `index.html` (`#founder` section) — the copy is a
   starting point; make it yours.
3. **Add analytics (optional).** [Plausible](https://plausible.io) or Cloudflare Web
   Analytics are cookie-free (no consent banner needed). Paste the snippet before
   `</head>` in each HTML file.
4. **Serve `404.html` for missing routes.** GitHub Pages and Cloudflare Pages pick it up
   automatically; on Netlify it works out of the box too.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

(Open via a server, not `file://` — the site uses root-relative paths like `/css/styles.css`.)

## Notes

- The hero terminal and demo tabs show **illustrative** sample output and are labeled as such on the page.
- No fabricated stats, testimonials, or compliance claims — keep it that way until there are real ones.
- OG image source lives in git history (`og-tmp.html`); regenerate with headless Chrome at 1200×630 if the tagline changes.
