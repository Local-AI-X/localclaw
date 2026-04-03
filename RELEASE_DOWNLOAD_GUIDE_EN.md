# LocalClaw Download Guide

## 📥 Quick Selection

| Operating System | Chip Architecture | Recommended Download |
|-----------------|-------------------|---------------------|
| **macOS** | Apple Silicon (M1/M2/M3) | `LocalClaw-X.X.X-mac-arm64.dmg` |
| **macOS** | Intel | `LocalClaw-X.X.X-mac-x64.dmg` |
| **Windows** | 64-bit (Intel/AMD) | `LocalClaw-X.X.X-win-x64.exe` |
| **Windows** | ARM64 | `LocalClaw-X.X.X-win-arm64.exe` |

---

## 🍎 macOS

### How to Check Your Mac Chip Type
1. Click the ** Apple menu** in the top-left corner → **About This Mac**
2. Look for "Chip" or "Processor" information:
   - Shows **Apple M1/M2/M3** → Download the **arm64** version
   - Shows **Intel** → Download the **x64** version

### Package Descriptions

| Filename | Use Case |
|----------|----------|
| `LocalClaw-X.X.X-mac-arm64.dmg` | Apple Silicon Mac (M1/M2/M3 chips) |
| `LocalClaw-X.X.X-mac-x64.dmg` | Intel Mac |
| `LocalClaw-X.X.X-mac-arm64.zip` | For automatic updates (no need to download manually) |
| `LocalClaw-X.X.X-mac-x64.zip` | For automatic updates (no need to download manually) |

### Installation Steps
1. Download the appropriate `.dmg` file for your system
2. Double-click to open the DMG file
3. Drag the LocalClaw icon to the Applications folder
4. Launch LocalClaw from Launchpad or the Applications folder

> **Note**: If you see a "cannot be opened" warning on first launch, go to **System Settings → Privacy & Security** to allow it.

---

## 🪟 Windows

### How to Check Your Windows System Architecture
1. Press `Win + R`, type `msinfo32`, and press Enter
2. Look for "System Type":
   - Shows **x64-based PC** → Download the **x64** version
   - Shows **ARM-based PC** → Download the **arm64** version

### Package Descriptions

| Filename | Use Case |
|----------|----------|
| `LocalClaw-X.X.X-win-x64.exe` | 64-bit Windows (Intel/AMD processors) |
| `LocalClaw-X.X.X-win-arm64.exe` | ARM64 Windows (e.g., Surface Pro X, etc.) |

### Installation Steps
1. Download the appropriate `.exe` installer for your system
2. Double-click to run the installer
3. Follow the wizard prompts to complete installation
4. Launch from the desktop shortcut or Start menu after installation

---

## ⚠️ FAQ

### Which version should I download?
- **Unsure about your chip type?** Choose arm64 for modern Macs, x64 for Windows PCs
- **What if I download the wrong version?** The installer will show an incompatibility message; simply download the correct version

### Version Number Explanation
- `X.X.X` represents the version number, e.g., `0.3.1`
- Always download the latest version for the best experience

### Verifying File Integrity
Each release includes SHA256 checksum files to verify download integrity:
```bash
# macOS
shasum -a 256 -c LocalClaw-X.X.X-*.sha256

# Windows (PowerShell)
Get-FileHash LocalClaw-X.X.X-*.exe -Algorithm SHA256
```

---

## 🆘 Need Help?

- 📖 [Full Documentation](https://github.com/localClaw/LocalClaw#readme)
- 🐛 [Submit an Issue](https://github.com/localClaw/LocalClaw/issues)
- 💬 [Join Discussions](https://github.com/localClaw/LocalClaw/discussions)

