# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.4]

### Changed

- Recorded ATRAPS LLC as copyright holder and added a `NOTICE` file. The Apache-2.0
  appendix claimed 2025-2026, but every commit in this repository dates to 2026.
  No functional change.
- Renamed `LICENSE-APACHE` to `LICENSE`, matching the convention used across the other
  crates, and repointed the README reference.
- Dropped the deprecated `authors` field and repointed `repository` / `homepage` at
  the organisation.
- Refreshed dependencies (`cargo update`); `thiserror` moved to 2.0.20.
- Publishing is now driven by publishing a GitHub release rather than by pushing to
  `main`. The previous workflow auto-created a release and published on every push whose
  version differed, which meant a merge could reach crates.io without an explicit
  decision to ship. The release tag is now the trigger, its version is checked against
  `Cargo.toml`, and the job refuses to publish a commit not contained in `main`.
- Publishing now uses crates.io trusted publishing instead of a stored registry token.

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

[0.2.3]: https://github.com/ATRAPSLLC/cowfile/compare/v0.2.2...v0.2.3
[0.2.2]: https://github.com/ATRAPSLLC/cowfile/compare/v0.2.1...v0.2.2
[0.2.1]: https://github.com/ATRAPSLLC/cowfile/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/ATRAPSLLC/cowfile/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/ATRAPSLLC/cowfile/releases/tag/v0.1.0
