# Changelog

All notable changes to this project will be documented in this file.

The project follows Semantic Versioning.

## [Unreleased]

## [1.0.0] - Unreleased

### Added

- Opt-in horizontal ordering: cyclic single-lane placement with uneven tops in native supporting browsers; aligned horizontal rows elsewhere.
- Explicit aligned-row ordering in all supporting browsers.
- Support/contact discovery through npm funding metadata and consumer documentation.

### Changed

- Limit distributed documentation to consumer usage, support and delivery information.
- Normalize license-file formatting.
- Use dedicated public distribution/support URLs and the current source identity.
- Preserve existing unconfigured layout and public custom-property names.
- Support native `fit-tolerance` alongside the older `flow-tolerance` name.

The first stable release preserves existing markup and styling hooks. No markup migration is required from 0.1.0.

## [0.1.0] - 2026-09-14

### Added

- Framework-agnostic `.ehven-lanes` layout primitive.
- CSS Multi-column Layout baseline.
- Progressive enhancement to native CSS Grid Lanes.
- Public configuration through namespaced custom properties.
- Readable and minified CSS distribution artifacts.
- npm and direct-stylesheet delivery workflows.
- Automated tests, package inspection, checksums, and releases.

[0.1.0]: https://www.npmjs.com/package/@ehven/lanes/v/0.1.0
