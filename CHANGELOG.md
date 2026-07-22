# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.3]

### Changed

- Bumped `thiserror` from `2.0.18` to `2.0.19`.
- Bumped `memmap2` from `0.9.10` to `0.9.11`.
- Bumped `tempfile` (dev-dependency) from `3.26.0` to `3.27.0`.

## [0.2.2]

### Added

- `CowFile::fork` — create an independent copy-on-write clone of an existing `CowFile`.
- `CowFile::source_path` — return the backing file path (`Option<&Path>`) when the
  `CowFile` is file-backed.

## [0.2.1]

### Fixed

- Switched to `RwLock` and `AtomicBool` so `CowFile` is `Send + Sync`.

## [0.2.0]

### Changed

- Reworked the core logic to use OS-backed copy-on-write as its foundation.

## [0.1.0]

### Added

- Initial release: a copy-on-write abstraction for binary data backed by memory or files.

[0.2.3]: https://github.com/BinFlip/cowfile/compare/v0.2.2...v0.2.3
[0.2.2]: https://github.com/BinFlip/cowfile/compare/v0.2.1...v0.2.2
[0.2.1]: https://github.com/BinFlip/cowfile/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/BinFlip/cowfile/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/BinFlip/cowfile/releases/tag/v0.1.0
