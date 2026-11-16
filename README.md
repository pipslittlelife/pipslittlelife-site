# pipslittlelife.com

A plain static site: `index.html`, `privacy.html`, `style.css`, `assets/`. No build step.

## Turn on selling
Open `index.html` and fill in near the top:

```js
window.PIP = { buyUrl: "https://buy.stripe.com/…", price: "$9.99" };
```

While `buyUrl` is empty, every Buy button says "Coming soon · tell me when" and opens an email to support@.

## Publish (Cloudflare Pages, free)
1. Put this `website` folder in its own GitHub repo (it can be public; nothing secret is in here).
2. Cloudflare dashboard → Workers & Pages → Create → Pages → connect that repo.
   Build command: *(none)*. Output directory: `/`.
3. In the project's **Custom domains**, add `pipslittlelife.com` (and `www.pipslittlelife.com`).
   Cloudflare shows the DNS records to add.
4. Porkbun → Domain Management → pipslittlelife.com → DNS: add those records. Leave the email-forwarding (MX) records alone.

Every push to the repo republishes the site.

## Preview locally
```
python -m http.server 8737 --directory website
```
then open http://localhost:8737

## Art
The PNGs in `assets/` are drawn straight from Pip's own scene code (transparent backgrounds).
`pip-trailer.mp4` is the 16:9 "A day on your desktop" montage.
