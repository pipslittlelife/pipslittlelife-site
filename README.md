# pipslittlelife.com

A plain static site: `index.html`, `privacy.html`, `style.css`, `assets/`. No build step.

## Turn on selling
Open `index.html` and fill in near the top:

```js
window.PIP = { buyUrl: "https://buy.stripe.com/…", price: "$9.99" };
```

While `buyUrl` is empty, every Buy button says "Coming soon · tell me when" and opens an email to support@.

## Publish (GitHub Pages, free)
The site lives in the public repo `pipslittlelife/pipslittlelife-site`; every push to `main` republishes it.
- Repo → Settings → Pages: Source = "Deploy from a branch", branch `main`, folder `/ (root)`.
- Custom domain: `pipslittlelife.com` (the `CNAME` file keeps it set). Tick "Enforce HTTPS" once it's offered.
- Porkbun DNS for pipslittlelife.com:
  - `A` records on the root (`@`, host left blank): 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
  - `CNAME` `www` → `pipslittlelife.github.io`
  - Leave the email-forwarding (MX/TXT) records alone.

## Preview locally
```
python -m http.server 8737 --directory website
```
then open http://localhost:8737

## Art
The PNGs in `assets/` are drawn straight from Pip's own scene code (transparent backgrounds).
`pip-trailer.mp4` is the 16:9 "A day on your desktop" montage.
