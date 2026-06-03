# Changelog

All notable changes to the **DistroRun LSP** extension will be documented in this file.


## [0.1.3] — 2026-05-20

### Added

- Schema support for the new `build.output` key with enum values `iso`, `disk`, and `img`
- Schema support for `build.disk_size` (qcow2 virtual disk size when `output: disk`)
- Schema support for `build.persist_size` (persistence partition size when `output: img`)
- Pattern validation for size strings (e.g., `4G`, `512M`)


## [0.1.2] — 2026-02-19

### Changed

- Renamed `distro.name` to `distro.base` in the schema
- Rewrote README for clarity and consistency

### Added

- New mandatory top-level `name` key (string) in the schema


## [0.1.1] — 2026-02-18

### Added

- Logo 


## [0.1.0] — 2026-02-17

### Added

- Initial release
- JSON Schema for DistroRun YAML configuration files
- Autocompletion, validation, and hover documentation via Red Hat YAML
- Support for `version`, `distro`, `packages`, `users`, `services`, and `build` keys
