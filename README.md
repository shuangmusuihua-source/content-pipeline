# Content Pipeline

内容处理流水线：翻译 → 去AI味 → 多平台排版。

将英文内容转换为中文，优化表达，并输出为微信公众号、今日头条等平台的专业排版格式。

## 功能特性

- **智能翻译** - 英文翻译为中文 Markdown，保留原文结构
- **去 AI 味** - 识别并修复 AI 写作模式，让文本更自然
- **多平台排版** - 支持微信公众号、今日头条等专业排版格式
- **浏览器预览** - 生成 HTML 文件，一键打开预览，复制粘贴即可发布

## 安装

```bash
npx skills add shuangmusuihua-source/content-pipeline
```

## 使用方法

### 方式一：提供网页链接

```
https://example.com/english-article
```

### 方式二：翻译本地文件

```
翻译 ~/Documents/article.txt 并转成微信样式
```

### 方式三：直接粘贴文本

```
把这段英文翻译成中文，发到今日头条：
[粘贴英文内容]
```

## 工作流程

```
输入（URL/本地文件/直接文本）
    ↓
1. 获取内容
    ↓
2. 翻译为中文 Markdown
    ↓
3. 去除 AI 写作痕迹
    ↓
4. 选择目标平台
    ↓
5. 生成排版 HTML
    ↓
6. 浏览器预览
    ↓
7. 手动发布到平台
```

## 支持的平台

| 平台 | 代码 | 风格特点 |
|------|------|----------|
| 微信公众号 | wechat | 暖色调、米色背景、印刷级排版 |
| 今日头条 | toutiao | 白底黑字、红色强调、现代简洁 |

## 子 Skills

本插件包含以下可单独调用的子 skills：

| Skill | 功能 | 调用方式 |
|-------|------|----------|
| translate | 英文翻译为中文 Markdown | `Skill(skill: "content-pipeline:translate")` |
| wechat | 微信公众号格式化 | `Skill(skill: "content-pipeline:wechat")` |
| toutiao | 今日头条格式化 | `Skill(skill: "content-pipeline:toutiao")` |

## 依赖

- `humanizer-zh` skill - 用于去除 AI 写作痕迹

## 输出文件

生成的 HTML 文件命名规则：

- 微信公众号：`{article-name}-wechat.html`
- 今日头条：`{article-name}-toutiao.html`

## 发布指导

### 微信公众号

1. 登录 [mp.weixin.qq.com](https://mp.weixin.qq.com)
2. 进入素材管理 → 新建图文
3. 全选复制 HTML 内容 → 粘贴到编辑器
4. 保存 / 发布

### 今日头条

1. 登录 [mp.toutiao.com](https://mp.toutiao.com)
2. 发布文章 → 粘贴内容
3. 选择分类 → 发布

## 注意事项

1. **翻译质量** - 保持原文含义，专业术语双语标注
2. **AI 痕迹** - 翻译后的文本通常有明显 AI 味，会自动调用 humanizer-zh 处理
3. **平台兼容** - 微信需用 table 实现背景色，头条可直接用 div
4. **预览确认** - 生成后会自动打开浏览器让用户确认效果

## License

MIT
