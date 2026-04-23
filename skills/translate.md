---
name: translate
description: |
  将英文内容翻译为中文，输出 Markdown 格式。
  保留原文结构，专业术语双语标注。
allowed-tools:
  - Read
  - Write
---

# Translate: 英文翻译为中文

将英文内容翻译为自然流畅的中文，输出 Markdown 格式。

## 翻译原则

### 1. 准确性

- 保持原文含义不变
- 不添加、不删减内容
- 数字、日期保持原格式

### 2. 结构保留

- 标题层级保持一致
- 列表结构保持一致
- 代码块不翻译（注释可翻译）
- 链接保持原 URL

### 3. 专业术语处理

- **首次出现**：英文（中文解释）
- **后续出现**：使用中文或通用缩写

示例：
```
原文：Machine Learning models
译文：机器学习（Machine Learning）模型
```

### 4. 语言风格

- 使用简体中文
- 句子简洁，避免长句
- 适当使用成语，但不过度
- 保持原文语气（正式/随意）

---

## Markdown 元素处理

| 原文元素 | 处理方式 |
|----------|----------|
| `# 标题` | 翻译标题文本 |
| `**粗体**` | 翻译内容，保留粗体 |
| `*斜体*` | 翻译内容，保留斜体 |
| `[链接](url)` | 翻译链接文本，URL 不变 |
| `![图片](url)` | 翻译 alt 文本 |
| `> 引用` | 翻译引用内容 |
| `- 列表` | 翻译列表项 |
| `` `代码` `` | 保留代码，不翻译 |
| `代码块` | 保留代码，注释可翻译 |

---

## 翻译示例

**原文：**

```markdown
# The Future of AI

Artificial Intelligence is transforming every industry. From healthcare to finance, **AI-powered solutions** are becoming the norm.

> The question is not whether AI will change your business, but how quickly.

Key benefits include:
- Automation of repetitive tasks
- Better decision-making through data analysis
- Personalized customer experiences
```

**译文：**

```markdown
# AI 的未来

人工智能正在改变每一个行业。从医疗到金融，**AI 驱动的解决方案**正在成为常态。

> 问题不在于 AI 是否会改变你的业务，而在于有多快。

主要优势包括：
- 自动化重复性任务
- 通过数据分析做出更好的决策
- 个性化的客户体验
```

---

## 输出格式

翻译完成后，输出：

1. 翻译后的 Markdown 文本
2. 如有专业术语，列出术语对照表（可选）
