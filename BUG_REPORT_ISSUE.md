# Bug Report Issue Template for warpd-enhanced

---

## Title
`Bug reports — something not working as expected?`

## Labels
`bug`

## Body

```markdown
Found a bug? Something not working right?

Just describe what happened and I'll take a look!

Include whatever details you think are helpful - your setup, what you were doing, error messages, etc.

All reports welcome!
```

---

## How to Create This Issue

### Option 1: Via GitHub Web Interface
1. Go to https://github.com/MikkieMuis/warpd-enhanced/issues/new
2. Copy the title: `Bug reports — something not working as expected?`
3. Copy the body text above
4. Add label: `bug`
5. Click "Submit new issue"

### Option 2: Via GitHub CLI
```bash
gh issue create --repo MikkieMuis/warpd-enhanced \
  --title "Bug reports — something not working as expected?" \
  --label bug \
  --body "Found something broken or not behaving correctly with warpd-enhanced?

Please describe:

### What you did
Which warpd mode did you use? What grid shift keys did you press?

### What you expected
How should it behave?

### What actually happened
What occurred instead?

### Your setup
- **Distribution:** (e.g., openSUSE Tumbleweed, Arch, Ubuntu)
- **Compositor/WM:** (e.g., Sway, Hyprland, i3 on X11)
- **warpd-enhanced version:** (commit hash or build date)
- **Wayland or X11?**

### Additional info (optional)
Any error messages, screenshots, or other relevant details?

---

All bug reports welcome — grid alignment issues, shift problems, crashes, unexpected behavior, anything!"
```
