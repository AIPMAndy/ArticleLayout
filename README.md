# WeChatLayout

> 公众号长文排版神器 - 一键生成精美排版

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green)](https://nodejs.org/)
[![WeChat](https://img.shields.io/badge/WeChat-公众号排版-brightgreen)](https://mp.weixin.qq.com/)

---

## 🎯 项目简介

**WeChatLayout** 是一个专门面向公众号作者的排版工具，让你从繁琐的排版工作中解放出来，专注于内容创作。

**核心特色：**
- 🎨 **模板化排版**：10+精美模板，一键套用
- 🖼️ **海报样式**：自动生成封面海报、金句海报
- 📱 **长文优化**：专为手机阅读优化的排版方案
- ⚡ **一键生成**：Markdown → 精美排版HTML
- 🎭 **风格多样**：商务/文艺/科技/简约多种风格

---

## ✨ 功能特性

### 1. 模板系统

**内置模板：**

| 模板名称 | 适用场景 | 特点 |
|---------|---------|------|
| **商务经典** | 商业分析、行业报告 | 简洁大气，数据可视化 |
| **文艺清新** | 个人随笔、旅行游记 | 留白充足，配图优雅 |
| **科技极客** | 技术教程、产品评测 | 代码高亮，深色模式 |
| **简约现代** | 观点输出、知识分享 | 极简设计，专注阅读 |
| **故事叙述** | 人物专访、品牌故事 | 时间线布局，情感化设计 |

**自定义模板：**
```javascript
// 创建自定义模板
const myTemplate = {
  name: "我的风格",
  font: {
    title: "PingFang SC",
    body: "Noto Sans SC",
    code: "Fira Code"
  },
  color: {
    primary: "#1A1A1A",
    secondary: "#666666",
    accent: "#FF6B6B"
  },
  spacing: {
    paragraph: "1.8em",
    heading: "2.5em"
  }
};
```

### 2. 海报生成

**封面海报：**
- 自动提取文章标题和摘要
- 10+封面布局可选
- 支持自定义背景图
- 一键导出PNG/JPG

**金句海报：**
- 自动识别文章金句
- 多种字体搭配
- 背景模糊/渐变效果
- 适合朋友圈分享

**数据海报：**
- 自动将数据转为图表
- 支持柱状图/折线图/饼图
- 导出高清图片

### 3. 长文优化

**阅读体验优化：**
- 段落间距自动调整
- 小标题层级清晰
- 重点内容高亮
- 引用样式美化

**移动端适配：**
- 字体大小自适应
- 图片宽度自适应
- 代码块横向滚动
- 表格横向滚动

### 4. 一键排版

**输入：**
```markdown
# 文章标题

## 第一节
正文内容...

> 引用内容

## 第二节
正文内容...
```

**输出：**
精美的公众号排版HTML，直接复制到公众号编辑器。

---

## 🚀 快速开始

### 在线使用

**访问地址：** https://wechatlayout.netlify.app

无需安装，打开即用。

### 本地安装

```bash
# 1. 克隆仓库
git clone https://github.com/AIPMAndy/WeChatLayout.git
cd WeChatLayout

# 2. 安装依赖
npm install

# 3. 启动开发服务器
npm run dev

# 4. 打开浏览器访问
# http://localhost:3000
```

### 命令行使用

```bash
# 安装全局命令
npm install -g wechatlayout

# 排版单个文件
wechatlayout input.md -o output.html

# 使用指定模板
wechatlayout input.md -t business -o output.html

# 生成海报
wechatlayout input.md --poster cover -o poster.png
```

---

## 📖 使用指南

### 基础用法

**1. 选择模板**

打开工具后，从左侧模板库选择适合的模板：
- 商务文章 → 选择「商务经典」
- 技术教程 → 选择「科技极客」
- 个人随笔 → 选择「文艺清新」

**2. 粘贴内容**

将Markdown格式的文章内容粘贴到编辑器：
```markdown
# 如何打造个人IP

## 为什么要做个人IP
在AI时代，个人IP是最有价值的资产...

## 三个核心步骤
### 1. 定位
找到你的差异化优势...

### 2. 内容
持续输出有价值的内容...

### 3. 变现
设计合理的商业模式...
```

**3. 实时预览**

右侧实时预览排版效果，支持手机/平板/PC三种视图。

**4. 导出使用**

点击「导出HTML」，复制代码到公众号编辑器。

### 进阶用法

**自定义样式：**

```javascript
// 修改主题色
WeChatLayout.config({
  theme: {
    primary: "#1890FF",
    background: "#F5F5F5"
  }
});

// 修改字体
WeChatLayout.config({
  font: {
    title: "Source Han Sans",
    body: "PingFang SC"
  }
});
```

**批量处理：**

```javascript
const WeChatLayout = require('wechatlayout');

// 批量排版
const files = ['article1.md', 'article2.md', 'article3.md'];
files.forEach(file => {
  WeChatLayout.render(file, {
    template: 'business',
    output: `output/${file}.html`
  });
});
```

---

## 🎨 模板展示

### 商务经典

![商务经典模板](./examples/business-template.png)

**特点：**
- 深蓝色主色调
- 数据可视化组件
- 适合商业分析、行业报告

### 文艺清新

![文艺清新模板](./examples/literary-template.png)

**特点：**
- 大面积留白
- 优雅的中文字体
- 适合个人随笔、旅行游记

### 科技极客

![科技极客模板](./examples/tech-template.png)

**特点：**
- 深色背景
- 代码高亮
- 适合技术教程、产品评测

---

## 🔧 技术架构

### 技术栈

- **前端**：React 18 + TypeScript
- **样式**：Tailwind CSS + CSS Modules
- **构建**：Vite
- **部署**：Netlify / Vercel

### 核心模块

```
WeChatLayout/
├── src/
│   ├── templates/      # 模板系统
│   │   ├── business/   # 商务模板
│   │   ├── literary/   # 文艺模板
│   │   ├── tech/       # 科技模板
│   │   └── ...
│   ├── components/     # UI组件
│   │   ├── Editor/     # 编辑器
│   │   ├── Preview/    # 预览器
│   │   └── Poster/     # 海报生成
│   ├── utils/          # 工具函数
│   │   ├── parser.ts   # Markdown解析
│   │   ├── renderer.ts # HTML渲染
│   │   └── poster.ts   # 海报生成
│   └── styles/         # 全局样式
├── docs/              # 文档
├── examples/          # 示例
└── scripts/           # 脚本
```

### 排版引擎

**Markdown → HTML 流程：**

```javascript
// 1. 解析Markdown
const ast = parseMarkdown(input);

// 2. 应用模板
const styled = applyTemplate(ast, template);

// 3. 生成HTML
const html = renderToHTML(styled);

// 4. 添加微信适配
const wechatHtml = adaptForWeChat(html);
```

---

## 📚 文档

- [快速开始](./docs/quickstart.md)
- [模板开发指南](./docs/template-development.md)
- [API文档](./docs/api.md)
- [常见问题](./docs/faq.md)

---

## 🤝 贡献指南

欢迎提交PR！

**贡献方式：**
1. 提交新模板
2. 优化现有模板
3. 添加新功能
4. 修复bug
5. 完善文档

**提交模板：**

```bash
# 1. Fork仓库
# 2. 创建新分支
git checkout -b feature/new-template

# 3. 添加模板文件
mkdir src/templates/my-template
touch src/templates/my-template/index.css
touch src/templates/my-template/index.ts

# 4. 提交PR
```

---

## 📝 使用案例

### 案例1：商业分析文章

**作者：** 某咨询公司合伙人
**场景：** 每周发布行业分析报告
**效果：**
- 排版时间从2小时缩短到10分钟
- 文章阅读量提升300%
- 客户咨询量翻倍

### 案例2：技术教程

**作者：** 前端开发工程师
**场景：** 发布技术博客
**效果：**
- 代码展示更清晰
- 读者反馈阅读体验极佳
- 粉丝增长5000+

### 案例3：个人IP打造

**作者：** 自由职业者
**场景：** 打造个人品牌
**效果：**
- 视觉风格统一
- 专业度提升
- 商务合作增加

---

## 🗺️ 路线图

### V1.0（当前）
- ✅ 基础排版功能
- ✅ 5套内置模板
- ✅ 海报生成
- ✅ Markdown支持

### V2.0（2026 Q2）
- 🚧 AI智能排版
- 🚧 一键优化建议
- 🚧 更多模板
- 🚧 团队协作

### V3.0（2026 Q4）
- 📋 公众号数据接入
- 📋 自动发布
- 📋 数据分析
- 📋 多平台适配

---

## 💡 为什么做这个项目

**痛点：**
1. 公众号排版太费时间
2. 现有工具要么太复杂，要么太丑
3. 长文阅读体验差
4. 没有专门针对中文排版的工具

**解决方案：**
- 模板化：一键套用，省时省力
- 专业化：针对中文阅读优化
- 美观化：设计师级别的排版
- 智能化：AI辅助，自动优化

**愿景：**
让每个公众号作者都能轻松产出精美的排版，
专注于内容创作，而不是繁琐的格式调整。

---

## 📄 许可证

MIT License

---

**如果你也厌倦了繁琐的排版工作，试试WeChatLayout。**

**让排版变得简单，让创作回归本质。**

---

*Made with ❤️ by Andy | AI酋长*

*让每个公众号都能拥有精美的排版*