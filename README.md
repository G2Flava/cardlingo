# CardLingo v1.1.1 · 完整角色书条目编辑器

在 v1.1.0 智能项目版基础上扩展完整角色书编辑能力。

## 角色书级设置
- 名称、描述
- Scan Depth
- Token Budget
- Recursive Scanning
- Extensions JSON

## 每条角色书可编辑字段
- 名称 / Name
- 注释 / Comment
- 主关键词 / Keys
- 次关键词 / Secondary Keys
- 正文 / Content
- 插入顺序 / Insertion Order
- 深度 / Depth（Risu/ST 兼容）
- 优先级 / Priority
- 激活概率 / Activation Percent（Risu 兼容）
- 插入位置 / Position
- 条目模式 / Mode：normal / folder / child
- 所属文件夹 / Folder
- ID
- Enabled
- Constant / Always Active
- Selective
- Use Regex
- Case Sensitive
- Extensions JSON

## 条目操作
- 新增普通条目
- 新增 Risu 文件夹
- 复制
- 上移 / 下移
- 单条翻译
- 单条回退
- 恢复原文
- 删除

## 结构保护
`folder:UUID`、Risu `\uf000folder:UUID`、`@@stored_key`、`@@dont_activate`、`__...` 等结构键不会被当普通自然语言翻译。空正文的文件夹/模板条目仍会显示。

## 格式
继续保留 PNG/APNG、JSON/JSONL、Character Card V1/V2/V3、CHARX、JPEG-CHARX、ZIP-CHARX、独立 Lorebook 等功能，并新增标准 `lorebook_v3` 包装格式识别。

GitHub Pages 仍只需覆盖根目录 `index.html`。
