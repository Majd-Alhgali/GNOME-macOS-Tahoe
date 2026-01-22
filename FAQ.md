# Frequently Asked Questions (FAQ)

## General Questions

### Q: Will this theme work on GNOME 49?

**A:** Yes! The Tahoe theme is fully compatible with GNOME 43 and later, including GNOME 49. The theme is designed to adapt to new GNOME features automatically through CSS inheritance.

### Q: How do I make GNOME 49 look like macOS Tahoe 2026?

**A:** Follow these steps:

1. Clone the repository: `git clone https://github.com/kayozxo/GNOME-macOS-Tahoe`
2. Run the installer: `cd GNOME-macOS-Tahoe && ./install.sh`
3. Install essential extensions (Open Bar, Dash to Dock, User Themes, Blur My Shell)
4. Apply the theme in GNOME Tweaks
5. Configure extensions using the provided configs

See the [Complete Getting Started Guide](GETTING_STARTED.md) for detailed instructions.

### Q: What's the difference between Tahoe-Dark and Tahoe-Light?

**A:** 
- **Tahoe-Dark**: Dark theme optimized for low-light environments, resembling macOS Dark Mode
- **Tahoe-Light**: Light theme for bright environments, resembling macOS Light Mode

You can install both and switch between them in GNOME Tweaks.

### Q: Can I use custom accent colors?

**A:** Yes! The theme supports 16 beautiful accent colors:
- blue, green, purple, pink, orange, red, teal, indigo
- rose, emerald, violet, amber, cyan, lime, sky, slate

Generate and install them with:
```bash
./install.sh -d --color blue -la
```

## Installation Questions

### Q: The installer asks about "gum" - what is it?

