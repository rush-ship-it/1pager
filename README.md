# Continua Finance — website

Static site for [continua.finance](https://continua.finance). No build step: plain HTML, CSS and JavaScript.

```
index.html          the site
note16.html, note17.html   the notes, served at /note16 and /note17
assets/             mark and logo (SVG)
og.png              social preview image (2400×1260)
404.html            branded not-found page
CNAME               custom domain for GitHub Pages
.nojekyll           tells GitHub Pages to serve files as-is
robots.txt, sitemap.xml
```

## Deploy (GitHub Pages)
Settings → Pages → Source: *Deploy from a branch* → branch `main`, folder `/ (root)`.
The `CNAME` file keeps the custom domain across deploys. Turn on *Enforce HTTPS* once the certificate is issued.

DNS for the apex domain: four `A` records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`,
and optionally a `CNAME` for `www` pointing at `<user>.github.io`.

## Clean URLs
GitHub Pages serves `note17.html` at `https://continua.finance/note17` (and still at `/note17.html`). Links on the site use the extensionless form.

## Waitlist
Both waitlist forms post JSON to a Formspree endpoint (`WAITLIST_ENDPOINT` near the top of the script block in `index.html`).
In the Formspree dashboard keep reCAPTCHA off for this form (AJAX submissions cannot show a captcha) and, if you restrict
domains, allow `continua.finance`.
