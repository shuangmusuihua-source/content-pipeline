---
name: wechat
description: |
  将 Markdown 或纯文本转换为微信公众号排版格式。
  暖色调、米色背景、印刷级排版。
allowed-tools:
  - Read
  - Write
  - Bash
---

# WeChat Formatter: 微信公众号排版

将内容转换为微信公众号专业排版格式。

## 设计风格

**基于 Kami 印刷设计系统** - 暖色调、优雅舒适、印刷级排版。

### 颜色系统

| 元素 | 颜色 | 色值 |
|------|------|------|
| 页面背景 | 极浅米色 | `#fdfcf9` |
| 卡片背景 | 浅暖灰 | `#f9f8f5` |
| 强调色/标题 | 深蓝紫 | `#1e2a78` |
| 正文 | 深暖灰 | `#3d3d3a` |
| 次要文字 | 橄榄灰 | `#5e5d59` |
| 链接 | 深蓝 | `#2d5a8a` |
| 警示/代码 | 暖红 | `#b53333` |
| 分割线/边框 | 暖银 | `#b0aea5` |

### 字体规范

| 元素 | 字号 | 行高 | 字间距 |
|------|------|------|--------|
| H1 标题 | 20px | 1.30 | 0.5px |
| H2 章节 | 17px | 1.35 | 0.5px |
| H3 小节 | 15px | 1.40 | 0 |
| 正文 | 15px | 1.75 | 0.5px |
| 引用 | 14px | 1.60 | 0.5px |

---

## 关键技术

**重要：** 微信编辑器会过滤 `background-color`，但保留表格的背景色。

### 页面结构

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
</head>
<body style="margin: 0; padding: 0;">

<table style="width: 100%; border-collapse: collapse; border: none; background-color: #fdfcf9;">
<tr>
<td style="padding: 24px 16px; border: none; font-family: 'Source Han Sans SC', 'Noto Sans SC', -apple-system, BlinkMacSystemFont, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft Yahei', sans-serif;">

  <!-- 内容 -->

</td>
</tr>
</table>

</body>
</html>
```

### 标题样式

```html
<!-- H1 主标题 -->
<h1 style="font-size: 20px; font-weight: 500; color: #1e2a78; line-height: 1.30; text-align: center; letter-spacing: 0.5px; margin: 0 0 24px 0;">
  标题文本
</h1>

<!-- H2 章节标题 -->
<h2 style="font-size: 17px; font-weight: 500; color: #1e2a78; line-height: 1.35; text-align: left; letter-spacing: 0.5px; margin: 24px 0 16px 0; padding-bottom: 8px; border-bottom: 1px solid #b0aea5;">
  章节标题
</h2>
```

### 正文样式

```html
<p style="font-size: 15px; color: #3d3d3a; line-height: 1.75; text-align: justify; letter-spacing: 0.5px; margin: 0 0 16px 0;">
  正文内容
</p>
```

### 卡片样式

```html
<!-- 普通卡片 -->
<table style="width: 100%; border-collapse: collapse; border: none; background-color: #f9f8f5; margin: 0 0 16px 0;">
<tr>
<td style="padding: 16px; border-left: 3px solid #1e2a78; border-top: none; border-right: none; border-bottom: none;">
  <p style="font-size: 15px; color: #3d3d3a; line-height: 1.75; text-align: justify; letter-spacing: 0.5px; margin: 0;">
    卡片内容
  </p>
</td>
</tr>
</table>

<!-- 警示卡片 -->
<table style="width: 100%; border-collapse: collapse; border: none; background-color: #f9f8f5; margin: 0 0 16px 0;">
<tr>
<td style="padding: 16px; border-left: 3px solid #b53333; border-top: none; border-right: none; border-bottom: none;">
  <p style="font-size: 15px; color: #3d3d3a; line-height: 1.75; text-align: justify; letter-spacing: 0.5px; margin: 0;">
    <span style="font-weight: 500; color: #b53333;">重要提示：</span>警示内容
  </p>
</td>
</tr>
</table>
```

### 强调样式

```html
<!-- 强调文本 -->
<span style="color: #1e2a78; font-weight: 500;">强调内容</span>

<!-- 链接 -->
<a style="color: #2d5a8a; text-decoration: none;">链接文本</a>
```

---

## 微信兼容要点

1. **用 `table` 实现背景色** - 微信保留表格背景色
2. **设置 `border: none`** - 移除默认边框
3. **所有样式内联** - 不使用外部 CSS 或 class 选择器
4. **font-weight 最大 500** - 避免合成粗体
5. **避免** - 非 table 元素的 `background-color`、`class` 选择器

---

## 输出

生成 HTML 文件后，使用 `open` 命令打开：

```bash
open /path/to/output-wechat.html
```

文件命名：`{article-name}-wechat.html`
