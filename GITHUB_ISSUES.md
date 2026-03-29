# GitHub Issues for warpd-enhanced

Two starter issues to invite community participation.

---

## Issue #1: Feature Requests

**Title:** `Feature requests — what features would you like to see?`

**Labels:** `enhancement`

**Body:**
```markdown
Got an idea for improving warpd-enhanced?

Whether it's a new grid shifting feature, better hint alignment, or Wayland-specific improvements — we want to hear it.

Some ideas already being considered:

- Configurable grid shift increments per direction
- Save/restore grid positions
- Multi-monitor grid shift improvements
- Additional hint mode variants
- Better integration with other keyboard-driven tools

But we want to hear what *you* need for your workflow.

No idea is too small. Drop your suggestions here!
```

---

## Issue #2: Bug Reports

**Title:** `Bug reports — something not working as expected?`

**Labels:** `bug`

**Body:**
```markdown
Found something broken or not behaving correctly?

Please describe:

- **What you did:** Which warpd mode and grid shift keys you used
- **What you expected:** How it should behave
- **What happened:** What actually occurred
- **Your setup:** 
  - Distribution (e.g., openSUSE Tumbleweed, Arch, Ubuntu)
  - Compositor (e.g., Sway, Hyprland, i3 on X11)
  - warpd-enhanced version (or commit hash)

All reports welcome — grid alignment issues, shift amount problems, crashes, unexpected behavior, anything.

**Note:** For issues with the original warpd functionality (not grid shifting), please report to the [upstream project](https://github.com/rvaiya/warpd/issues).
```

---

## Issue #3: Platform Compatibility Reports (Optional)

**Title:** `Platform compatibility — does it work on your system?`

**Labels:** `compatibility`, `help wanted`

**Body:**
```markdown
Tested warpd-enhanced on your platform? Let us know how it went!

We're especially interested in hearing from users on:

- Different Linux distributions (Arch, Ubuntu, Fedora, NixOS, etc.)
- Different Wayland compositors (Hyprland, river, labwc, etc.)
- X11 window managers (i3, bspwm, dwm, etc.)
- macOS

Please share:

- ✅ **Platform:** Distribution + compositor/WM
- ✅ **Status:** Working perfectly / Minor issues / Not working
- ✅ **Grid shift:** Does it work as expected?
- ✅ **Notes:** Any quirks, workarounds, or special setup needed

This helps other users know what to expect and helps prioritize compatibility fixes!
```

---

## How to Create These Issues

1. Go to https://github.com/MikkieMuis/warpd-enhanced/issues/new
2. Copy the title and body from above
3. Add the appropriate labels
4. Submit!

Or use the GitHub CLI:
```bash
gh issue create --repo MikkieMuis/warpd-enhanced \
  --title "Feature requests — what features would you like to see?" \
  --label enhancement \
  --body "Got an idea for improving warpd-enhanced?..."
```
