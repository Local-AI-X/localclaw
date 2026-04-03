# LocalClaw 下载指南

## 📥 快速选择

| 操作系统 | 芯片架构 | 推荐下载 |
|---------|---------|---------|
| **macOS** | Apple Silicon (M1/M2/M3) | `LocalClaw-X.X.X-mac-arm64.dmg` |
| **macOS** | Intel | `LocalClaw-X.X.X-mac-x64.dmg` |
| **Windows** | 64位 (Intel/AMD) | `LocalClaw-X.X.X-win-x64.exe` |
| **Windows** | ARM64 | `LocalClaw-X.X.X-win-arm64.exe` |

---

## 🍎 macOS

### 如何查看你的 Mac 芯片类型
1. 点击屏幕左上角 ** 苹果菜单** → **关于本机**
2. 查看"芯片"或"处理器"信息：
   - 显示 **Apple M1/M2/M3** → 下载 **arm64** 版本
   - 显示 **Intel** → 下载 **x64** 版本

### 安装包说明

| 文件名 | 适用场景 |
|-------|---------|
| `LocalClaw-X.X.X-mac-arm64.dmg` | Apple Silicon Mac (M1/M2/M3 芯片) |
| `LocalClaw-X.X.X-mac-x64.dmg` | Intel Mac |
| `LocalClaw-X.X.X-mac-arm64.zip` | 自动更新使用（无需手动下载） |
| `LocalClaw-X.X.X-mac-x64.zip` | 自动更新使用（无需手动下载） |

### 安装步骤
1. 下载对应版本的 `.dmg` 文件
2. 双击打开 DMG 文件
3. 将 LocalClaw 图标拖拽到 Applications 文件夹
4. 从启动台或应用程序文件夹打开 LocalClaw

> **注意**: 首次打开时如遇"无法打开"提示，请前往 **系统设置 → 隐私与安全性** 中允许打开。

---

## 🪟 Windows

### 如何查看你的 Windows 系统架构
1. 按 `Win + R`，输入 `msinfo32` 回车
2. 查看"系统类型"：
   - 显示 **x64-based PC** → 下载 **x64** 版本
   - 显示 **ARM-based PC** → 下载 **arm64** 版本

### 安装包说明

| 文件名 | 适用场景 |
|-------|---------|
| `LocalClaw-X.X.X-win-x64.exe` | 64位 Windows (Intel/AMD 处理器) |
| `LocalClaw-X.X.X-win-arm64.exe` | ARM64 Windows (如 Surface Pro X 等) |

### 安装步骤
1. 下载对应版本的 `.exe` 安装程序
2. 双击运行安装程序
3. 按向导提示完成安装
4. 安装完成后可从桌面快捷方式或开始菜单启动

---

## ⚠️ 常见问题

### 下载哪个版本？
- **不确定芯片类型？** 现代 Mac 选 arm64，Windows PC 通常选 x64
- **下载错了怎么办？** 安装程序会提示不兼容，重新下载正确版本即可

### 版本号说明
- `X.X.X` 代表版本号，例如 `0.3.1`
- 始终下载最新版本的安装包以获得最佳体验

### 校验文件完整性
每个发布版本都提供 SHA256 校验文件，可验证下载完整性：
```bash
# macOS
shasum -a 256 -c LocalClaw-X.X.X-*.sha256

# Windows (PowerShell)
Get-FileHash LocalClaw-X.X.X-*.exe -Algorithm SHA256
```

---

## 🆘 需要帮助？

- 📖 [完整文档](https://github.com/localClaw/LocalClaw#readme)
- 🐛 [提交 Issue](https://github.com/localClaw/LocalClaw/issues)
- 💬 [加入讨论](https://github.com/localClaw/LocalClaw/discussions)

