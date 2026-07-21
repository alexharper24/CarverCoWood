# Carver Co. Woodworking — carvercowood.com

Static website for Carver Co. Woodworking, a family-owned custom woodworking
studio in Louisville, KY (live-edge tables, epoxy bar tops, custom furniture).

Hosted on GitHub Pages from the `main` branch root. No build step — plain
HTML/CSS/JS, one file per page, images in `images/`.

## Pages

| File | Page |
|---|---|
| `index.html` | Home |
| `about.html` | About / our story |
| `gallery.html` | Work gallery |
| `pricing.html` | Pricing guide |
| `testimonials.html` | Customer reviews |
| `contact.html` | Contact + quote request form |
| `404.html` | Not-found page |

## Contact form

The quote form on `contact.html` posts to Formspree. Setup:

1. Create a free form at [formspree.io](https://formspree.io) with
   notifications going to `info@carvercowood.com`.
2. Replace `YOUR_FORM_ID` in `contact.html` with the real form ID.
3. Submit one test message and click the one-time confirmation email
   Formspree sends.

Until the ID is set, the form shows a friendly "not connected yet" message
instead of failing silently.

## Custom domain cutover (from the old WordPress host)

All images are local to this repo, so the old WordPress site is no longer
needed once DNS moves:

1. GitHub → Settings → Pages → Custom domain: `carvercowood.com` (this
   commits a `CNAME` file — do this **before** changing DNS).
2. At the DNS host, point the apex `carvercowood.com` at GitHub Pages with
   four A records (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
   `185.199.111.153`) and a `www` CNAME to `alexharper24.github.io`.
3. Back in GitHub Pages settings, enable **Enforce HTTPS** once the
   certificate is issued.
4. After the domain resolves here, the WordPress hosting can be cancelled.
