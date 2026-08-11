# CardLingo · 角色卡安全翻译器

这是一个纯前端角色卡翻译工具。角色卡解析、编辑、变量保护与重新封装都在浏览器本地完成；只有待翻译文本会发送给你配置的模型 API。

## 已实现

- PNG Character Card V1/V2/V3：读取 `ccv3`（优先）和 `chara` tEXt 元数据，并重新写回 PNG。
- JSON 角色卡导入/导出。
- CHARX V3：读取根目录 `card.json`，保留 ZIP 内全部原始资源，翻译后重新封装。
- DeepSeek V4 Flash / V4 Pro 快速预设，也支持任意 OpenAI 兼容 API。
- Chat Completions 与 Responses API 两种协议。
- 安全翻译范围：核心设定、开场/示例、系统提示词、作者说明、世界书正文、姓名、标签、世界书关键词可分别开启。
- 默认不翻译世界书关键词、姓名和标签，降低触发逻辑被破坏的风险。
- 自动保护 `{{user}}`、`{{char}}`、HTML/XML 标签、Markdown 代码块/行内代码、URL、`${...}`、`<%...%>`。
- 支持自定义不可翻译词和正则。
- 批处理、并发请求、失败重试、占位符完整性检查、进度与取消。
- 字段逐项检查、手工编辑、JSON 编辑、翻译字段高亮。
- 移动端响应式界面、深色/浅色模式。

## 运行

直接打开 `index.html` 即可。CHARX 功能使用 JSZip CDN，因此需要联网；PNG/JSON 其余本地功能不依赖服务器。

若浏览器以 `file://` 打开时模型服务阻止跨域请求，请用静态服务器或 GitHub Pages 部署。例如：

```bash
python3 -m http.server 8080
```

然后打开 `http://localhost:8080`。

## DeepSeek 推荐配置

- Base URL：`https://api.deepseek.com`
- Model：`deepseek-v4-flash`
- Protocol：Chat Completions
- Temperature：0.2

## 隐私提示

API Key 默认只驻留当前页面内存。只有勾选“在此浏览器保存 API Key”时，才会写入 `localStorage`。不要在公用设备保存密钥。
