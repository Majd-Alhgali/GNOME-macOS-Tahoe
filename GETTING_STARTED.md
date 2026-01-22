# How to Make GNOME 49 Look Like macOS Tahoe 2026

This comprehensive guide will help you transform your GNOME 49 desktop into a beautiful macOS Tahoe 2026-inspired environment.

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Quick Start (5 Minutes)](#quick-start-5-minutes)
- [Detailed Installation](#detailed-installation)
- [Essential Configuration](#essential-configuration)
- [Recommended Extensions](#recommended-extensions)
- [Troubleshooting](#troubleshooting)
- [GNOME 49 Compatibility](#gnome-49-compatibility)

## Prerequisites

### System Requirements

- **GNOME Desktop Environment**: Version 43+ (including GNOME 49)
- **Operating System**: Any Linux distribution with GNOME
  - Fedora 39+
  - Ubuntu 23.04+
  - Arch Linux
  - Pop!_OS 22.04+
  - Other GNOME-based distributions

### Required Tools

- Git
- Python 3.6+
- GTK 3.0 and GTK 4.0 libraries
- GNOME Tweaks or [Refine](https://flathub.org/apps/page.tesk.Refine) (Recommended)

## Quick Start (5 Minutes)

Follow these steps to get the macOS Tahoe look on your GNOME 49 desktop quickly:

### Step 1: Clone the Repository

```bash
git clone https://github.com/kayozxo/GNOME-macOS-Tahoe
cd GNOME-macOS-Tahoe
```

### Step 2: Run the Interactive Installer

```bash
./install.sh
```

The installer will:
- Automatically install [Gum](https://github.com/charmbracelet/gum) if needed (for interactive menus)
- Present an easy-to-use menu with all installation options
- Guide you through theme installation, accent color selection, and extras

### Step 3: Select Your Preferences

In the interactive menu, choose:

1. **Install Theme** → Select Light, Dark, or Both
2. **Generate Accent Colors** → Choose from 16 beautiful colors (optional)
3. **Install Libadwaita Override** → Enable for GTK4 apps and GNOME Shell (recommended)
4. **Install Extras** → Icons, cursors, wallpapers, and more

### Step 4: Apply the Theme

Using GNOME Tweaks or Refine:
1. Open **Tweaks** → **Appearance**
2. Select **Applications**: `Tahoe-Dark` or `Tahoe-Light`
3. Select **Shell**: `Tahoe-Dark` or `Tahoe-Light`
4. Optionally select colored variant like `Tahoe-Dark-Blue`

### Step 5: Install Essential Extensions

For the complete macOS Tahoe experience, install:
- [Open Bar](https://extensions.gnome.org/extension/6580/open-bar/) - macOS-style top bar
- [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock/) - macOS-style dock
- [Blur My Shell](https://extensions.gnome.org/extension/3193/blur-my-shell/) - Beautiful blur effects

**Continue to [Extension Configuration Guide](.config/EXTENSIONS.md) for detailed setup.**

### Step 6: Reboot

Log out and back in, or reboot your system to see the changes!

🎉 **Congratulations!** Your GNOME 49 desktop now looks like macOS Tahoe 2026!

## Detailed Installation

### Command-Line Installation (Advanced Users)

If you prefer command-line flags over the interactive menu:

#### Install Dark Theme Only

```bash
./install.sh -d
```

#### Install Light Theme Only

```bash
./install.sh -l
```

#### Install with Accent Color

```bash
# Generate all 16 accent color variants
./install.sh --colors

# Install dark theme with blue accent
./install.sh -d --color blue

# Install light theme with green accent
./install.sh -l --color green
```

#### Install with Libadwaita Override

For modern GTK4 applications and GNOME Shell accent colors:

```bash
# Dark theme with libadwaita override
./install.sh -d -la

# Dark blue theme with libadwaita override and GNOME Shell theming
./install.sh -d --color blue -la

# Light theme with purple accent and libadwaita
./install.sh -l --color purple -la
```

#### Install Wallpapers

```bash
./install.sh -w
```

#### Install Extras (All-in-One)

The interactive menu provides an "Install Extras" option that includes:
- MacTahoe icons
- MacTahoe wallpapers
- WhiteSur cursors
- Ulauncher theme
- GDM theme

### Available Accent Colors

Choose from 16 beautiful accent colors:

| Color   | Hex Code | Color   | Hex Code |
|---------|----------|---------|----------|
| Blue    | #3b82f6  | Rose    | #f43f5e  |
| Green   | #10b981  | Emerald | #059669  |
| Purple  | #8b5cf6  | Violet  | #7c3aed  |
| Pink    | #ec4899  | Amber   | #d97706  |
| Orange  | #f59e0b  | Cyan    | #06b6d4  |
| Red     | #ef4444  | Lime    | #84cc16  |
| Teal    | #14b8a6  | Sky     | #0ea5e9  |
| Indigo  | #6366f1  | Slate   | #64748b  |

After installation, select your preferred color variant in **Tweaks → Appearance** (e.g., `Tahoe-Dark-Blue`, `Tahoe-Light-Green`).

## Essential Configuration

### 1. Top Bar (Open Bar Extension)

Open Bar provides the macOS-style top bar experience:

1. Install [Open Bar](https://extensions.gnome.org/extension/6580/open-bar/)
2. Open **Extension Manager** → **Open Bar** → **Settings**
3. Go to **Admin** tab → Click **Import**
4. Select config file:
   - Dark Mode: `.config/extensions/openBar/Tahoe-Dark`
   - Light Mode: `.config/extensions/openBar/Tahoe-Light`

### 2. Dock (Dash to Dock Extension)

Configure the dock to look like macOS:

1. Install [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock/)
2. Follow the [Dash to Dock setup guide](.config/EXTENSIONS.md#3-dash-to-dock)
3. Key settings:
   - Position: Bottom
   - Icon size: 48-56px
   - Enable transparency and blur

### 3. Window Management (Tiling Shell)

For macOS-like window management:

1. Install [Tiling Shell](https://extensions.gnome.org/extension/7065/tiling-shell/)
2. Import the provided config: `.config/extensions/tiling-shell/tilingshell-settings.txt`

### 4. Workspace Indicator (Space Bar)

Add the macOS-style workspace indicator:

1. Install [Space Bar](https://extensions.gnome.org/extension/5090/space-bar/)
2. Follow the [Space Bar setup guide](.config/EXTENSIONS.md#5-space-bar)

### 5. Blur Effects (Blur My Shell)

Enable beautiful blur effects:

1. Install [Blur My Shell](https://extensions.gnome.org/extension/3193/blur-my-shell/)
2. Create pipelines as shown in [Blur My Shell guide](.config/EXTENSIONS.md#2-blur-my-shell)
3. Apply blur to panel, dock, and overview

## Recommended Extensions

### Essential Extensions for macOS Tahoe Look

| Extension | Purpose | Priority |
|-----------|---------|----------|
| [Open Bar](https://extensions.gnome.org/extension/6580/open-bar/) | macOS-style top bar | ⭐⭐⭐ Required |
| [Dash to Dock](https://extensions.gnome.org/extension/307/dash-to-dock/) | macOS-style dock | ⭐⭐⭐ Required |
| [User Themes](https://extensions.gnome.org/extension/19/user-themes/) | Enable custom shell themes | ⭐⭐⭐ Required |
| [Blur My Shell](https://extensions.gnome.org/extension/3193/blur-my-shell/) | Blur effects | ⭐⭐ Highly Recommended |
| [Space Bar](https://extensions.gnome.org/extension/5090/space-bar/) | Workspace indicator | ⭐⭐ Highly Recommended |
| [Tiling Shell](https://extensions.gnome.org/extension/7065/tiling-shell/) | Window tiling | ⭐ Recommended |
| [Gnome 4x UI Improvements](https://extensions.gnome.org/extension/4158/gnome-40-ui-improvements/) | UI enhancements | ⭐ Recommended |
| [Vitals](https://extensions.gnome.org/extension/1460/vitals/) | System monitor | Optional |

### Installing Extensions

**Method 1: Extension Manager (Recommended)**

```bash
flatpak install flathub com.mattjakeman.ExtensionManager
```

**Method 2: Web Browser**
Visit [extensions.gnome.org](https://extensions.gnome.org/) with Firefox or GNOME Web

**Method 3: Command Line**
Use `gnome-extensions-cli` or download from extension pages

## Troubleshooting

### Theme Not Applying

**Problem**: Theme doesn't show up in GNOME Tweaks

**Solutions**:
1. Ensure themes are installed to `~/.themes/` directory
2. Restart GNOME Shell: Press `Alt+F2`, type `r`, press Enter (X11 only)
3. Log out and back in
4. Check permissions: `chmod -R 755 ~/.themes/Tahoe-*`

### Libadwaita Apps Not Themed

**Problem**: GTK4 applications (like GNOME Settings, Files) don't use the theme

**Solution**:
```bash
# Reinstall with libadwaita override
./install.sh -d -la  # or -l -la for light theme
```

**Note**: This is a known limitation of libadwaita. The override works but apps won't support multiple themes.

### Flatpak Apps Not Themed

**Problem**: Flatpak applications don't use the custom theme

**Solution**:
```bash
# Grant Flatpak access to theme directories
sudo flatpak override --filesystem=xdg-config/gtk-3.0
sudo flatpak override --filesystem=xdg-config/gtk-4.0

# Install theme for Flatpak
./install.sh --flatpak
```

### GNOME Shell Theme Not Applying

**Problem**: Top panel and overview don't use the custom theme

**Solutions**:
1. Ensure [User Themes](https://extensions.gnome.org/extension/19/user-themes/) extension is installed and enabled
2. Install with libadwaita flag: `./install.sh -d -la`
3. Select the shell theme in GNOME Tweaks → Appearance → Shell
4. Restart GNOME Shell (X11: `Alt+F2`, type `r`) or log out/in

### Accent Colors Not Showing

**Problem**: Colored theme variants (like Tahoe-Dark-Blue) don't appear

**Solution**:
```bash
# Generate specific color
./install.sh --color blue

# Or generate all colors
./install.sh --colors

# Install to ~/.themes
./install.sh -d --color blue -la
```

### Extensions Not Working on GNOME 49

**Problem**: Some extensions show as incompatible

**Solutions**:
1. Wait for extension updates to support GNOME 49
2. Try forcing compatibility (may be unstable):
   ```bash
   gnome-extensions enable extension-name@domain
   ```
3. Check for alternative extensions
4. Report issues to extension developers

## GNOME 49 Compatibility

### Current Status

The Tahoe theme is designed to work with GNOME 43+ including:
- ✅ GNOME 43, 44, 45, 46, 47, 48
- ✅ GNOME 49 (tested and compatible)

### GTK Version Support

- ✅ **GTK 3.0**: Full support
- ✅ **GTK 4.0**: Full support with libadwaita override
- ✅ **GNOME Shell**: Full support via User Themes extension

### Known GNOME 49-Specific Notes

1. **Libadwaita Changes**: GNOME 49 may have updated libadwaita. Reinstall the override if needed:
   ```bash
   ./install.sh -d -la
   ```

2. **Extension Compatibility**: Some extensions may need updates for GNOME 49. Check:
   - Extension Manager for updates
   - [extensions.gnome.org](https://extensions.gnome.org/) for compatibility badges

3. **New GNOME 49 Features**: The theme automatically adapts to new GNOME features through CSS inheritance.

### Testing Your Setup

After installation, verify everything works:

1. **Theme Applied**: Check GTK3 apps (Nautilus, etc.)
2. **Shell Themed**: Check top panel and overview
3. **GTK4 Apps**: Check Settings, Console, Files
4. **Extensions**: Verify all extensions are active
5. **Accent Colors**: Check if custom colors appear in UI elements

## Next Steps

1. **Fine-tune Extensions**: See [Extension Configuration Guide](.config/EXTENSIONS.md)
2. **Install Wallpapers**: Check `.config/walls/` for macOS Tahoe wallpapers
3. **Customize Further**: Explore additional theme options in the installer
4. **Install App Launcher**: Try [Ulauncher](https://ulauncher.io/) with the Liquid Glass theme

## Additional Resources

- **Main Repository**: [github.com/kayozxo/GNOME-macOS-Tahoe](https://github.com/kayozxo/GNOME-macOS-Tahoe)
- **Extension Setup**: [.config/EXTENSIONS.md](.config/EXTENSIONS.md)
- **Wallpapers**: [.config/walls/](.config/walls/)
- **Reddit Discussion**: [r/unixporn post](https://www.reddit.com/r/unixporn/comments/1ogcgqg/gnome_macos_tahoe_v060/)

## Support

- 🐛 **Report Issues**: [GitHub Issues](https://github.com/kayozxo/GNOME-macOS-Tahoe/issues)
- 💬 **Discuss**: [Reddit r/unixporn](https://www.reddit.com/r/unixporn/)
- ☕ **Support Development**: [Buy Me a Coffee](https://www.buymeacoffee.com/kayozxo)

---

**Enjoy your macOS Tahoe-styled GNOME 49 desktop! 🎨**
