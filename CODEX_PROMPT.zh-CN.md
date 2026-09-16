请将这个仓库或下载包中的 Herdr Dark Neutral White 外观配置迁移到这台设备。目标是近黑背景、淡紫色标签和边框、中性白色正文，以及有空行的侧栏。

先读取包里的 README.md 和三个配置片段，检查本机操作系统、Ghostty、herdr、Claude Code 的版本及实际生效的配置位置。先备份所有需要修改的文件，备份名带时间戳，不能覆盖旧备份。

1. 将 ghostty-appearance.conf 中的外观设置合并到 Ghostty 现有配置。处理已有 theme、config-file 和重复颜色项的优先级，确保这些颜色实际生效。重复的 font-family 是有序字体回退，palette 是 16 个独立条目，不要压成单项。非 macOS 不写 macos-titlebar-style，并按本机版本检查其他字段。
2. 将 herdr-appearance.toml 合并到 herdr 配置，只更新片段中列出的字段；TOML 同名表不要重复声明。保留所有未列出的设置、会话和工作区。
3. 将 herdr-dark.json 放到 ~/.claude/themes/herdr-dark.json，并只将 ~/.claude/settings.json 的 theme 字段改为 custom:herdr-dark。若同名主题已有不同内容，先备份。保留其余全部设置。
4. 检查 JetBrains Mono 和 Sarasa Mono SC 是否存在；缺字体时明确告知，不要静默换字体后声称完全一致。若软件未安装或版本不支持某项，说明具体缺口，不要擅自升级或改动其他产品。
5. 运行 Ghostty 和 herdr 自带的配置检查，验证 JSON，核对实际修改仅限这些外观项，并确认中性白正文是 #eae8ee。不要重启或终止正在运行的会话，不要修改分屏布局、快捷键、账号、权限、模型、通知和状态栏脚本。
6. 完成后用简洁中文列出改动、检查结果及本机适用的重新加载步骤；对无法实看验证的效果如实说明。

这是已确定的样式迁移，普通兼容性选择自行处理；无需重新设计主题或反复让我确认。
