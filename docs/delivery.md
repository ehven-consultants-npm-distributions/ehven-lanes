# Consumer delivery and integrity

Install the published package with an exact version and retain the project lockfile:

```sh
npm install --save-exact @ehven/lanes@0.1.0
```

The readable and minified CSS under this repository's dist directory are byte-for-byte equal to the corresponding files inside the npm0.1.0 package. distribution.json identifies their SHA-256 digests and the registry package integrity.

## Download and self-host

Versioned GitHub Release assets use these canonical URLs:

```text
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/lanes.css
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/lanes.min.css
https://github.com/ehven-consultants-npm-distributions/ehven-lanes/releases/download/vVERSION/SHA256SUMS
```

Select an available version from the Releases page. You may also download the stylesheet files from dist and check their digests against distribution.json. Save the stylesheet with your site and reference your own local asset URL. Preserve its MIT notice.

For release assets, download the desired CSS file and SHA256SUMS from the same exact release. On Linux, run `grep ' lanes.min.css$' SHA256SUMS | sha256sum --check`. On macOS, use `grep ' lanes.min.css$' SHA256SUMS | shasum -a 256 --check`.

## Earlier GitHub URLs

This distribution repository is the canonical public home. Update bookmarks and direct stylesheet URLs that used the earlier GitHub source location; historical source URLs are not a permanent download contract and may become inaccessible. Published npm versions remain unchanged and available through npm. Do not replace a pinned version with a moving latest URL.

## Compatibility and recovery

The selector, stylesheet exports and documented custom properties form the public API. Visual ordering differs between the Multi-column fallback and native Grid Lanes; use independent peer items. Review release notes before upgrading. Restore the previous verified exact version if needed, and report a reproducible usage issue through this repository's issue tracker. Use the private security-reporting route for suspected vulnerabilities.
