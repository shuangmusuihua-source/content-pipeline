---
name: toutiao
description: |
  将 Markdown 或纯文本转换为今日头条排版格式。
  白底黑字、红色强调、现代简洁。
allowed-tools:
  - Read
  - Write
  - Bash
---

# Toutiao Formatter: 今日头条排版

将内容转换为今日头条专业排版格式。

## 设计风格

**现代简洁** - 白底黑字、红色强调、信息密度高。

### 颜色系统

| 元素 | 颜色 | 色值 |
|------|------|------|
| 页面背景 | 纯白 | `#ffffff` |
| 卡片背景 | 浅灰 | `#f7f7f7` |
| 警示卡片背景 | 浅红 | `#fff5f5` |
| 标题 | 纯黑 | `#222222` |
| 正文 | 深灰 | `#333333` |
| 次要文字 | 中灰 | `#444444` |
| 强调色 | 头条红 | `#d4393a` |
| 警示色 | 深红 | `#c53030` |
| 信息色 | 蓝色 | `#2b6cb0` |
| 分割线 | 浅灰 | `#e5e5e5` |

### 字体规范

| 元素 | 字号 | 行高 | 字重 |
|------|------|------|------|
| H1 标题 | 24px | 1.35 | 600 |
| H2 章节 | 20px | 1.40 | 600 |
| H3 小节 | 18px | 1.45 | 500 |
| 正文 | 17px | 1.80 | 400 |
| 引用 | 16px | 1.75 | 400 |

---

## 页面结构

今日头条编辑器对样式支持较好，可直接使用 `div` 和 `background-color`。

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
</head>
<body style="margin: 0; padding: 0; background-color: #ffffff;">

<div style="padding: 24px 20px; font-family: -apple-system, BlinkMacSystemFont, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft Yahei', sans-serif; max-width: 680px; margin: 0 auto;">

  <!-- 内容 -->

</div>

</body>
</html>
```

### 标题样式

```html
<!-- H1 主标题 -->
<h1 style="font-size: 24px; font-weight: 600; color: #222222; line-height: 1.35; margin: 0 0 20px 0;">
  标题文本
</h1>

<!-- H2 章节标题 -->
<h2 style="font-size: 20px; font-weight: 600; color: #222222; line-height: 1.40; margin: 32px 0 16px 0; padding-left: 12px; border-left: 4px solid #d4393a;">
  章节标题
</h2>
```

### 正文样式

```html
<p style="font-size: 17px; color: #333333; line-height: 1.80; text-align: justify; margin: 0 0 18px 0;">
  正文内容
</p>
```

### 强调样式

```html
<!-- 强调文本 -->
<span style="color: #d4393a; font-weight: 500;">强调内容</span>

<!-- 加粗标题 -->
<span style="font-weight: 600; color: #222222;">加粗内容</span>
```

### 卡片样式

```html
<!-- 普通卡片 -->
<div style="background-color: #f7f7f7; padding: 16px 18px; margin: 0 0 16px 0; border-radius: 6px;">
  <p style="font-size: 16px; color: #444444; line-height: 1.75; text-align: justify; margin: 0;">
    卡片内容
  </p>
</div>

<!-- 信息卡片（蓝色边框） -->
<div style="background-color: #f7f7f7; padding: 16px 18px; margin: 0 0 16px 0; border-radius: 6px;">
  <p style="font-size: 17px; font-weight: 600; color: #2b6cb0; line-height: 1.60; margin: 0 0 10px 0;">
    ▎标题
  </p>
  <p style="font-size: 16px; color: #444444; line-height: 1.75; text-align: justify; margin: 0;">
    内容
  </p>
</div>

<!-- 警示卡片 -->
<div style="background-color: #fff5f5; padding: 16px 18px; margin: 0 0 16px 0; border-radius: 6px; border-left: 4px solid #c53030;">
  <p style="font-size: 16px; color: #444444; line-height: 1.75; text-align: justify; margin: 0;">
    <span style="font-weight: 600; color: #c53030;">重要提示：</span>警示内容
  </p>
</div>
```

### 分割线

```html
<div style="height: 1px; background-color: #e5e5e5; margin: 24px 0;"></div>
```

---

## 列表样式

```html
<p style="font-size: 17px; color: #333333; line-height: 1.80; text-align: justify; margin: 0 0 10px 0; padding-left: 1.5em;">
  • 列表项一
</p>
<p style="font-size: 17px; color: #333333; line-height: 1.80; text-align: justify; margin: 0 0 10px 0; padding-left: 1.5em;">
  • 列表项二
</p>
```

---

## 输出

生成 HTML 文件后，使用 `open` 命令打开：

```bash
open /path/to/output-toutiao.html
```

文件命名：`{article-name}-toutiao.html`
