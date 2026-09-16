# vinay-portfolio

Freelance portfolio site — a single static `index.html`, no build step, no dependencies.

## Local preview

Open `index.html` in a browser, or:

```bash
python -m http.server 8000
```

## Deploying on Render

The repo contains `render.yaml`, so Render can configure the service itself:

1. Go to https://dashboard.render.com/blueprints and choose **New Blueprint Instance**.
2. Pick this repository and apply. Render reads `render.yaml` and creates a static site.
3. Every push to `main` redeploys automatically.

Manual alternative (no blueprint): **New → Static Site**, then set
**Build Command** to blank and **Publish Directory** to `.`.

## Editing the site

Everything lives in `index.html`:

| What | Where |
|---|---|
| Name and tagline | `.brand`, `.hero h1`, `.hero .lede` |
| Availability / timezone / rates panel | `<aside class="spec">` |
| Services and tech stacks | `#services` |
| Projects | `#work` — three `article.proj` blocks, currently marked `SAMPLE` |
| Process steps | `#process` |
| Email and Freelancer link | `#contact` |

To publish a real project: replace the copy, delete its
`<span class="chip-sample">SAMPLE</span>`, and swap the drawn thumbnail
`<div class="thumb">…</div>` for a screenshot:

```html
<img src="images/project-one.png" alt="Dashboard screenshot" class="thumb">
```
