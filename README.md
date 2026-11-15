# `@ehven/lanes`

Framework-independent CSS masonry for unequal-height peer items. No runtime JavaScript or dependencies. Existing markup uses CSS Columns, enhanced to native Grid Lanes where supported.

## Install and use

Use the project's normal package manager, for example:

```sh
npm install @ehven/lanes@1.0.0
```

Import one stylesheet once through the existing CSS pipeline:

```css
@import '@ehven/lanes/lanes.css';
/* Or: @import '@ehven/lanes/lanes.css' layer(layout); */
```

```html
<div class="ehven-lanes">
  <article>First item</article>
  <article>Second item</article>
  <article>Third item</article>
</div>
```

Only direct children become lane items. Compatible bundlers also accept the root export; `/lanes.min.css` is the minified alternative.

## Horizontal ordering

```html
<div class="ehven-lanes" data-ehven-lanes-order="horizontal">
  <!-- Independent, single-lane peer items -->
</div>
```

In native supporting browsers, successive cards cycle across columns and stack below their own column predecessor, retaining uneven tops. Direction follows LTR/RTL. This is cyclic placement, not shortest-column packing.

Without native Grid Lanes plus infinite-tolerance support, horizontal mode falls back to aligned Grid rows, each below the preceding row's tallest card. No JavaScript polyfill ships.

Set `data-ehven-lanes-order="rows"` for aligned rows everywhere. Omitted or unrecognized values preserve the original fallback/enhancement behavior. Ordered modes require single-lane children without explicit placement, spanning or CSS `order`. Consumer UI can change the attribute without measuring or reordering cards.

## Configure

Keep consumer CSS in `config/packages/npm/lanes/index.css`, imported through the existing pipeline. Preserve existing filenames until a deliberate migration; never edit `node_modules`.

```css
.project-list {
  --ehven-lanes-lane-minimum: 16rem;
  --ehven-lanes-gap: 1.25rem;
  --ehven-lanes-flow-tolerance: 3rem;
}
```

Apply `project-list` alongside `ehven-lanes`, or set inherited defaults on an ancestor.

| Custom property | Default | Effect |
|---|---|---|
| `--ehven-lanes-lane-minimum` | `18rem` | Preferred responsive lane minimum |
| `--ehven-lanes-gap` | `1rem` | Separation between items |
| `--ehven-lanes-flow-tolerance` | `normal` (native equivalent of `1em`) | Original native mode's placement tolerance |

The existing tolerance hook maps to both native `flow-tolerance` and its newer `fit-tolerance` name. Horizontal mode fixes it to `infinite`; rows mode has none. Supply valid nonnegative lengths where required; CSS invalid-value handling applies.

## Manual use without Node

1. Download [lanes.min.css](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/v1.0.0/lanes.min.css) and [SHA256SUMS](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/v1.0.0/SHA256SUMS) from the same release.
2. In that directory, verify the selected file. Linux: `grep ' lanes.min.css$' SHA256SUMS | sha256sum --check`. macOS: `grep ' lanes.min.css$' SHA256SUMS | shasum -a 256 --check`. Expect `lanes.min.css: OK`.
3. Store CSS locally, retain its license notice, and load it:

```html
<link rel="stylesheet" href="/assets/vendor/ehven-lanes/lanes.min.css">
```

4. Apply the markup/settings above. Verify narrow/wide layout and actual content order.

Readable CSS is also available. Corresponding npm/direct-download CSS bytes match. An optional CDN adds a third-party dependency:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@ehven/lanes@1.0.0/dist/lanes.min.css">
```

Never use moving `latest` URLs in production.

## Compatibility and accessibility

Fallbacks require CSS Columns (default) or modern Grid with `min()` (ordered modes). Native horizontal masonry additionally requires `display: grid-lanes` and `fit-tolerance: infinite` or the older `flow-tolerance` equivalent.

DOM order is unchanged. Columns flow downward; original native mode favors shorter lanes. Horizontal masonry can place a later card higher than an earlier card in another column. Use independent peers; choose rows for strict visual row sequence. Preserve meaningful source order and verify keyboard traversal.

Verified engines: WebKit 27.2 (native and fallback), Chromium 156 and Firefox 157 (fallback). These are test-engine results, not certification of every branded browser or host version.

Recipes cover Astro, Starlight, WordPress, Webflow and static HTML; they do not certify every host version. Reserve media dimensions to reduce shifts and handle inner text overflow in consumer CSS.

The stable 1.x contract covers the class, ordering attributes, three custom properties, stylesheet exports and documented defaults. Patches preserve behavior; compatible additions use a minor; incompatible contract changes require a major and migration notes. Native layout depends on browser support; aligned rows remain the horizontal fallback. Only the latest minor of the current major receives fixes; no response-time guarantee applies. Restore an exact verified version to roll back.

## Agent-assisted integration

> Use the approved pinned version and existing stylesheet pipeline. Load one variant once; use direct-child peers and documented settings. Preserve semantic DOM/focus order and host rules. Account for native/fallback ordering; test narrow/wide layouts and report version, changes, checks and gaps.

This is consumer guidance, not an installed assistant integration.

## Support and funding

For paid integration, support or sponsorship inquiries, [contact Ehven Consultants](https://ehven.com/contact/). Sponsorship is not a support agreement. Use public issues for routine bugs and the security policy for vulnerabilities.

## Documentation

- [Installation workflows](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v1.0.0/docs/installation.md)
- [Delivery and recovery](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v1.0.0/docs/delivery.md)
- [Security policy](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v1.0.0/SECURITY.md)
- [Changelog](https://github.com/ehven-consultants-npm-distributions/ehven-lanes/blob/v1.0.0/CHANGELOG.md)

MIT © Gilad Ehven
