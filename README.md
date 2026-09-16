# Herdr + Ghostty Dark Theme

一套经过实际使用调整的 Ghostty、herdr 与 Claude Code 深色外观配置。

特点：近黑背景、淡紫色标签和边框、中性白正文、适合中文阅读的字体回退，以及更宽的 herdr 侧栏。

## 下载

```bash
git clone https://github.com/billprestigio/herdr-ghostty-theme.git
cd herdr-ghostty-theme
```

也可以在 GitHub 页面点击 `Code` → `Download ZIP`。

## 最省事的迁移方式

把这个仓库交给任何能够操作文件和终端的 AI Agent，并发送下面这段提示词：

```text
请把这个仓库中的 Ghostty、herdr 和 Claude Code 外观配置迁移到当前设备。先识别操作系统、软件版本和实际配置路径，再分别备份原文件并合并配置片段，不要整份覆盖，也不要改动快捷键、通知、账号、权限、模型、会话或工作区。检查 JetBrains Mono 和 Sarasa Mono SC 是否存在；Windows 没有 Ghostty 桌面版时跳过 Ghostty，只安装 herdr 和 Claude Code 部分。完成后运行可用的配置检查，确认正文颜色为 #eae8ee、herdr 的 sidebar_max_width 为 60、Agent row_gap 为 0，并告诉我重新加载方法及无法验证的项目。
```

这些文件是配置片段，不能直接覆盖目标设备的完整配置，否则可能丢失原有快捷键、通知和其他个人设置。

## 文件说明

- `ghostty-appearance.conf`：Ghostty 的字体、颜色、窗口和光标外观。
- `herdr-appearance.toml`：herdr 的主题、边框与侧栏设置。
- `herdr-dark.json`：Claude Code 自定义主题，显示名为 `Herdr Dark`。
- `SHA256SUMS.txt`：配置文件完整性校验值。

## 样式参数

- 终端背景：`#11121b`
- 正文：`#eae8ee`
- 紫色强调：`#cba6f7`
- 字体：JetBrains Mono
- 中文回退字体：Sarasa Mono SC
- 字号：`16`
- herdr 侧栏最大宽度：`60`
- Agent 列表行间距：`0`

## 手动安装位置

### macOS

- Ghostty：`~/Library/Application Support/com.mitchellh.ghostty/config.ghostty`
- herdr：`~/.config/herdr/config.toml`
- Claude Code 主题：`~/.claude/themes/herdr-dark.json`
- Claude Code 设置：`~/.claude/settings.json`

### Linux

- Ghostty：`$XDG_CONFIG_HOME/ghostty/config.ghostty`；未设置 `XDG_CONFIG_HOME` 时使用 `~/.config/ghostty/config.ghostty`
- herdr：`~/.config/herdr/config.toml`
- Claude Code 主题：`~/.claude/themes/herdr-dark.json`
- Claude Code 设置：`~/.claude/settings.json`

### Windows

- Ghostty：官方桌面版目前尚未支持 Windows，跳过 `ghostty-appearance.conf`
- herdr：`%APPDATA%\herdr\config.toml`
- Claude Code 主题：`%USERPROFILE%\.claude\themes\herdr-dark.json`
- Claude Code 设置：`%USERPROFILE%\.claude\settings.json`

把 `herdr-appearance.toml` 合并进 herdr 配置，把 `herdr-dark.json` 复制到 Claude Code 主题位置。然后只把 Claude Code 设置中的 `theme` 字段设为：

```json
"theme": "custom:herdr-dark"
```

## 重新加载

- macOS Ghostty：按 `Cmd + Shift + ,`
- Linux Ghostty：按 `Ctrl + Shift + ,`
- herdr：先按 `Ctrl + B`，松开后按 `Shift + R`
- Claude Code：输入 `/theme`，选择 `Herdr Dark`

配置不包含账号、密钥、会话历史、工作区数据或状态栏脚本。安装前仍应备份目标设备的现有配置。

## 官方文档

- [Ghostty 配置路径](https://ghostty.org/docs/config)
- [Ghostty 平台支持](https://ghostty.org/docs/features)
- [herdr 配置路径](https://herdr.dev/docs/configuration/)
- [Claude Code 自定义主题](https://code.claude.com/docs/en/terminal-config)
