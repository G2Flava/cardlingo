# CardLingo · Tavern 全功能回退版

静态 GitHub Pages 版本。无需自建后端，浏览器直接请求你配置的 OpenAI 兼容 API。

## 已实现
- PNG / JSON / CHARX 导入
- Character Card V1 / V2 / V3 读取
- PNG 角色卡重新封装导出、JSON 导出、CHARX 原格式下载
- 角色 / 角色书双页面
- 单字段翻译
- 角色一键批量翻译
- 角色书一键批量翻译
- 单条角色书翻译
- 角色书创建、新增/删除/编辑条目
- 备选开场新增/删除/编辑
- API 设置、Chat Completions / Responses API
- 术语表：新增、删除、导入、导出、清空、分类、备注
- AI 助手：读取当前角色卡上下文，支持应用结构化字段补丁
- 深色 / 浅色主题
- 中文 / English / 日本語界面切换（核心导航）
- 一键下载中文版
- 变量 / 模板 / URL / 代码保护
- 自定义保护词 / 正则
- 翻译历史
- 全局撤销 / 重做
- 每个已翻译字段“回退”按钮
- 每个字段“原文”按钮
- 当前页面翻译批量回退
- 整张角色卡恢复原卡

## GitHub Pages 部署
将 `index.html`、`styles.css`、`app.js` 三个文件放在仓库根目录，然后使用 Pages 从 `main / (root)` 发布。

## API URL
基础 URL 填服务根地址，例如 `https://api.deepseek.com`。Chat Completions 会自动请求 `/v1/chat/completions`；Responses API 会请求 `/responses`。
