# Contributing to warpd-enhanced

Thank you for your interest in contributing!

## This is a Fork

This is an enhanced fork of [warpd](https://github.com/rvaiya/warpd). For contributions to the original project, please visit the upstream repository.

## Reporting Issues

**Bug reports and compatibility feedback are very welcome!** Issues help improve the project.

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
- Open an issue to discuss your idea first
- Include your use case and why it would be valuable

**For general warpd features:**
- Consider contributing to the [upstream project](https://github.com/rvaiya/warpd)
- If upstream is unresponsive, feel free to suggest it here

## Pull Requests

**Note:** This is primarily a personal fork maintained for my own use. While I appreciate the interest, I may be selective about accepting PRs to keep the codebase aligned with my workflow.

**That said, PRs are welcome for:**
- Bug fixes (especially grid shifting issues)
- Platform compatibility improvements
- Documentation improvements
- Well-scoped enhancements that align with the fork's goals

**Before submitting a PR:**
1. Open an issue first to discuss larger changes
2. Keep changes focused and well-documented
3. Test on your platform (mention which in PR description)
4. Follow the existing code style (use `.clang-format`)
5. Update relevant documentation (README.md, CHANGELOG-ENHANCED.md)

**Please understand:**
- I may not accept all PRs (it's a personal fork, not a community project)
- Response time may vary (maintained as time permits)
- If your PR isn't accepted, you're encouraged to maintain your own fork!

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

## Alternative: Fork This Fork!

If you have ideas that diverge from this fork's direction, you're encouraged to create your own fork! That's the beauty of open source. Just maintain the MIT license and attribution chain.

**Note:** The master branch is the main development branch. Things may break between releases.
