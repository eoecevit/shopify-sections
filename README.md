# Shopify Sections

Custom Shopify OS 2.0 sections (Liquid + vanilla JS + CSS) that I built for a real hair salon and online shop in Vienna. Every section is self-contained: markup, styles, script and `{% schema %}` live in a single file, so you can drop it into any Online Store 2.0 theme.

## Sections

| File | What it does | Editor settings |
|---|---|---|
| `sections/brands-carousel.liquid` | Endless, continuously scrolling brand logo carousel (no stops, no jumps) | 7 settings, `brand` blocks |
| `sections/collection-split.liquid` | Split layout: a product grid from a chosen collection next to a content column with text, icons, image and buy buttons (configurable products per row, image position, width, color scheme) | 13 settings, `text` / `buy_buttons` / `icon` / `image` blocks |
| `sections/services-list.liquid` | Salon services list: each service with image, price, duration, short + expandable long description and a booking button (editor labels in German) | 10 settings, `service` blocks |

`experiments/` contains earlier iterations of the brand carousel (active slide state, infinite-scroll performance test, click handling). They are kept for reference and comparison.

## Installation

1. In Shopify Admin go to **Online Store → Themes → … → Edit code**.
2. Under `sections/`, click **Add a new section** and give it the file name, e.g. `brands-carousel`.
3. Paste the file content and save.
4. Open the theme editor. The section shows up under **Add section**.

Or with the Shopify CLI:

```bash
shopify theme pull
cp sections/*.liquid <your-theme>/sections/
shopify theme push
```

## Tech

- Liquid, Shopify Online Store 2.0 (JSON templates, section blocks, presets)
- Vanilla JavaScript, no dependencies
- Lazy-loaded images, responsive CSS

## Roadmap

- [ ] Scope the carousel JavaScript to `section.id`, so several carousels can run on one page
- [ ] Give the experiment variants their own schema names
- [ ] Add screenshots / GIFs of each section
- [ ] Add translation keys (`locales/*.json`) instead of hard-coded labels

## License

MIT, see [LICENSE](LICENSE).
