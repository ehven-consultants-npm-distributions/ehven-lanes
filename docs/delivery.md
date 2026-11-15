# Consumer delivery and recovery

Install an exact version with the project's normal package manager and lockfile. Import `@ehven/lanes/lanes.css` or `/lanes.min.css`; compatible bundlers also accept the root export.

For no-build use, download the desired CSS and checksum manifest from the same published release:

```text
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/lanes.min.css
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/SHA256SUMS
```

Follow the README's Linux/macOS checksum commands, retain the license notice, and store/link the verified file locally. Corresponding npm and direct-download CSS bytes are identical.

An optional version-pinned CDN adds a third-party network dependency:

```text
https://cdn.jsdelivr.net/npm/@ehven/lanes@VERSION/dist/lanes.min.css
```

Never use moving `latest` URLs in production. Restore the previously verified exact dependency or CSS file to roll back; remove imports/attributes to uninstall. Check the resulting host layout. CSS introduces no persistent runtime state. Report version and reproduction through the public support route.
