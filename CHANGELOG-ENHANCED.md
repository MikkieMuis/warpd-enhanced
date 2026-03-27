# Changelog - warpd-enhanced

All notable changes to this fork are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased]

### Added
- Interactive 8-way grid shifting for hint mode
  - Shift the entire hint grid in real-time using Shift+key combinations
  - 8 directional keys: U/I/O (up row), J/L (middle row), </M/> (bottom row)
  - Configurable shift amount via `hint_shift_amount` config option (default: 10px)
  - Accumulative shifts - multiple keypresses stack for precise positioning
  - Auto-reset on each new hint mode activation
- New configuration options:
  - `hint_shift_amount`: Number of pixels to shift per keypress (default: 10)
  - `hint_shift_up`: Key binding for shifting up (default: I)
  - `hint_shift_down`: Key binding for shifting down (default: M)
  - `hint_shift_left`: Key binding for shifting left (default: J)
  - `hint_shift_right`: Key binding for shifting right (default: L)
  - `hint_shift_up_left`: Key binding for up-left diagonal (default: U)
  - `hint_shift_up_right`: Key binding for up-right diagonal (default: O)
  - `hint_shift_down_left`: Key binding for down-left diagonal (default: less/<)
  - `hint_shift_down_right`: Key binding for down-right diagonal (default: greater/>)

### Fixed
- Typo in X/input.c: `input_evnet` → `input_event`

### Changed
- Updated README with fork information and grid shifting documentation
- Added Quick Start section for openSUSE Tumbleweed
- Added Sway/Wayland configuration examples

## Upstream Version

This fork is based on [warpd v1.3.5](https://github.com/rvaiya/warpd) (commit 01650ea).

For upstream changes, see the original [CHANGELOG.md](CHANGELOG.md).

---

## Why This Fork?

The original warpd project has minimal activity (~11 commits in 2+ years). This fork adds the interactive grid shifting feature that significantly improves hint mode usability on Wayland, especially for complex UIs where hints don't naturally align with clickable elements.

## Contributing

- For enhancements specific to this fork: Open issues/PRs here
- For general warpd features: Consider contributing to the [upstream project](https://github.com/rvaiya/warpd)
