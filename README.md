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

在新设备安装好 Ghostty、herdr 和 Claude Code 后，把这个仓库交给 Codex，并粘贴 [CODEX_PROMPT.zh-CN.md](CODEX_PROMPT.zh-CN.md) 的内容。Codex 会先备份，再把外观片段合并到本机现有配置中。

这些文件是配置片段，不能直接覆盖目标设备的完整配置，否则可能丢失原有快捷键、通知和其他个人设置。

## 文件说明

- `ghostty-appearance.conf`：Ghostty 的字体、颜色、窗口和光标外观。
- `herdr-appearance.toml`：herdr 的主题、边框与侧栏设置。
- `herdr-dark.json`：Claude Code 自定义主题，显示名为 `Herdr Dark`。
- `CODEX_PROMPT.zh-CN.md`：给新设备 Codex 的完整迁移提示词。
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

Ghostty 的片段应合并到本机 Ghostty 配置：

- macOS：`~/Library/Application Support/com.mitchellh.ghostty/config.ghostty`
- Linux：`~/.config/ghostty/config`

herdr 的片段应合并到：

```text
~/.config/herdr/config.toml
```

Claude Code 主题文件放到：

```text
~/.claude/themes/herdr-dark.json
```

然后只把 `~/.claude/settings.json` 中的 `theme` 字段设为：

```json
"theme": "custom:herdr-dark"
```

## 重新加载

- macOS Ghostty：按 `Cmd + Shift + ,`
- herdr：先按 `Ctrl + B`，松开后按 `Shift + R`
- Claude Code：输入 `/theme`，选择 `Herdr Dark`

配置不包含账号、密钥、会话历史、工作区数据或状态栏脚本。安装前仍应备份目标设备的现有配置。
