# Quick Reference Card - GNOME 49 macOS Tahoe 2026

A quick reference for common commands and configurations to make GNOME 49 look like macOS Tahoe 2026.

## 🚀 Quick Installation Commands

### Basic Installation

```bash
# Clone repository
git clone https://github.com/kayozxo/GNOME-macOS-Tahoe
cd GNOME-macOS-Tahoe

# Interactive installer (recommended)
./install.sh

# Dark theme only
./install.sh -d

# Light theme only
./install.sh -l

# Both themes
./install.sh -l -d
```

### With Accent Colors

```bash
# Dark theme with blue accent + libadwaita
./install.sh -d --color blue -la

# Light theme with green accent + libadwaita
./install.sh -l --color green -la

# Generate all 16 color variants
./install.sh --colors

# Dark theme with all colors
./install.sh -d --colors
```

### Update Installation

```bash
cd GNOME-macOS-Tahoe
git pull origin main
./install.sh
```

### Uninstall

```bash
./install.sh -u
```

## 🎨 Available Accent Colors

```
blue      green     purple    pink      orange    red       teal      indigo
rose      emerald   violet    amber     cyan      lime      sky       slate
```

**Usage**: `./install.sh -d --color <color> -la`

## 🔧 Essential Extensions (Must Install)

| Extension | Install Command | Priority |
|-----------|----------------|----------|
| Open Bar | [Link](https://extensions.gnome.org/extension/6580/open-bar/) | ⭐⭐⭐ Required |
| Dash to Dock | [Link](https://extensions.gnome.org/extension/307/dash-to-dock/) | ⭐⭐⭐ Required |
| User Themes | [Link](https://extensions.gnome.org/extension/19/user-themes/) | ⭐⭐⭐ Required |
| Blur My Shell | [Link](https://extensions.gnome.org/extension/3193/blur-my-shell/) | ⭐⭐ Recommended |
| Space Bar | [Link](https://extensions.gnome.org/extension/5090/space-bar/) | ⭐⭐ Recommended |

**Quick install Extension Manager**:
```bash
flatpak install flathub com.mattjakeman.ExtensionManager
```

## 📝 Configuration Import Commands

### Open Bar (Top Panel)

1. Open Extension Manager → Open Bar → Settings
2. Go to Admin tab
3. Import: `.config/extensions/openBar/Tahoe-Dark` (or Tahoe-Light)

### Tiling Shell

1. Open Tiling Shell settings
2. Scroll to bottom
3. Import: `.config/extensions/tiling-shell/tilingshell-settings.txt`

## 🛠️ Common Troubleshooting

### Theme not showing in Tweaks

```bash
# Fix permissions
chmod -R 755 ~/.themes/Tahoe-*

# Restart GNOME Shell (X11 only)
# Press Alt+F2, type: r, press Enter

# Or log out and back in
```

### Flatpak apps not themed

```bash
sudo flatpak override --filesystem=xdg-config/gtk-3.0
sudo flatpak override --filesystem=xdg-config/gtk-4.0
./install.sh --flatpak
```

### GTK4 apps (Settings, Files) not themed

```bash
./install.sh -d -la  # Dark + libadwaita
# or
./install.sh -l -la  # Light + libadwaita
```

### GNOME Shell theme not applying

1. Install User Themes extension
2. Enable it in Extensions
3. Reinstall with: `./install.sh -d -la`
4. Select shell theme in Tweaks → Appearance → Shell

## 🎯 Complete macOS Tahoe Look Checklist

- [ ] Install Tahoe theme (`./install.sh -d -la`)
- [ ] Install Open Bar extension + import config
- [ ] Install Dash to Dock extension + configure
- [ ] Install User Themes extension
- [ ] Install Blur My Shell + create pipelines
- [ ] Install Space Bar extension + configure
- [ ] Apply theme in GNOME Tweaks
- [ ] Install wallpapers (`./install.sh -w`)
- [ ] Install MacTahoe icons (via installer extras)
- [ ] Install WhiteSur cursors (via installer extras)
- [ ] Install Ulauncher theme (optional)
- [ ] Log out and back in

## 📚 Documentation Links

- [Complete Getting Started Guide](GETTING_STARTED.md) - Comprehensive setup instructions
- [Extension Configuration Guide](.config/EXTENSIONS.md) - Detailed extension setup
- [Main README](README.md) - Project overview and features
- [Wallpapers](.config/walls/) - macOS Tahoe wallpaper collection

## 💡 Pro Tips

### Switch Between Light and Dark

```bash
# Install both themes
./install.sh -l -d --color blue -la

# Switch in GNOME Tweaks:
# - Applications: Tahoe-Dark / Tahoe-Light
# - Shell: Tahoe-Dark / Tahoe-Light
```

### Use Different Accent Colors for Day/Night

```bash
# Install multiple color variants
./install.sh -d --color blue -la
./install.sh -d --color orange -la

# Switch between Tahoe-Dark-Blue and Tahoe-Dark-Orange in Tweaks
```

### Keep Theme Updated

```bash
# Add to your .bashrc or .zshrc
alias tahoe-update='cd ~/GNOME-macOS-Tahoe && git pull && ./install.sh'
```

### Backup Your Configuration

```bash
# Backup extension configs
cp -r ~/.local/share/gnome-shell/extensions ~/backup/extensions

# Backup Open Bar config
# Export via Open Bar Settings → Admin → Export
```

## 🐛 Report Issues

Found a bug or have a question?
- [GitHub Issues](https://github.com/kayozxo/GNOME-macOS-Tahoe/issues)
- [Reddit Discussion](https://www.reddit.com/r/unixporn/comments/1ogcgqg/gnome_macos_tahoe_v060/)

## ☕ Support

Love this theme? [Buy me a coffee](https://www.buymeacoffee.com/kayozxo) ❤️

---

**Quick Links**: [Getting Started](GETTING_STARTED.md) | [Extensions](.config/EXTENSIONS.md) | [README](README.md)
