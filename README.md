# CardLingo 单文件稳定修复版 v1.0.3

针对你截图中的两个问题修复：页面被 Safari 按桌面布局缩放、按钮全部无响应。

- CSS / JavaScript / JSZip 全部内嵌到 `index.html`，避免 GitHub Pages + Safari 缓存到不同版本。
- 触屏 iPhone 强制移动布局，即使站点曾开启“请求桌面网站”。
- localStorage 被 Safari 隐私设置阻止时也不会中断按钮绑定。
- 设置/术语/历史弹窗增加兼容回退。
- 启动失败时页面顶部会直接显示错误，不再静默失效。

## GitHub 更新
只需要覆盖仓库根目录里的 `index.html`。旧 `styles.css` 和 `app.js` 可以留着，它们不会再被引用。
