# Claude 对话查看器

在浏览器本地查看 Claude.ai 导出的对话记录。所有数据仅在本地处理，不上传任何内容。

**在线使用：** https://tyxo0o315.github.io/claude-viewer/

---

## 功能

- **本地处理** — 导入 JSON 文件后数据不离开浏览器
- **虚拟滚动** — 仅渲染可视区域内的消息，大文件流畅不卡顿
- **懒加载** — 窗口列表仅解析摘要，点击时才加载完整消息
- **空窗口过滤** — 自动跳过无内容的对话
- **Thinking 折叠** — 展开 / 收起 Claude 的内部思考过程（默认折叠）
- **关键词搜索** — 高亮匹配结果，支持上一个 / 下一个导航
- **Markdown 渲染** — 代码块、表格、引用等完整渲染
- **气泡样式** — Human 消息靠右，Claude 消息靠左
- **完整时间戳** — 显示 `年-月-日 时:分`
- **窗口列表信息** — 对话名称 + 消息条数 + 最后活跃时间

---

## 使用方法

### 方式一：在线直接使用

打开 https://tyxo0o315.github.io/claude-viewer/，点击「导入 JSON 文件」即可。

### 方式二：本地离线使用

下载 [`claude-viewer.html`](./claude-viewer.html) 到本地，双击在浏览器打开。

---

## 导出 Claude 对话

1. 打开 [Claude.ai](https://claude.ai) → 头像 → **Settings**
2. 进入 **Privacy** 选项卡
3. 点击 **Export data** → 确认导出
4. 等待邮件，下载压缩包，解压得到 `conversations.json`
5. 将该文件导入查看器即可

---

## 截图预览

```
+----------------------+------------------------------------------+
| Claude 对话查看器     | ← 返回   Python 列表推导式讲解           |
|                      +------------------------------------------+
| [导入 JSON 文件]      | 搜索…          搜索   ◀   ▶   1 / 3    |
|                      |                                          |
| Python 列表推导式     |               Python 的列表推导式怎么用？|
| 4 条消息  2026-05-20 |                          ← You           |
|                      |                                          |
| Git 工作流最佳实践    | Claude →                                 |
| 4 条消息  2026-05-22 | ▶ Thinking                               |
|                      | ## 列表推导式（List Comprehension）      |
|                      | ```python                                |
|                      | squares = [x**2 for x in range(10)]     |
|                      | ```                                      |
+----------------------+------------------------------------------+
```

---

## 技术栈

- 纯 HTML + CSS + JavaScript，单文件，零安装
- [marked.js](https://marked.js.org/) — Markdown 渲染
- [DOMPurify](https://github.com/cure53/DOMPurify) — XSS 防护
- 配色参考 Claude 官方设计语言（见 [`claude-design-style.docx`](./claude-design-style.docx)）
