# `@ehven/lanes`

Framework-agnostic CSS masonry layout with progressive enhancement to CSS Grid Lanes.

`@ehven/lanes` provides a lightweight waterfall layout without JavaScript sizing or item placement:

- CSS Multi-column Layout is the dependable baseline.
- Supporting browsers upgrade automatically to native CSS Grid Lanes.
- Plain HTML and CSS are the consumer interface; documentation includes Astro, Starlight, WordPress, Webflow and static HTML examples.
- No framework runtime is required.
- No runtime dependencies are required.

## Install

```sh
pnpm add @ehven/lanes@0.1.1
```

Import the readable stylesheet:

```css
@import '@ehven/lanes/lanes.css';
```

It may also be placed into a cascade layer:

```css
@import '@ehven/lanes/lanes.css' layer(layout);
```

## Manual use without Node or a build tool

1. Download [lanes.min.css](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/v0.1.1/lanes.min.css) and [SHA256SUMS](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/v0.1.1/SHA256SUMS) from the same release.
2. In the download directory, verify the minified file. On macOS use `grep ' lanes.min.css$' SHA256SUMS | shasum -a 256 --check`; on Linux use `grep ' lanes.min.css$' SHA256SUMS | sha256sum --check`. A successful check reports `lanes.min.css: OK`.
3. Store the CSS with your site, for example as `assets/vendor/ehven-lanes/lanes.min.css`, and load it in the document head:

```html
<link rel="stylesheet" href="/assets/vendor/ehven-lanes/lanes.min.css">
```

4. Use the markup below. Only direct children of the container become layout items. Set the public custom properties if needed, then check narrow and wide layouts and the ordering limitations below.

This self-hosted path has no package-manager or JavaScript requirement. WordPress and Webflow examples are in the public installation documentation.

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
  href="https://cdn.jsdelivr.net/npm/@ehven/lanes@0.1.1/dist/lanes.min.css"
/>
```

Never use an unpinned `latest` URL in production.

GitHub Releases also provide `lanes.css`, `lanes.min.css`, and `SHA256SUMS` for downloading and self-hosting.

## Ordering and accessibility

The document order is never changed.

Native Grid Lanes places successive items into the currently shortest lane. The Multi-column fallback flows content down one column before continuing into the next. Consequently, the visual arrangement can differ between the fallback and native enhancement.

Use lanes for independent peer items such as cards, images, summaries, or resources. Do not use it where a strict visual sequence is necessary for comprehension.

## Agent-assisted integration

The following task can be given to a coding assistant. Apply it within the consuming project's own instructions and authorization rules:

> Integrate @ehven/lanes at the project-approved pinned version for independent peer cards. Inspect the existing stylesheet pipeline and load one documented CSS variant once. Apply ehven-lanes to the intended container with each item as a direct child. Configure only the documented custom properties. Preserve semantic HTML and DOM/focus order, respect the different visual ordering of Multi-column fallback and native Grid Lanes, and follow the host project's dependency and deployment rules. Verify relevant narrow/wide layouts in available browsers, then report the exact version, changed files, checks and remaining coverage gaps.

This is consumer guidance, not an automatically installed assistant integration. No agent-specific Skill or executable tool is included.

## Documentation

- [Installation workflows](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v0.1.1/docs/installation.md)
- [Dual-delivery contract](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v0.1.1/docs/delivery.md)
- [Security policy](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v0.1.1/SECURITY.md)
- [Changelog](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v0.1.1/CHANGELOG.md)

## License

MIT © Gilad Ehven
