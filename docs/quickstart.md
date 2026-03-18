# 快速开始

## 在线使用（推荐）

**访问地址：** https://articlelayout.netlify.app

无需安装，打开即用。

## 本地安装

### 方法一：npm安装

```bash
# 安装
npm install -g articlelayout

# 使用
articlelayout input.md -o output.html
```

### 方法二：源码安装

```bash
# 克隆仓库
git clone https://github.com/AIPMAndy/ArticleLayout.git
cd ArticleLayout

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 打开 http://localhost:3000
```

## 基础用法

### 1. 命令行使用

```bash
# 基础排版
articlelayout article.md

# 指定模板
articlelayout article.md -t business

# 指定输出
articlelayout article.md -o output.html

# 生成海报
articlelayout article.md --poster cover

# 完整示例
articlelayout article.md -t magazine -o article.html --poster cover --toc
```

### 2. Node.js API

```javascript
const ArticleLayout = require('articlelayout');

// 基础使用
const html = ArticleLayout.render('# Hello World');

// 高级配置
const html = ArticleLayout.render(markdown, {
  template: 'business',
  theme: {
    primary: '#1890FF',
    font: 'PingFang SC'
  },
  features: {
    toc: true,
    nightMode: true,
    animation: true
  }
});

// 生成海报
ArticleLayout.poster(markdown, {
  type: 'cover',
  style: 'gradient',
  output: 'cover.png'
});
```

### 3. 浏览器使用

```html
<!DOCTYPE html>
<html>
<head>
  <script src="https://cdn.jsdelivr.net/npm/articlelayout@latest/dist/articlelayout.min.js"></script>
</head>
<body>
  <div id="editor"></div>
  <div id="preview"></div>
  
  <script>
    const editor = document.getElementById('editor');
    const preview = document.getElementById('preview');
    
    // 实时预览
    editor.addEventListener('input', (e) => {
      const html = ArticleLayout.render(e.target.value);
      preview.innerHTML = html;
    });
  </script>
</body>
</html>
```

## 模板列表

| 模板ID | 名称 | 适用场景 |
|--------|------|----------|
| business | 商务经典 | 商业分析、行业报告 |
| literary | 文艺清新 | 个人随笔、旅行游记 |
| tech | 科技极客 | 技术教程、产品评测 |
| minimal | 简约现代 | 观点输出、知识分享 |
| story | 故事叙述 | 人物专访、品牌故事 |
| magazine | 杂志风格 | 深度报道、专题策划 |
| academic | 学术严谨 | 论文、研究报告 |
| cards | 卡片流 | 清单、推荐、合集 |
| timeline | 时间轴 | 历史回顾、项目复盘 |
| dialogue | 对话式 | 访谈、问答、辩论 |
| news | 新闻快讯 | 热点评论、快讯报道 |
| tutorial | 教程步骤 | 操作指南、食谱、DIY |

## 配置选项

```javascript
{
  // 模板选择
  template: 'business',
  
  // 主题配置
  theme: {
    primary: '#1890FF',      // 主色
    secondary: '#666666',    // 次要色
    background: '#FFFFFF',   // 背景色
    font: 'PingFang SC'      // 字体
  },
  
  // 功能开关
  features: {
    toc: true,           // 目录
    nightMode: true,     // 夜间模式
    animation: true,     // 动画效果
    lazyLoad: true,      // 图片懒加载
    copyCode: true,      // 代码复制
    progressBar: true    // 阅读进度条
  },
  
  // 排版选项
  layout: {
    lineHeight: 1.8,     // 行高
    paragraphSpacing: '1.5em',  // 段落间距
    maxWidth: '800px'    // 最大宽度
  }
}
```

## 下一步

- [查看模板示例](../examples/)
- [阅读API文档](./api.md)
- [自定义模板开发](./template-development.md)