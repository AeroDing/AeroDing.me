---
  -tags:
    - tool
    - 效率工具
---

# 基于 bumpp + conventional-changelog-cli 的版本自动化与 CHANGELOG 生成实践

## 简介
本实践文档介绍如何结合使用 `bumpp` 与 `conventional-changelog-cli` 实现前端项目的版本号自动化管理与 CHANGELOG 自动生成。通过配置自动化流程，可以在每次版本升级时自动生成规范化的变更日志、提交变更并打标签，极大提升团队协作效率与版本发布的规范性。适用于需要遵循语义化版本和规范化提交的项目，帮助开发者更好地追踪历史变更，提升项目可维护性和可追溯性。


## 安装相应依赖

::: code-group

```bash [npm]
npm install bumpp conventional-changelog-cli -D
```

```bash [yarn]
yarn add bumpp conventional-changelog-cli -D
```

```bash [pnpm]
pnpm add bumpp conventional-changelog-cli -D
```

:::

## 配置bumpp.config.js
```javascript
import { execSync } from 'node:child_process'
import { defineConfig } from 'bumpp'

export default defineConfig({
  all: true,
  // 在版本号变更提交之前执行
  execute: () => {
    // 生成或更新 CHANGELOG.md，-p angular 预设，-i 输入文件，-s 写回文件，-r 0 从头开始生成
    execSync('npx conventional-changelog -p angular -i CHANGELOG.md -s -r 0', { stdio: 'inherit' })

    // 把更新的 changelog 加入 git 暂存区
    execSync('git add CHANGELOG.md', { stdio: 'inherit' })
  },

  // 自动提交版本和 changelog 变更
  commit: true,

  // 自动打标签
  tag: true,

  // 自动推送到远程仓库
  push: true,
})

```


::: tip
通过上述方法，可采用交互式命令生成标签与日志，从而有助于提升管理与维护效率。

:::

## 使用方式

::: code-group

```bash [npm]
npx bumpp
```

```bash [yarn]
yarn bumpp
```

```bash [pnpm]
pnpm bumpp
```
