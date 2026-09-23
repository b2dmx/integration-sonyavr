# Sony AVR integration for Remote Two Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

_Changes in the next release_

### Added
- Optional setting to show the volume on the receiver's own scale (for example
  0-74 on an STR-AN1000) instead of a percentage, so the number on the remote
  matches the receiver's display. Off by default; existing setups are unchanged.
  The scale comes from the receiver's reported minimum and maximum, and the
  volume step is applied in the same units.

### Fixed
- Sensor entities now update when the volume or mute is changed from the
  remote. `volume_up`, `volume_down`, `set_volume_level` and `mute` emitted
  only the media-player attribute, and because they set the volume
  optimistically the AVR's own `VolumeChange` notification was then a no-op,
  so the sensors never saw the change.

---

## v0.0.1 - 2024-03-16
### Initial release

## v1.0.0 - 2024-07-22
### Optimizations for battery usage and upload to remote