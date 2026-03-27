# Contributing to warpd-enhanced

Thank you for your interest in contributing!

## This is a Fork

This is an enhanced fork of [warpd](https://github.com/rvaiya/warpd). For contributions to the original project, please visit the upstream repository.

## Reporting Issues

When filing an issue, please include:

 - A complete description of the problem and minimal steps to reproduce it
 - Platform (Wayland/X11/macOS)
 - Output of `warpd -v`
 - Your config file (or minimal config that reproduces the issue)
 - Screen setup (number of monitors, resolution)
 - Whether the issue occurs with or without grid shifting enabled

**For grid shifting specific issues:**
 - Which Shift+key combinations you used
 - Your `hint_shift_amount` setting
 - Description of unexpected behavior

## Feature Requests

**For enhancements to grid shifting or fork-specific features:**
- Open an issue here describing your use case

**For general warpd features:**
- Consider contributing to the [upstream project](https://github.com/rvaiya/warpd)
- If upstream is unresponsive, feel free to suggest it here

## Pull Requests

Pull requests are welcome! Please:

1. Keep changes focused and well-documented
2. Test on your platform (mention which in PR description)
3. Follow the existing code style (use `.clang-format`)
4. Update relevant documentation (README.md, man page, CHANGELOG-ENHANCED.md)

## Development Setup

```bash
git clone https://github.com/MikkieMuis/warpd-enhanced.git
cd warpd-enhanced
make
sudo make install
```

Test your changes locally before submitting.

## Questions?

Open an issue for questions about the grid shifting feature or fork-specific functionality.

---

**Note:** The master branch is the main development branch. Things may break between releases.
