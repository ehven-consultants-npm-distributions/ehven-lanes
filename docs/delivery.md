# Consumer delivery and integrity

`@ehven/lanes` is available as an npm package and as versioned downloadable CSS. The readable and minified stylesheets represent the same public CSS API. The readable file includes explanatory CSS comments; neither variant provides implementation confidentiality.

## Package installation

Install an exact version using your project's package manager and retain its lockfile. Import `@ehven/lanes/lanes.css` or `@ehven/lanes/lanes.min.css` from a supported CSS build. The package root resolves to the readable stylesheet for compatible bundlers.

## Download and self-host

For corrected releases, the canonical download pattern after publication is:

```text
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/lanes.css
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/lanes.min.css
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/SHA256SUMS
```

Download the desired stylesheet and its checksum manifest from the same exact version. On Linux:

```sh
grep ' lanes.min.css$' SHA256SUMS | sha256sum --check
```

On macOS:

```sh
grep ' lanes.min.css$' SHA256SUMS | shasum -a 256 --check
```

Store the verified file with the consuming site, retain its license notice, and reference it with a local stylesheet link. npm-delivered CSS and corresponding direct-download CSS have identical bytes for a given release and variant.

## Optional CDN

An exact version may also be used through jsDelivr:

```text
https://cdn.jsdelivr.net/npm/@ehven/lanes@VERSION/dist/lanes.min.css
```

This adds a third-party network dependency. Self-hosting avoids that dependency. Do not use a moving `latest` production URL.

## Compatibility and recovery

The selector, stylesheet exports and documented custom properties form the public API. Consult release notes before upgrading. If a new version causes a problem, restore the previously verified exact version in the consumer and report the affected version and a reproduction through the documented support route.
