# Celestial Grove

**A seed-based generative system for celestial tree groves.**

A catalogue of computational textile compositions for fashion, textile and surface design — algorithmically drawn, seed-documented, and ready for production.

---

## Overview

Celestial Grove is a generative design system rather than a single artwork. Each composition is built from a set of recursive trees — drawn from the ground upward with branches that fork, rotate, and thin — gathered under a moonlit sky. Above them, one to three moons hang soft and even.

The system is designed for:

- **Fashion houses** adapting botanical ornament for apparel and accessories
- **Textile studios** developing repeat patterns and yardage
- **Surface designers** working across print, wallpaper, and interior applications

Every composition can be licensed, adapted, or commissioned to a brief.

---

## Concept

A grove, when it is *generated* rather than drawn, becomes a constellation — endless, precise, quietly yours.

The branching tree — recursive, irregular, endlessly varied — has always been a computational structure. The way a trunk forks into limbs, the way a stream splits into tributaries, the way a family line grows — these are algorithms the world has been running long before there were computers. Celestial Grove translates that structure into code. Each composition begins with a handful of trees, and unfolds through recursion, rotation, and scale until the frame fills with a quiet, moonlit grove.

The palette, the number of branches, the sky colour, and the number of moons are all derived from a single numeric seed.

Unlike the animated volumes in this series (Bezier 2, Brownian Graphe), **Celestial Grove is a still composition.** The plate, the framed plate, the surfaces, and the archive are all static frames. This is deliberate: a grove is something you stand still inside. Its character is stillness, not motion.

---

## Features

- **Seed-based generation** — every composition is defined by a numeric seed and can be regenerated exactly
- **Deterministic output** — the same seed always produces the same composition
- **Recursive branching** — trees that fork, rotate, scale, and thin as they rise
- **Moonlit sky** — one to three soft moons placed above the grove
- **Distance-based line thickness** — branch width scales with the tree's own dimensions
- **Adaptive surfaces** — one seed applied across print, scarf, textile, and wall formats
- **Archive** — eight curated seeds available for immediate loading
- **Download** — export the composition as a high-resolution PNG
- **Keyboard shortcuts** — `R` for new seed, `S` to save

---

## Project Structure

```
.
├── index.html          # Main catalogue page
├── images/
│   ├── fav.svg         # Favicon
│   ├── tote.png        # Mockup: tote bag
│   ├── tee.png         # Mockup: t-shirt
│   └── cushion.png     # Mockup: cushion
└── README.md
```

---

## How It Works

### The Seed

A numeric seed (a large integer) initializes a deterministic pseudo-random generator. From this seed, the system derives:

- Background sky colour (from a palette of 21 deep tones)
- Number of branches (trees in the grove, typically 10–60)
- Per-branch colour (from a palette of 50 tones)
- Number of moons (1–3)

Because the generator is deterministic, the same seed always produces the same composition — on any device, at any time.

### The Trees

Each tree is drawn recursively. A trunk is drawn from the base upward, then a single branch continues from its tip — rotated by a random angle, and scaled down slightly. At each step, there is a chance the branch will fork into two separate sub-branches, each rotated away from the parent.

The recursion stops at a fixed depth (13 steps), producing a branching structure that grows from the ground upward. The line width of each branch is derived from the tree's own width, so larger trees draw thicker trunks.

The result is not a forest of identical trees — each one is generated independently, so no two are alike.

### The Moons

One to three moons are placed in the upper half of the frame, at random positions, with random radii. Each is drawn as a filled circle in a warm cream colour, with a soft shadow blur that gives it a gentle glow.

### The Surfaces

The same seed is rendered across four surface formats. These are static frames — they represent the print-ready composition.

| Surface  | Aspect | Material          |
|----------|--------|-------------------|
| Print    | 1 : 1  | Cotton rag        |
| Scarf    | 3 : 1  | Twill silk        |
| Textile  | 4 : 3  | Fabric yardage    |
| Wall     | 2 : 3  | Wallpaper         |

Each surface uses the same underlying seed and structural logic — only the repeat, orientation, and scale change.

### Stillness

Unlike Bezier 2 and Brownian Graphe, Celestial Grove does not animate. The plate is a single frozen frame — the composition is complete the moment it is generated.

This is a deliberate design choice. A grove is not a swarm. It is not a rotation. It is a place you stand inside. The stillness is what gives the composition its character, and what makes it print-ready in the strictest sense: what you see is what you get.

