# VOICES — Landing Page

Static HTML landing page for voices.vu. No build step, no dependencies beyond a Google Fonts CDN call.

## Files

- `index.html` — the entire page, self-contained

## How to deploy

### Vercel (recommended)
1. Push this folder to a GitHub repo
2. Import the repo in vercel.com → Add New Project
3. Leave all settings as default — Vercel detects static HTML automatically
4. Deploy

### Any static host (Netlify, Cloudflare Pages, S3, etc.)
Upload `index.html` as the root file. No configuration needed.

### Local preview
```
python3 -m http.server 8080
```
Then open http://localhost:8080

## Links

Both CTA buttons point to:
```
https://social.voices.vu/about
```
Update the `href` on the `.cta` anchor in `index.html` if this changes.

## Fonts

Loaded from Google Fonts CDN — no local files needed:
- **Roboto Mono 500** — wordmark
- **Inter 300, 700** — tagline and button

## Animation

The background is a canvas flow-field: ~180 particles follow a layered noise vector field, leaving fading ink trails. All parameters (particle count, speed, colours) are at the top of the `<script>` block in `index.html` and are commented for easy tuning.

Key variables to tweak:
| Variable | Default | Effect |
|---|---|---|
| `PARTICLE_COUNT` | 180 | More = denser, Less = more minimal |
| `t += 0.0015` | 0.0015 | Higher = faster flow field evolution |
| `inkColors` | teal/blue family | Swap RGB values to change palette |
| `ctx.fillStyle = 'rgba(2,6,9,0.04)'` | 0.04 opacity | Higher = trails fade faster |
