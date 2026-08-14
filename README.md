# CardLingo v1.0.8 · iOS CHARX 导入修复版

本版修复 iPhone / iPad Safari 的“文件”选择器会把 `.charx` 灰掉、无法点选的问题。

## 修复内容

- 通用“导入文件”入口不再使用 HTML `accept` 扩展名过滤。
- iOS 文件选择器现在可以选择 `.charx`、`.charx.zip`、`.risum` 等任意文件；CardLingo 会在选择后自行判断是否属于支持格式。
- 保留 v1.0.7 的 PNG/APNG、JSON/JSONL、CHARX、ZIP-CHARX、JPEG-CHARX、Lorebook 与安全分段翻译逻辑。
- 不支持的文件会在网站内提示“无法识别”，不会误解析。

## GitHub Pages 更新

只需用本包中的 `index.html` 覆盖仓库根目录原来的 `index.html`，然后 Commit changes。
