# AlpinX — Landing Page

A high-fidelity, responsive landing page for **AlpinX**, a crypto derivatives trading platform. Built as a single self-contained HTML file with no dependencies, no build step, and no framework — just open `index.html` in any browser.

🔗 **Live preview:** [hellbent86.github.io/alpinx-landing](https://hellbent86.github.io/alpinx-landing)

![AlpinX Preview](https://img.shields.io/badge/status-production--ready-brightgreen) ![HTML](https://img.shields.io/badge/stack-HTML%20%2B%20CSS%20%2B%20JS-blue) ![Responsive](https://img.shields.io/badge/responsive-desktop%20%7C%20tablet%20%7C%20mobile-orange)

---

## Overview

This landing page was faithfully implemented from a Figma design, preserving the exact color palette, typography, layout, and visual identity. It features a dark-mode crypto trading aesthetic with a violet/indigo accent palette, subtle micro-interactions, and a fully reconstructed trading terminal mockup with live-updating data.

## Features

### Design Fidelity
- **Exact Figma colors** preserved as CSS custom properties — no approximation to framework defaults
- **Plus Jakarta Sans** typography with precise weight/size mapping
- **Real SVG assets** (logo + 9 icons) inlined as base64 for full portability
- **Dark-mode-first** design with near-black base (`#08070f`) and violet/indigo accents

### Sections
1. **Floating header** — nav pill sits inline at top, transitions to a frosted 64px backdrop bar on scroll with blur effect. Logo scales from 120×40 to 96×32 when floating.
2. **Hero** — headline, subtext, two CTAs (Join Now / Explore) with a full trading terminal mockup on the right
3. **Candlestick background** — 26 bars scattered in a wave pattern, staggered draw-in animation on load, followed by a gentle idle opacity drift
4. **Unlock Smarter Ways To Trade** — three feature cards with large line-art icons
5. **More Than Just a Trading Terminal** — six feature items with icons over a structural grid
6. **FAQ** — expandable accordion with smooth max-height transitions, plus/× icon rotation
7. **Footer** — solid dark-indigo background, logo, link columns, social icons

### Trading Terminal Mockup
A faithful HTML/CSS reconstruction of the Figma trading dashboard, not an image. Includes:
- Left sidebar navigation (Home / Trade / Buy / Wallet)
- Header bar with XBTUSD pair, mark price, 24h stats
- Trade orders panel (Limit/Market/Stop, quantity, execution, leverage slider, BUY/SELL buttons, balance readouts)
- TradingView-style chart with SVG line that draws itself in on load
- Full order book with green bid rows and red ask rows, VOI/OIR summary
- Depth chart
- Open positions table (10 rows)
- Recent trades feed (16 rows)
- **Subtle live data animation**: every ~1.2s a random numeric value flashes and shifts its last digits

### Animations & Micro-interactions
- **Buttons**: primary CTA lifts with purple glow + sheen sweep on hover; secondary lifts with border brighten; both scale on press
- **3D tilt**: the trading dashboard tilts toward the cursor on hover (±8°) with a reactive shadow
- **Candle draw-in**: staggered scaleY grow from baseline, then idle opacity breathing
- **Parallax**: candles and grid lines shift subtly on mouse move
- **Scroll reveal**: sections fade up via IntersectionObserver with staggered card timing
- **FAQ**: smooth expand/collapse with rotating plus→× icon
- **Nav indicator**: underline slides between menu items following the cursor
- **Chart line draw**: SVG stroke-dashoffset animation on load
- **"Coming Soon" badge**: soft shadow pulse
- All animations respect `prefers-reduced-motion`

### Responsive Breakpoints
| Breakpoint | Behavior |
|---|---|
| Desktop (>1024px) | Full layout, nav pill with sliding indicator |
| Tablet (≤1023px) | Single-column hero, hamburger menu, full dashboard scaled to 85% |
| Mobile (≤600px) | Stacked layout, full-width CTAs, full dashboard scaled to 62% |

The trading terminal is **identical across all breakpoints** — no panels are hidden, it's simply scaled down via CSS `transform: scale()`.

## Tech Stack

- **Zero dependencies** — no npm, no bundler, no framework
- **Single file** — `index.html` contains all HTML, CSS, and JS
- **~95KB** total (including base64-encoded SVG assets)
- **Google Fonts** — Plus Jakarta Sans loaded via CDN
- **Vanilla JS** — IntersectionObserver, CSS animations, requestAnimationFrame
- **CSS Grid + Flexbox** — for all layouts
- **CSS Custom Properties** — for the full color system

## Color Palette

| Token | Hex | Role |
|---|---|---|
| `--bg` | `#08070f` | Page background |
| `--white` | `#ffffff` | Primary text, logo |
| `--text-muted` | `#a3a3c2` | Subtext, labels |
| `--text-card` | `#d1d1fa` | Card body text |
| `--periwinkle` | `#a0a2f6` | Borders, nav indicator |
| `--grad-top` | `#8974ff` | Primary button gradient (top) |
| `--grad-bottom` | `#5646ff` | Primary button gradient (bottom) |
| `--candle` | `#7f6efc` | Highlighted candle bars |
| `--border-primary` | `#7e80ec` | Primary button border |
| `--border-secondary` | `#7778ae` | Secondary button border |

## Quick Start

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/alpinx-landing.git

# Open in browser
open alpinx-landing/index.html
```

Or simply download `index.html` and double-click it — no server needed.

## Deployment

The page works anywhere static HTML is served:

- **GitHub Pages**: push to `main`, enable Pages in repo settings → done
- **Netlify / Vercel**: drag and drop the file, or connect the repo
- **Any web server**: drop `index.html` into the document root

## Browser Support

Tested and working in:
- Chrome / Edge 90+
- Firefox 90+
- Safari 15+
- Mobile Safari / Chrome on iOS and Android

## License

This project is proprietary. The AlpinX brand, logo, and design are owned by their respective holders. This implementation is for evaluation purposes.

---

Built with care from a Figma design, one `<div>` at a time.