---

## Usage

### In the browser

1. Open `index.html` in any modern browser.
2. Click **New Seed** to generate a new grove.
3. Click **Download** to save the composition as a PNG.
4. Scroll to the **Archive** section and click any plate to load it into Plate 001.

### Keyboard shortcuts

| Key | Action          |
|-----|-----------------|
| `R` | New seed        |
| `S` | Save as PNG     |

### Reproducing a composition

Each composition is identified by an 8-digit seed label displayed in the metadata panel. To reproduce a specific composition, note the seed and regenerate it programmatically:

```js
const rng = new RandomGenerator(seed);
const features = buildFeatures(rng);
renderComposition(canvas, features, rng);
```

Because the generator is deterministic, this will produce the identical composition on any device.

---

## Technical Notes

- **No build step.** The system is a single HTML file with inline CSS and JavaScript.
- **No dependencies.** All drawing is done with the native Canvas 2D API.
- **Deterministic.** The `RandomGenerator` class uses a xorshift-based PRNG seeded by an integer, so identical seeds produce identical outputs.
- **Static rendering.** Every canvas renders a single frame. There is no animation loop.
- **Feature isolation.** Cover, framed plate, surfaces, and archive thumbnails each derive their own feature set from their own local RNG, without disturbing the main plate's state.
- **Bounded recursion.** The tree recursion has a hard depth limit of 13, preventing stack overflow even at large canvas sizes.
- **Responsive.** The layout adapts from large desktop down to very small mobile devices (tested at 360px viewport width).
- **Accessible.** Supports `prefers-reduced-motion`. Pinch-zoom is enabled.

### Browser support

Tested in current versions of:

- Chrome / Edge
- Firefox
- Safari (desktop and iOS)

---

## Licensing

All Celestial Grove compositions are **seed-documented** and available for licensing across textile, surface, and print applications.

- **Standard licenses** cover single-product production runs.
- **Commercial use, custom editions, or exclusive rights** are available on request.

Each license is issued against a specific seed ID. Regeneration of the same seed produces the identical composition — ensuring reproducibility between artist, studio, and manufacturer.

For licensing enquiries: [reyhanehdaneshdoost@gmail.com](mailto:reyhanehdaneshdoost@gmail.com)

---

## Commission

Celestial Grove is a generative design system, not a fixed artwork. It can be adapted for specific briefs:

| Service     | Description                                                       |
|-------------|-------------------------------------------------------------------|
| Licensing   | Existing seeds from the archive, licensed for production use      |
| Commission  | New compositions designed to your palette, repeat, and product    |
| Systems     | A private generative tool built for your studio's ongoing use     |

To begin a conversation: [reyhanehdaneshdoost@gmail.com](mailto:reyhanehdaneshdoost@gmail.com)

---

## Series

Celestial Grove is part of a computational textile series. Each volume approaches ornament from a different structural angle:

| Volume             | Structure              | Motion                     |
|--------------------|------------------------|----------------------------|
| Girih 1            | Islamic geometric      | Static                     |
| Arachne            | Rotating rings         | Static                     |
| Baroque Me Baby    | Baroque frames         | Static                     |
| Bezier 1           | Concentric curves      | Static                     |
| Bezier 2           | Single rotating curve  | Animated (plate)           |
| Brownian Graphe    | Graph networks         | Animated + interactive     |
| **Celestial Grove**| Recursive branch trees | **Static**                 |

The series is designed as a coherent whole — same page structure, same seed logic, same licensing and commission terms — so that each volume can be presented individually or as part of a larger body of work.

---

## Credits

- **Design & Generative System** — Reyhaneh Daneshdoost
- **Typefaces** — Cormorant Garamond · DM Mono
- **Platform** — Reyrove Studio
- **Edition** — Celestial Grove, Autumn 2026

### On AI tools

Where technical obstacles were encountered, AI tools were used for debugging and code optimization. Every structural, aesthetic, and conceptual decision remained the artist's own.

---

## Links

- Website — [reyrove.github.io](https://reyrove.github.io/)
- Instagram — [@rey._.rove](https://www.instagram.com/rey._.rove/)
- LinkedIn — [Reyhaneh Daneshdoost](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- X — [@reyrove](https://x.com/reyrove)

---

© Celestial Grove · All compositions reproducible by seed · Computational Textile 