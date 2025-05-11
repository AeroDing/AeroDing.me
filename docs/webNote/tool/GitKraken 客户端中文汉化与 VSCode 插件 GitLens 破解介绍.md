---
tags:
 - tool
 - gitkraken
 - gitlens
 - vscode
 - plugin
---

# GitKraken 客户端中文汉化与 VSCode 插件 GitLens 破解介绍

本文简要介绍了两个实用工具：GitKraken 的中文汉化补丁和 VSCode 插件 GitLens 的破解激活工具，帮助用户更好地使用这两款提升 Git 工作效率的软件。

---

## GitKraken 客户端中文汉化补丁

GitKraken 是一款流行的 Git 图形界面客户端，因其友好的界面和强大的功能受到广泛欢迎，但官方暂未提供简体中文支持。为解决这一问题，开发者在 GitHub 上发布了一个中文汉化补丁项目[yk47g/gitkraken-chinese]，通过替换 GitKraken 安装目录中的语言文件，实现界面中文化。

### 汉化原理

- 该汉化方案通过修改 GitKraken 软件目录下的 English 语言对应的 JSON 文件（`strings.json`）来完成翻译。
- 汉化文件由自动翻译工具辅助生成，支持有道、OpenAI、DeepSeek 等翻译 API（需用户自行申请 API Key）。


### 安装步骤

1. 从项目中下载与你当前 GitKraken 版本匹配的 `.json` 文件，重命名为 `strings.json`。
2. 替换 GitKraken 安装目录下对应的 `strings.json` 文件，路径因操作系统不同而异：
    - Windows：`%程序安装目录%\gitkraken\app-x.x.x\resources\app\src\strings.json`
    - macOS：`/Applications/GitKraken.app/Contents/Resources/app/src/strings.json`
    - Linux：视安装方式不同，可能在 `/usr/share/gitkraken/resources/app.asar.unpacked/src/strings.json` 或 `/opt/gitkraken/resources/app.asar.unpacked/src/strings.json`
3. 重启 GitKraken，界面即生效中文显示。

### 特色与维护

- 汉化项目持续更新，支持 GitKraken 9.12.0 到 11.0.0 等多个版本。
- 统一了大量 Git 术语的翻译，如“Cherry Pick”翻译为“拣选”，“Pull Request”翻译为“拉取请求”等。
- 项目欢迎社区参与讨论翻译用词，保证术语一致性和专业性。

---

## VSCode 插件 GitLens Pro 破解激活工具

GitLens 是 VSCode 中非常强大的 Git 扩展，提供丰富的代码注释、历史查看和协作功能。GitLens Pro 版本包含更多高级功能，但需付费激活。

在 GitHub 上有一个名为 [chengazhen/gitlens-pro] 的项目，提供了一个 GitLens Pro 的激活工具，帮助用户激活 Pro 功能。

### 使用说明

- 推荐使用 GitLens 15.1.0 版本，新版本也可能支持。
- 需先登录 GitLens（注册邮箱随意），登录后才能触发激活。
- 激活工具根据操作系统不同，提供对应的可执行文件：
    - Windows：双击运行 `activate.exe`
    - macOS：运行 `chmod +x activate_mac_arm64 && ./activate_mac_arm64`
    - Linux：运行 `./activate`
- 运行后根据提示操作即可完成激活。

---

## 总结

- **GitKraken 中文汉化补丁** 通过替换语言文件实现界面中文，极大提升了中文用户的使用体验，且项目活跃持续更新，支持多版本。
- **GitLens Pro 激活工具** 方便用户免费体验 GitLens 的高级功能，支持多平台操作，使用简单。

这两个项目均托管于 GitHub，方便用户下载和参与社区交流，是提升 Git 工作效率的有力辅助工具。

---

*注：以上内容基于公开 GitHub 项目资料整理，使用时请遵守相关软件许可协议。*

---

## 参考链接

- [GitKraken 中文汉化补丁](https://github.com/yk47g/gitkraken-chinese)
- [GitLens Pro 激活工具](https://github.com/chengazhen/gitlens-pro)

