# CardLingo v1.0.7 · 全面格式支持版

单文件 GitHub Pages 版本。部署时只需要用本目录的 `index.html` 覆盖仓库根目录旧版 `index.html`。

## 角色卡格式

- PNG Character Card V1 / V2 / V3：读取 `chara` / `ccv3`，V3 优先；导出时保留其他 PNG 块和 Risu 扩展资源块。
- APNG Character Card：与 PNG 相同读取角色卡元数据，并保留动画相关块。
- JSON Character Card V1 / V2 / V3。
- Legacy / Off-spec JSON：兼容 `char_name`、`char_persona`、`char_greeting` 等常见旧字段别名。
- JSONL：从逐行 JSON 中识别角色卡/角色书，导出时仅替换被编辑的那一行，其他行原样保留。
- CHARX：ZIP 容器，读取 `card.json`，所有 assets、`x_meta`、未知文件及 `module.risum` 原样保留；翻译后仅改角色数据再重新封装。
- 容错 CHARX ZIP：支持 `.zip`，并兼容 `card.json` 被多包一层目录的情况。
- JPEG / JPG-CHARX：支持 RisuAI 式“JPEG 前缀 + ZIP/CHARX”混合文件，并按原格式重新导出。

## 角色书 / 世界书格式

- Character Card 内嵌 `character_book`。
- 独立 Character Book JSON / `.lorebook`。
- SillyTavern / World Info 风格 `entries` 对象。
- `entries` 数组型 Lorebook JSON。
- Risu Lorebook JSON：`{ type: "risu", data: [...] }`。
- Risu Module JSON 中的 `lorebook`（顶层或 `module.lorebook`）。

## 安全原则

- V2 / V3 / CHARX 中不认识的扩展字段尽量原样保留，不先转换成另一套结构。
- CHARX 的二进制素材不发送给翻译模型。
- `{{user}}`、`{{char}}`、XML/HTML 标签、URL、代码等继续使用 Safe Segments 保护，不使用旧版 `__CLPH_*__` 占位符方案。
- 翻译后的字段仍支持单字段回退、整页回退、撤销/重做和恢复原文。

## 暂不作为独立导入格式

- `.risum` / `.risup`：它们属于 Risu 模块/预设，而不是角色卡格式。本版会在 CHARX 中完整保留 `module.risum`，但不会把独立二进制 `.risum/.risup` 当作角色卡翻译。
- WebP：未作为 Character Card 标准导入格式处理。

## 实测

已用 `The Chronicles of The Ruined City.charx` 做 CHARX 压力测试：约 89 MB、2136 个容器文件、1067 条 assets；可读取 `card.json`，修改后重新封装，文件数量与 `module.risum` 均保留。
