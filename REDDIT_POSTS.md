# Reddit Posts Documentation

This file contains ready-to-use Reddit posts for promoting warpd-enhanced.

---

## r/swaywm Post (POSTED: 2026-03-28)

**Subreddit:** r/swaywm  
**Post URL:** https://old.reddit.com/r/swaywm/submit?selftext=true  
**Flair:** Release (or Utility)  
**Best time to post:** Weekday mornings 8-11am EST

### Title (Choose One):

**Option 1 (Recommended - Direct & Casual):**
```
I got fed up with misaligned hint grids in warpd, so I forked it and added 8-way grid shifting
```

**Option 2 (More Descriptive):**
```
warpd-enhanced: Added interactive grid shifting for keyboard-driven mouse control on Wayland
```

**Option 3 (Problem-Focused):**
```
Fixed warpd's misaligned hint mode on Wayland with real-time grid shifting
```

### Post Body:

```markdown
Got fed up waiting for hint mode grid alignment issues to be solved on Wayland, so I forked warpd and now actively maintain **warpd-enhanced** - specifically built and tested for Sway/Wayland users.

**GitHub:** https://github.com/MikkieMuis/warpd-enhanced

## The Problem

On Wayland, warpd's hint mode uses a uniform grid (can't detect clickable elements like it does on X11). In complex UIs like Thunderbird, file managers, or web apps, the grid rarely aligns with actual buttons and links.

## The Solution

Added 8-way directional grid shifting - press Shift+direction keys to move the entire hint grid in real-time until it aligns perfectly with your UI elements.

**Key bindings:**
```
Shift+U    Shift+I    Shift+O
   ↖          ↑          ↗

Shift+J                Shift+L
   ←                      →

Shift+<    Shift+M    Shift+>
   ↙          ↓          ↘
```

## Features

- ✅ Real-time manual grid alignment for hint mode
- ✅ Configurable shift amount (default: 10px per keypress)
- ✅ Accumulative shifts for precise positioning
- ✅ Auto-reset on each hint mode activation
- ✅ Cross-platform (Linux X11/Wayland, macOS)
- ✅ Both hint mode and grid mode for flexible mouse control

I specifically test on openSUSE Tumbleweed + Sway, but it should work on all platforms since the original warpd does.

## Installation

Builds from source in ~30 seconds. No AppImage/packaging headaches - just clone, make, install.

Full installation instructions (with dependencies for various distros) in the README.

## Sway Config Example

```
bindsym $mod+g exec warpd --grid
bindsym $mod+h exec warpd --hint --oneshot --click 1
```

Add to `~/.config/warpd/config`:
```
hint_shift_amount: 10
```

---

**Note:** This is a personal fork I maintain for my daily workflow. For the stable, original version, see [rvaiya/warpd](https://github.com/rvaiya/warpd).

If you try it out, let me know how it works for you! Open issues on GitHub if you hit any problems - I'm actively maintaining it.
```

---

## Future Subreddit Targets (Next Week)

### r/unixporn
- **Focus:** Visual appeal + workflow
- **Best time:** Weekday evenings
- **Style:** More casual, can include screenshots/GIFs
- **Flair:** Check available flairs when posting

### r/Wayland
- **Focus:** Technical Wayland-specific features
- **Best time:** Weekday mornings
- **Style:** Technical, focus on Wayland limitations you solved
- **Flair:** Check available flairs when posting

### r/linux
- **Focus:** General Linux tool, cross-distro compatibility
- **Best time:** Weekday mornings
- **Style:** Professional, emphasize cross-platform nature
- **Flair:** Software/Tool

### r/commandline
- **Focus:** Keyboard-driven workflow, CLI tools
- **Best time:** Weekday mornings
- **Style:** Highlight keyboard-only control
- **Flair:** Check available flairs when posting

---

## Post-Posting Checklist

After posting to any subreddit:

- [ ] Check back within first 2 hours to answer questions
- [ ] Be responsive and friendly to comments
- [ ] Accept feedback gracefully (even criticism)
- [ ] If someone reports a bug, acknowledge it professionally
- [ ] Update README if multiple people request the same feature
- [ ] Track which posts got the most engagement for future reference

---

## Tips for Maximum Engagement

1. **Timing matters:** Post weekday mornings (8-11am EST) for best visibility
2. **Avoid weekends:** Tech subreddits have less engagement Sat/Sun
3. **First 2 hours are critical:** Quick responses boost post visibility
4. **Be humble:** "I made this" not "This is amazing"
5. **Acknowledge the original:** Always credit rvaiya/warpd
6. **Don't spam:** Wait at least 1 week between subreddit posts
7. **Cross-posting:** Wait 2-3 days between related subreddits

---

## Engagement Metrics to Track

After each post, note:
- Upvotes
- Comments
- GitHub stars gained (check Insights → Traffic → Referring sites)
- Issues opened
- Actual user feedback

This helps you understand which communities are most interested.

---

## Template for Future Subreddits

When adapting this post for other subreddits, adjust:

1. **Title:** Keep the "fed up, so I forked it" energy - it's authentic
2. **Problem statement:** Tailor to the subreddit's focus (Wayland for r/wayland, keyboard workflow for r/commandline, etc.)
3. **Features:** Emphasize what matters to that community
4. **Installation:** Always mention "30 seconds to build"
5. **Note:** Always credit the original warpd project

---

## GitHub Comment Template (for related issues)

When you find relevant GitHub issues where your fork might help:

```markdown
Hey @username - Got fed up waiting, so I forked and actively maintain **[warpd-enhanced](https://github.com/MikkieMuis/warpd-enhanced)** - should work on all platforms (Linux X11/Wayland, macOS).

I specifically test on openSUSE Tumbleweed + Sway. No AppImage/WebKit headaches - just a clean 30-second build from source.

Full installation (including dependencies for other distros) in the README. If you hit issues, open an issue - I'm actively maintaining it.

Hope this helps!
```

Adjust the technical details based on the specific issue you're commenting on.