**A:** [Gum](https://github.com/charmbracelet/gum) is an interactive terminal UI tool that makes the installer more user-friendly with menus and prompts. The installer can automatically install it, or you can skip it and use the non-interactive fallback mode.

### Q: Do I need to install both light and dark themes?

**A:** No, you can install just one:
- Dark only: `./install.sh -d`
- Light only: `./install.sh -l`
- Both: `./install.sh -l -d`

### Q: What does the `-la` flag do?

**A:** The `-la` flag installs the libadwaita override, which:
1. Applies the theme to modern GTK4 applications (GNOME Settings, Files, Console, etc.)
2. Applies accent colors to GNOME Shell elements (panel, dash, notifications, popups)

Example: `./install.sh -d -la`

**Note**: Libadwaita doesn't officially support custom themes, so this override means GTK4 apps will use one fixed theme until you reinstall with a different override.

### Q: How do I update the theme?

**A:**
```bash
cd GNOME-macOS-Tahoe
git pull origin main
./install.sh
```

This will fetch the latest changes and reinstall the theme.

### Q: How do I uninstall the theme?

**A:**
```bash
cd GNOME-macOS-Tahoe
./install.sh -u
```

The uninstaller will remove themes from `~/.themes/` and offer to remove libadwaita overrides.

## Theme Issues

### Q: The theme doesn't appear in GNOME Tweaks

**A:** Try these solutions:

1. **Check installation directory**: Themes should be in `~/.themes/`
   ```bash
   ls ~/.themes/
   ```

2. **Fix permissions**:
   ```bash
   chmod -R 755 ~/.themes/Tahoe-*
   ```

3. **Restart GNOME Shell** (X11 only):
   - Press `Alt+F2`
   - Type `r`
   - Press Enter

4. **Log out and back in** (Wayland)

### Q: GTK4 apps (Settings, Files, etc.) aren't using my theme

**A:** Modern GTK4 apps use libadwaita, which doesn't officially support custom themes. Install the libadwaita override:

```bash
./install.sh -d -la  # Dark theme
# or
./install.sh -l -la  # Light theme
```

**Important**: Once installed, GTK4 apps will use this one theme until you reinstall with a different override. They won't switch with your GTK3 theme.

### Q: The GNOME Shell (top panel, overview) isn't themed

**A:** GNOME Shell theming requires additional steps:

1. **Install User Themes extension**:
   - From [extensions.gnome.org](https://extensions.gnome.org/extension/19/user-themes/)
   - Or via Extension Manager

2. **Enable the extension**:
   - Open GNOME Extensions app
   - Toggle "User Themes" to ON

3. **Reinstall with libadwaita** (recommended):
   ```bash
   ./install.sh -d -la
   ```

4. **Select Shell theme in Tweaks**:
   - Open GNOME Tweaks → Appearance
   - Set "Shell" to `Tahoe-Dark` or `Tahoe-Light`

### Q: Flatpak apps don't use my theme

**A:** Flatpak apps run in a sandbox and need explicit permission to access theme files:

```bash
# Grant permissions
sudo flatpak override --filesystem=xdg-config/gtk-3.0
sudo flatpak override --filesystem=xdg-config/gtk-4.0

# Install theme for Flatpak
./install.sh --flatpak
```

### Q: My accent colors aren't showing up

**A:** Make sure you:

1. **Generated the color variant**:
   ```bash
   ./install.sh --color blue
   ```

2. **Installed with libadwaita flag** (for GNOME Shell elements):
   ```bash
   ./install.sh -d --color blue -la
   ```

3. **Selected the colored theme** in GNOME Tweaks:
   - Go to Appearance
   - Select `Tahoe-Dark-Blue` (not just `Tahoe-Dark`)

## Extension Questions

### Q: Which extensions are absolutely required?

**A:** For the complete macOS Tahoe look, these are essential:

- **Open Bar** - macOS-style top bar (⭐⭐⭐ Required)
- **Dash to Dock** - macOS-style dock (⭐⭐⭐ Required)
- **User Themes** - Enable custom shell themes (⭐⭐⭐ Required)
- **Blur My Shell** - Blur effects (⭐⭐ Highly Recommended)

See the [Extension Configuration Guide](.config/EXTENSIONS.md) for setup instructions.

### Q: Where are the extension configuration files?

**A:** Configuration files are in the `.config/extensions/` directory:

- Open Bar: `.config/extensions/openBar/Tahoe-Dark` (or Tahoe-Light)
- Tiling Shell: `.config/extensions/tiling-shell/tilingshell-settings.txt`
- Blur My Shell: Follow setup guide in `.config/EXTENSIONS.md`

### Q: An extension says it's incompatible with GNOME 49

**A:** Extension compatibility varies:

1. **Wait for updates**: Extension developers usually update for new GNOME versions within a few weeks
2. **Check Extension Manager**: Look for updated versions
3. **Force enable** (may be unstable):
   ```bash
   gnome-extensions enable extension-name@domain
   ```
4. **Find alternatives**: Search for similar extensions that support GNOME 49

### Q: How do I import extension configurations?

**A:** 

**For Open Bar:**
1. Open Extension Manager → Open Bar → Settings
2. Go to "Admin" tab
3. Click "Import"
4. Select `.config/extensions/openBar/Tahoe-Dark` (or Tahoe-Light)

**For Tiling Shell:**
1. Open Tiling Shell settings
2. Scroll to the bottom
3. Click "Import"
4. Select `.config/extensions/tiling-shell/tilingshell-settings.txt`

## Customization Questions

### Q: Can I use a different accent color for light and dark themes?

**A:** Yes! Install color variants for both themes:

```bash
./install.sh -d --color blue -la
./install.sh -l --color green -la
```

Then select:
- `Tahoe-Dark-Blue` for dark mode
- `Tahoe-Light-Green` for light mode

### Q: Can I change just the panel or just the dock?

**A:** Yes, the theme and extensions work independently:

- **Theme**: Controls window decorations, app colors, GTK elements
- **Open Bar**: Controls top panel appearance
- **Dash to Dock**: Controls dock appearance
- **Blur My Shell**: Controls blur effects

Configure each separately to mix and match.

### Q: How do I use the macOS Tahoe wallpapers?

**A:**

1. **Install wallpapers**:
   ```bash
   ./install.sh -w
   ```

2. **Or use installer extras**: Select "Install Extras" in the interactive menu

3. **Or manually**: Wallpapers are in `.config/walls/` directory

4. **Set as background**:
   - Right-click wallpaper → Set as Background
   - Or: Settings → Appearance → Background

### Q: Can I customize the colors myself?

**A:** Yes! The theme uses standard CSS. You can edit:

- GTK3: `~/.themes/Tahoe-Dark/gtk-3.0/gtk.css`
- GTK4: `~/.themes/Tahoe-Dark/gtk-4.0/gtk.css`
- Shell: `~/.themes/Tahoe-Dark/gnome-shell/gnome-shell.css`

Or use the Python script to generate custom accent colors:
```bash
python3 generate_accent_variants.py --color "#your-hex-color" --name "custom"
```

## Performance Questions

### Q: Does this theme impact performance?

**A:** The theme itself has minimal performance impact. However:

- **Blur My Shell**: Blur effects can impact performance on older hardware. Adjust blur intensity in settings.
- **Extensions**: Too many extensions can slow down GNOME Shell. Install only what you need.

### Q: Why does GNOME Shell feel slower after installing extensions?

**A:** Each extension adds overhead. Tips to improve performance:

1. Only enable essential extensions
2. Disable extensions you don't actively use
3. Reduce blur intensity in Blur My Shell
4. Use lighter extension alternatives
5. Check `journalctl -f` for error messages from misbehaving extensions

## Troubleshooting

### Q: After updating GNOME, my theme broke

**A:** GNOME updates can sometimes cause issues. Try:

```bash
cd GNOME-macOS-Tahoe
git pull origin main
./install.sh -d -la  # or your preferred options
```

Then restart GNOME Shell or log out/in.

### Q: Some UI elements are the wrong color

**A:** This can happen if:

1. **Multiple themes installed**: Remove old/conflicting themes from `~/.themes/`
2. **Cache issues**: Clear GTK cache:
   ```bash
   rm -rf ~/.cache/gtk-*
   ```
3. **Need libadwaita reinstall**:
   ```bash
   ./install.sh -d -la
   ```

### Q: Text is hard to read on some elements

**A:** Try:

1. **Switch theme variant**: If using dark, try light, or vice versa
2. **Try different accent color**: Some colors have better contrast
3. **Adjust font size**: GNOME Tweaks → Fonts → Scaling Factor

### Q: The installer failed with an error

**A:** Common solutions:

1. **Check permissions**: Make sure you can write to `~/.themes/` and `~/.config/`
2. **Missing dependencies**: Install Python 3 and Git
3. **Check error message**: Read the error output for specific issues
4. **Report bug**: [Open an issue](https://github.com/kayozxo/GNOME-macOS-Tahoe/issues) with the error message

## Advanced Questions

### Q: Can I use this theme on X11 and Wayland?

**A:** Yes, the theme works on both:

- **X11**: Full support, including GNOME Shell restart (`Alt+F2`, `r`)
- **Wayland**: Full support, but requires log out/in to restart Shell

### Q: How do I contribute to this project?

**A:** Contributions are welcome!

1. Fork the repository
2. Make your changes
3. Test thoroughly on different GNOME versions
4. Submit a pull request
5. Report bugs via [GitHub Issues](https://github.com/kayozxo/GNOME-macOS-Tahoe/issues)

### Q: Can I use this theme on non-GNOME desktops?

**A:** Limited support:

- **MATE/Cinnamon**: GTK themes may work but not shell themes
- **XFCE**: GTK themes should work
- **KDE/Plasma**: Not compatible
- **Other**: GTK3/4 themes may work; shell themes won't

### Q: Where are theme files installed?

**A:**

- **Themes**: `~/.themes/Tahoe-*`
- **GTK4 config**: `~/.config/gtk-4.0/` (libadwaita override)
- **Icons**: `~/.local/share/icons/` (if installed)
- **Wallpapers**: `~/Pictures/Wallpapers/` (if installed)

## Support

### Q: Where can I get help?

**A:**

- 📖 [Getting Started Guide](GETTING_STARTED.md)
- 🚀 [Quick Reference](QUICK_REFERENCE.md)
- 🐛 [GitHub Issues](https://github.com/kayozxo/GNOME-macOS-Tahoe/issues)
- 💬 [Reddit r/unixporn](https://www.reddit.com/r/unixporn/comments/1ogcgqg/gnome_macos_tahoe_v060/)

### Q: How can I support this project?

**A:**

- ⭐ Star the repository on GitHub
- 🐛 Report bugs and issues
- 💡 Suggest improvements
- 📢 Share with others
- ☕ [Buy the developer a coffee](https://www.buymeacoffee.com/kayozxo)

---

**Can't find your question?** [Open an issue](https://github.com/kayozxo/GNOME-macOS-Tahoe/issues) or check the [Getting Started Guide](GETTING_STARTED.md).
