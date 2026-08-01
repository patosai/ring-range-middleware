# Change Log
All notable changes to this project will be documented in this file. This change log follows the conventions of [keepachangelog.com](http://keepachangelog.com/).

## [0.2.0] - 2026-08-01
### Fixed
- File bodies now serve Range responses by seeking with `RandomAccessFile` instead of streaming the entire file and filtering. This makes video/large-file partial content requests O(range size) rather than O(file size).
- Streaming range responses (non-File bodies with known length) stop reading the source once all requested ranges have been written, instead of draining the rest of the body.

## 0.1.0 - 2020-12-02
### Added
- Initial HTTP Range middleware for Ring.

[0.2.0]: https://github.com/patosai/ring-range-middleware/compare/0.1.0...0.2.0
