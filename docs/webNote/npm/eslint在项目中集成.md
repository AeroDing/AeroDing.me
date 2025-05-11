---
tags:
 - eslint
 - npm
---

# 现代化 ESLint 配置集成指南：基于 antfu/eslint-config 的最佳实践

推荐理由：

1. **社区权威与活跃维护**  
   `antfu/eslint-config` 由知名前端开发者 Anthony Fu 维护，广泛应用于 Vue、Vite、UnoCSS 等主流开源项目，社区活跃、更新及时，能持续跟进前端最佳实践。

2. **零配置开箱即用**  
   集成了 TypeScript、Vue、React、Prettier、格式化、风格统一等多套规则，无需繁琐配置，适配主流前端技术栈，极大简化 ESLint 配置流程。

3. **极致开发体验**  
   内置自动修复、智能排序、格式化与代码风格统一，配合 VSCode 插件可实现保存自动修复，提升团队协作效率，减少代码 review 成本。

4. **高度可扩展与自定义**  
   支持按需覆盖、扩展规则，兼容 monorepo、多包管理等复杂项目结构，满足企业级项目的灵活需求。

5. **最佳实践沉淀**  
   规则集融合了作者及社区多年实战经验，兼顾代码规范性与开发效率，避免过度限制，适合现代前端项目落地。

综上，`antfu/eslint-config` 是当前前端项目集成 ESLint 的首选方案，兼具易用性、规范性与可维护性，强烈推荐在新老项目中统一采用。

## 特性对比
| 特性                | 传统 ESLint 配置       | antfu/eslint-config      |
|---------------------|-----------------------|--------------------------|
| 配置架构            | 层级式 cascading      | 扁平化 flat config       |
| 框架支持            | 手动配置插件          | 声明式自动加载           |
| 格式化集成          | 需单独配置 Prettier   | 内置 formatters 系统     |
| 类型感知            | 复杂 TS 配置          | 开箱即用类型检查         |
| 规则维护            | 手动管理              | 持续维护的预设规则集     |


## 安装cli方式

::: code-group

```bash [pnpm]
pnpm dlx @antfu/eslint-config@latest
```

```bash [npm]
npm @antfu/eslint-config@latest
```

```bash [yarn]
yarn dlx @antfu/eslint-config@latest
```

:::



## 详细配置与使用说明

如需更细致的自定义和进阶配置，可参考官方文档：[antfu/eslint-config](https://github.com/antfu/eslint-config)。
