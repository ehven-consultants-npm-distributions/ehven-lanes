# `@ehven/lanes`

Framework-agnostic CSS masonry layout with progressive enhancement to CSS Grid Lanes.

`@ehven/lanes` provides a lightweight waterfall layout without JavaScript sizing or item placement:

- CSS Multi-column Layout is the dependable baseline.
- Supporting browsers upgrade automatically to native CSS Grid Lanes.
- Plain HTML and CSS are the consumer interface; documentation includes Astro, Starlight, WordPress, Webflow and static HTML examples.
- No framework runtime is required.
- No runtime dependencies are required.

Consumer documentation and byte-matched CSS for `@ehven/lanes@0.1.0`. Download the [readable stylesheet](dist/lanes.css) or [minified stylesheet](dist/lanes.min.css), retain the license notice, and self-host it. [Integrity metadata](distribution.json) identifies these exact files.

## Install

```sh
pnpm add @ehven/lanes@0.1.0
```

Import the readable stylesheet:

```css
@import '@ehven/lanes/lanes.css';
```

It may also be placed into a cascade layer:

```css
@import '@ehven/lanes/lanes.css' layer(layout);
```

## Use

```html
<div class="ehven-lanes">
  <article>First item</article>
  <article>Second item with more content</article>
  <article>Third item</article>
</div>
```

Only the direct children of `.ehven-lanes` become lane items.

## Configure

```css
.project-list {
  --ehven-lanes-lane-minimum: 16rem;
  --ehven-lanes-gap: 1.25rem;
  --ehven-lanes-flow-tolerance: 3rem;
}
```

```html
<div class="ehven-lanes project-list">
  <!-- Independent peer items -->
</div>
```

| Custom property | Default | Purpose |
|---|---:|---|
| `--ehven-lanes-lane-minimum` | `18rem` | Preferred minimum width of each responsive lane |
| `--ehven-lanes-gap` | `1rem` | Horizontal and vertical separation between items |
| `--ehven-lanes-flow-tolerance` | `1em` | Native Grid Lanes tolerance for treating nearly equal lane positions as ties |

`--ehven-lanes-flow-tolerance` affects only browsers supporting native Grid Lanes.

## Direct stylesheet delivery

A version-pinned CDN URL is available after publication:

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/@ehven/lanes@0.1.0/dist/lanes.min.css"
/>
```

Never use an unpinned `latest` URL in production.

See [consumer delivery and integrity](docs/delivery.md) for versioned release URLs and migration from earlier GitHub links.

## Ordering and accessibility

The document order is never changed.

Native Grid Lanes places successive items into the currently shortest lane. The Multi-column fallback flows content down one column before continuing into the next. Consequently, the visual arrangement can differ between the fallback and native enhancement.

Use lanes for independent peer items such as cards, images, summaries, or resources. Do not use it where a strict visual sequence is necessary for comprehension.

## Documentation

- [Installation workflows](docs/installation.md)
- [Dual-delivery contract](docs/delivery.md)
- [Security policy](SECURITY.md)
- [Changelog](CHANGELOG.md)

## License

MIT © Gilad Ehven
