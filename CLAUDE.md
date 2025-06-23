# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个基于 VitePress 的个人博客项目，使用 @sugarat/theme 主题。项目部署在两个站点：
- 主站: https://711799.xyz
- 备用站点: https://aeroding.github.io/AeroDing.me/

## 核心技术栈

- **VitePress**: 静态站点生成器
- **@sugarat/theme**: 博客主题，基于 VitePress
- **Vue 3**: 前端框架
- **TypeScript**: 类型系统
- **Element Plus**: UI 组件库
- **SCSS**: 样式预处理器
- **pnpm**: 包管理器

## 常用命令

### 开发命令
```bash
# 启动开发服务器
pnpm dev
# 或
npm run dev

# 构建生产版本
pnpm build
# 或
npm run build

# 本地预览构建结果
pnpm serve
# 或
npm run serve
```

## 项目结构

```
docs/                          # 文档内容目录
├── .vitepress/               # VitePress 配置
│   ├── config.mts           # 主配置文件
│   ├── blog-theme.ts        # 博客主题配置
│   └── theme/               # 自定义主题
│       ├── index.ts         # 主题入口
│       ├── style.scss       # 自定义样式
│       └── assets/          # 主题资源
├── public/                  # 静态资源
├── webNote/                 # 技术笔记分类
│   ├── npm/                # npm 相关
│   ├── react/              # React 相关
│   ├── tool/               # 工具相关
│   └── vscode/             # VSCode 相关
├── images/                 # 图片资源
├── about.md               # 关于页面
├── aboutme.md             # 个人介绍
└── index.md               # 首页
```

## 配置架构

### 主配置 (docs/.vitepress/config.mts)
- 继承 @sugarat/theme 博客主题
- 配置站点基本信息（标题、描述、语言等）
- 设置导航菜单和社交链接
- 配置网站图标和 meta 信息

### 主题配置 (docs/.vitepress/blog-theme.ts)
- 使用 @sugarat/theme 的 getThemeConfig
- 配置 3D 模型 (oml2d)
- 设置页脚信息
- 配置主题色和作者信息
- 管理友链和公告功能

### 主题扩展 (docs/.vitepress/theme/index.ts)
- 导入 @sugarat/theme 作为基础主题
- 可扩展自定义样式和组件

## 内容管理

### 文章分类
- `webNote/npm/`: NPM 相关技术文章
- `webNote/react/`: React 技术文章 
- `webNote/tool/`: 开发工具相关文章
- `webNote/vscode/`: VSCode 配置和插件文章
- `webNote/recommend/`: 软件推荐文章

### 图片管理
- 图片存放在 `docs/images/` 目录下
- 按功能模块分子目录存放
- 支持多种图片格式

## 部署配置

项目支持 GitHub Pages 部署：
- 配置了正确的 base 路径
- 设置了合适的网站图标路径
- 针对 GitHub Pages 优化了资源加载

## 特殊功能

### 3D 模型支持
- 使用 oml2d 库集成 Live2D 模型
- 支持移动端显示
- 配置了默认的 Senko 模型

### 搜索功能
- 默认启用 pagefind 离线全文搜索
- 支持中文搜索

### 主题定制
- 使用 el-blue 主题色
- 支持自定义 SCSS 样式
- 可配置用户主题 CSS

## 博客文章写作规范

### Front Matter 格式
每篇博客文章都应该在文件顶部添加 YAML Front Matter，格式如下：

```yaml
---
title: 文章标题
tags:
  - 标签1
  - 标签2
  - 标签3
---
```

**示例：**
```yaml
---
title: Cursor 切换到 VSCode 扩展商店的完整指南
tags:
  - vscode
  - cursor
  - extensions
---
```

**要求：**
- `title`: 必须，文章标题，应该简洁明确
- `tags`: 必须，至少包含 1-5 个相关标签
- 标签应该使用小写英文，多个单词用连字符连接
- 标签应该反映文章的主要技术栈、工具或主题

### 常用标签参考
- **前端技术**: `vue`, `react`, `javascript`, `typescript`, `html`, `css`
- **工具软件**: `vscode`, `cursor`, `git`, `npm`, `webpack`, `vite`
- **后端技术**: `node`, `python`, `java`, `go`, `database`
- **开发工具**: `development`, `productivity`, `automation`, `cli`
- **配置相关**: `config`, `setup`, `installation`, `configuration`
