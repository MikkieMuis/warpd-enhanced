# warpd-enhanced

**An enhanced fork of [warpd](https://github.com/rvaiya/warpd) with interactive grid shifting**

A modal keyboard driven interface for mouse manipulation.

## Enhancements in this Fork

### Interactive 8-Way Grid Shifting

This fork adds **real-time manual grid alignment** for hint mode, solving the problem where hint labels don't align with actual UI elements in applications like Thunderbird, file managers, or complex web interfaces.

**Features:**
- **8-way directional shifting**: Move the entire hint grid in any direction using intuitive Shift+key combinations
- **Configurable shift amount**: Control how many pixels to move per keypress (default: 10px)
- **Accumulative shifts**: Multiple keypresses stack for precise positioning
- **Auto-reset**: Grid position resets on each new hint mode activation
- **Zero visual overhead**: No additional UI elements, just the grid moving in real-time

**Key Bindings:**
```
Shift+U    Shift+I    Shift+O
   ↖          ↑          ↗
(up-left)   (up)   (up-right)

Shift+J                Shift+L
   ←                      →
 (left)               (right)

Shift+<    Shift+M    Shift+>
   ↙          ↓          ↘
(down-left) (down) (down-right)
```

**Configuration:**
Add to your `~/.config/warpd/config`:
```
hint_shift_amount: 10  # pixels to shift per keypress
```

**Usage Example:**
1. Activate hint mode: `Super+h`
2. Grid doesn't align? Press `Shift+I` to shift up, `Shift+L` to shift right, etc.
3. Once aligned, type the hint label to click
4. Next activation automatically resets grid position

## Quick Start

### Installation

**For openSUSE Tumbleweed:**
```bash
# Install dependencies
sudo zypper install libXi-devel libXinerama-devel libXtst-devel libXfixes-devel \
                     libXft-devel wayland-devel libxkbcommon-devel cairo-devel

# Clone and build
git clone https://github.com/MikkieMuis/warpd-enhanced.git
cd warpd-enhanced
make
sudo make install
```

**For other distributions:**
See the [Dependencies](#dependencies) section below for required packages.

### Basic Sway/Wayland Configuration

Add to your `~/.config/sway/config`:
```
# warpd keybindings
bindsym $mod+g exec warpd --grid
bindsym $mod+h exec warpd --hint --oneshot --click 1
bindsym $mod+Escape exec pkill -x warpd  # Emergency exit
```

Add to your `~/.config/warpd/config`:
```
hint_chars: abcdefghijklmnopqrstuvwxyz0123456789
hint_bgcolor: #00000000        # Transparent background
hint_fgcolor: #ff0000          # Red labels
hint_shift_amount: 10          # Grid shift: 10 pixels per keypress
```

Reload Sway: `$mod+Shift+c`

### Compatibility

**Tested on:**
- openSUSE Tumbleweed + Sway (Wayland)

**Should work on:**
- All platforms supported by upstream warpd (Linux X11/Wayland, macOS)
- Any Wayland compositor (Sway, Hyprland, etc.)
- X11 window managers (i3, bspwm, etc.)

The grid shifting feature is platform-agnostic and uses the same input handling as the original warpd. If warpd works on your system, this enhanced version should work too.

**Feedback welcome!** If you test on other platforms/distros, please report your experience via [GitHub issues](https://github.com/MikkieMuis/warpd-enhanced/issues).

### Releases & Packages

**Current status:** No official releases or distribution packages yet.

**Installation:** Build from source (see above). The build process is straightforward and takes ~30 seconds.

**Future plans:**
- Tagged releases may come if there's community interest
- Distribution packages (AUR, etc.) are not currently planned
- Feel free to package this for your distribution (attribution appreciated!)

**Note:** This is a personal fork maintained for my own use. For stable, packaged versions of warpd, see the [original project](https://github.com/rvaiya/warpd).

---

## Original warpd Description

# Demo

## Hint Mode `Alt-Meta-x`

<p align="center">
<img src="demo/hints.gif" height="400px"/>
</p>

## Grid Mode `Alt-Meta-g`

<p align="center">
<img src="demo/warp.gif" height="400px"/>
</p>

## Normal Mode `Alt-Meta-c`

<p align="center">
<img src="demo/discrete.gif" height="400px"/>
<img src="demo/discrete2.gif" height="400px" width="711px"/>
</p>


# Dependencies

## X

The usual array of X libraries:

 - libxi
 - libxinerama
 - libxft
 - libxfixes
 - libxtst
 - libx11

## Wayland (sway/wlroots only (**no gnome support**))

 - libwayland-client
 - cairo
 - xkbcommon

*Note:* The wayland port has several limitations due
to the nature of Wayland's architecture.

See the LIMITATIONS section of the man page for more details.

## MacOS:

 - The standard Xcode command line developer tools.

# Installation

Make sure you have the appropriate dependencies for your system:

E.g

## debian/ubuntu:

```
git clone https://github.com/rvaiya/warpd.git
cd warpd
sudo apt-get install \
	libxi-dev \
	libxinerama-dev \
	libxft-dev \
	libxfixes-dev \
	libxtst-dev \
	libx11-dev \
	libcairo2-dev \
	libxkbcommon-dev \
	libwayland-dev &&
make && sudo make install
```

By default warpd will build a single binary for both X and wayland. An X or
Wayland only binary can be generated by setting either `DISABLE_WAYLAND` or
`DISABLE_X` at compile time.

## macos:

```
curl -L https://github.com/rvaiya/warpd/releases/download/v1.3.5/warpd-1.3.5-osx.tar.gz |  sudo tar xzvfC - / && launchctl load /Library/LaunchAgents/com.warpd.warpd.plist
```

Uninstallation:

```
sudo rm /usr/local/bin/warpd /usr/local/share/man/man1/warpd.1.gz /Library/LaunchAgents/com.warpd.warpd.plist
```

or (from source)

```
# Install the xcode command line tools if you
# don't already have them.
xcode-select --install

make && sudo make install && launchctl load /Library/LaunchAgents/com.warpd.warpd.plist
```

Uninstallation:

```
sudo make uninstall
```

*Note:* On initialization you may be prompted to add the warpd binary to your
accessibility settings. **If you are upgrading it may also be necessary to run
`sudo tccutil reset Accessibility` (this will remove all applications
from your accessibility settings)**. The service is now also managed by a
launchd service (see below) and should not be explicitly started by the
user.

*Note 2:* Some programs (e.g iTerm) have a 'secure input mode' that may need to be
disabled in order for warpd to work properly.

The service can be disabled with

```
launchctl unload /Library/LaunchAgents/com.warpd.warpd.plist
```

# Quickstart

1. Run `warpd`

## Hint Mode
2. Press `A-M-x` (`alt+meta+x`) to generate a list of hints
3. Enter the key sequence associated with the desired target to warp the pointer to that location and enter normal mode.
4. Use the normal mode movement keys to select the final desination (see Normal Mode).

## Grid Mode
2. Press `A-M-g` (meta is the command key) to activate the warping process.
3. Use `u`,`i`,`j`,`k` to repeatedly navigate to different quadrants.
4. Press `m` to left click, `,` to middle click or `.` to right click.
5. See Normal Mode

## Normal Mode
2. Press `A-M-c` to activate normal mode.
3. Use the normal movement keys (default `hjkl`) to adjust the cursor.
4. Press `m` to left click, `,` to middle click or `.` to right click.
5. Press `escape` to quit.

A drag movement can be simulated from any of the above modes by focusing on the
source and then pressing the `drag_key` (default `v`) which will cause normal
mode to be activated for selection of the drag target.

A more comprehensive description can be found in the [man page](warpd.1.md) (along with a list of options).

## Wayland

*Note:* Wayland does not permit clients to globally bind hotkeys. These must be
bound within the compositor using warpd's oneshot flags.

E.g

**On sway**:

```
# warpd hotkeys

bindsym Mod4+Mod1+x exec warpd --hint
bindsym Mod4+Mod1+c exec warpd --normal
bindsym Mod4+Mod1+g exec warpd --grid
```

**Using sxhkd**:

```
# warpd hotkeys

Alt + super + x
  exec warpd --hint

Alt + super + c
  warpd --normal

Alt + super + g
  warpd --grid
```

# Packages:

`warpd` is currently available on the following distributions:

## Arch

Available in the [AUR](https://aur.archlinux.org/): [warpd](https://aur.archlinux.org/packages/warpd/), [warpd-wayland](https://aur.archlinux.org/packages/warpd-wayland), [warpd-git](https://aur.archlinux.org/packages/warpd-git) maintained by Matheus Fillipe.

If you are interesting in adding warpd to your distribution's repository please contact me.

# Limitations/Bugs

- Programs which use Xinput and or Xtest for keyboard may not work correctly
  (e.g synergy). If a specific program which you feel should be working does
  not please file an [issue](https://github.com/rvaiya/warpd/issues).

- The hack used for pointer hiding on OSX doesn't work on some programs (e.g
  iTerm). The original cursor will consequently be visible in such cases,
  though functionality should be otherwise unaffected.

- Wayland support has several limitations (see CAVEATS in the man page).

# Contributions

A special thanks to

 - **[Raheman Vaiya](https://github.com/rvaiya)** - For creating warpd and making this fork possible.
 - Pete Fein - For encouragement and early adoption.
 - Matheus Fillipe - For the original border radius patch as well as numerous bug reports and feature requests.
 - The Kaleidoscope/Vimperator projects - For inspiration.
 - Drew Devault - For making the Wayland ecosystem inhabitable.

---

## About This Fork

**warpd is an excellent tool by [Raheman Vaiya](https://github.com/rvaiya).** This fork simply adds one feature I needed: interactive grid shifting for hint mode on Wayland.

**Original warpd:** [github.com/rvaiya/warpd](https://github.com/rvaiya/warpd)

### Why This Fork Exists

The original warpd works great! However, on Wayland, hint mode can't detect clickable elements and uses a uniform grid instead. In complex UIs (Thunderbird, file managers, web apps), this grid rarely aligns with actual buttons/links.

This fork adds real-time grid shifting - press Shift+direction keys to move the grid until it aligns perfectly. Problem solved!

### Should You Use This Fork?

**Use the original warpd if:**
- You're on X11 (hint mode can detect elements)
- You primarily use grid mode or normal mode
- You want the stable, well-tested version

**Try this fork if:**
- You're on Wayland and use hint mode frequently
- Misaligned hints frustrate you in complex UIs
- You want to shift the grid manually

### Fork Maintenance

This is primarily a personal fork maintained for my own workflow. I'll:
- ✅ Keep it working for my use case (openSUSE + Sway)
- ✅ Accept bug fix PRs
- ✅ Welcome compatibility reports from other platforms
- ⚠️  Be selective about feature additions (to keep it simple)

For general warpd features/issues, please use the [upstream project](https://github.com/rvaiya/warpd/issues).

### Contributing

Bug reports and compatibility feedback are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for details.
