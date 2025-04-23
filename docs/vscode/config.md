---
title: VSCode 配置
tags:
  - vscode
  - config
---

# vscode 用户配置

## 配置文件

```jsonc
{
    // 编辑器核心配置
    "editor.cursorSmoothCaretAnimation": "on", // 启用光标插入符平滑动画效果
    "editor.fontFamily": "Input Mono, monospace", // 设置编辑器字体族
    "editor.guides.bracketPairs": "active", // 在活动括号对周围显示引导线
    "editor.lineNumbers": "interval", // 行号显示模式：间隔显示（如5,10,15...）
    "editor.renderWhitespace": "boundary", // 显示边界空白字符（单词间空格等）
    "window.autoDetectColorScheme": true, // 自动检测系统颜色方案
    "workbench.colorTheme": "Vitesse Dark", // 主颜色主题
    "workbench.editor.tabActionLocation": "left", // 标签页操作按钮位置
    "workbench.fontAliasing": "antialiased", // 字体抗锯齿渲染方式
    "workbench.iconTheme": "catppuccin-perfect-mocha", // 图标主题
    "workbench.list.smoothScrolling": true, // 列表平滑滚动
    "workbench.preferredLightColorTheme": "Vitesse Light", // 浅色模式备用主题
    "workbench.productIconTheme": "icons-carbon", // 产品图标主题
    "workbench.startupEditor": "newUntitledFile", // 启动时打开新空白文件
    "workbench.tree.expandMode": "singleClick", // 资源管理器单击展开
    "workbench.tree.indent": 10, // 树状结构缩进量（像素）
    "debug.onTaskErrors": "debugAnyway", // 遇到任务错误时仍继续调试
    "diffEditor.ignoreTrimWhitespace": false, // 差异编辑器不忽略空白修改
    "editor.wordSeparators": "`~!@#%^&*()=+[{]}\\|;:'\",.<>/?",
    "editor.find.addExtraSpaceOnTop": false,
    "editor.inlineSuggest.enabled": true, // 启用行内代码建议
    "editor.multiCursorModifier": "ctrlCmd", // 多光标快捷键使用Ctrl/Cmd
    "editor.suggestSelection": "first", // 自动选择建议列表首项
    "editor.tabSize": 2, // Tab缩进设置为2空格
    "editor.unicodeHighlight.invisibleCharacters": false, // 不显示Unicode不可见字符提示
    "editor.stickyScroll.enabled": true, // 启用粘性滚动功能
    "editor.hover.sticky": true, // 保持悬停提示框直到手动关闭
    "editor.codeActionsOnSave": {
        "source.fixAll": "never", // 禁用所有自动修复
        "source.fixAll.eslint": "explicit", // 仅显式调用时运行ESLint修复
        "source.organizeImports": "always" // 总是自动整理import语句
    },
    "editor.foldingImportsByDefault": true, // 默认折叠import语句
    "editor.foldOnLoad": true, // 打开文件时自动折叠到预设层级
    "editor.foldLevel": 4, // 默认折叠层级深度
    "explorer.confirmDelete": false, // 删除文件时无需确认
    "explorer.confirmDragAndDrop": false, // 拖拽移动文件时无需确认
    "files.eol": "\n", // 文件默认换行符为LF
    "files.insertFinalNewline": true, // 保存时自动插入文件末尾换行
    "files.simpleDialog.enable": true, // 启用简洁文件对话框
    "git.autofetch": true, // 自动拉取远程Git变更
    "git.confirmSync": false, // Git同步时无需确认
    "git.enableSmartCommit": true, // 启用智能提交（无stage时直接commit）
    "git.untrackedChanges": "separate", // 未跟踪文件单独显示
    "scm.diffDecorationsGutterWidth": 2,
    "terminal.integrated.cursorBlinking": true, // 终端光标闪烁
    "terminal.integrated.cursorStyle": "line", // 终端光标样式为竖线
    "terminal.integrated.fontWeight": "300", // 终端字体粗细
    "terminal.integrated.persistentSessionReviveProcess": "never", // 终端会话不自动恢复进程
    "terminal.integrated.tabs.enabled": true, // 启用终端标签页
    "workbench.editor.closeOnFileDelete": true, // 文件删除时自动关闭对应标签
    "workbench.editor.highlightModifiedTabs": true, // 高亮修改过的标签页
    "workbench.editor.limit.enabled": true, // 启用编辑器数量限制
    "workbench.editor.limit.perEditorGroup": true, // 每个编辑器组单独限制
    "workbench.editor.limit.value": 5, // 每个编辑器组最大标签数
    "search.exclude": {
        "**/*.snap": true,
        "**/*.svg": true,
        "**/.git": true,
        "**/.github": false,
        "**/.nuxt": true,
        "**/.output": true,
        "**/.pnpm": true,
        "**/.vscode": true,
        "**/.yarn": true,
        "**/assets": true,
        "**/bower_components": true,
        "**/dist/**": true,
        "**/logs": true,
        "**/node_modules": true,
        "**/out/**": true,
        "**/package-lock.json": true,
        "**/pnpm-lock.yaml": true,
        "**/public": true,
        "**/temp": true,
        "**/yarn.lock": true,
        "**/CHANGELOG*": true,
        "**/LICENSE*": true
    },
    "window.dialogStyle": "custom",
    "window.nativeTabs": true,
    "window.title": "${rootName}", // 窗口标题显示当前根目录名称
    "window.titleBarStyle": "custom", // 使用自定义标题栏样式
    "extensions.autoUpdate": "onlyEnabledExtensions", // 仅自动更新已启用扩展
    "emmet.showSuggestionsAsSnippets": true, // Emmet建议以代码片段形式展示
    "emmet.triggerExpansionOnTab": false, // Tab键不触发Emmet展开
    "errorLens.enabledDiagnosticLevels": [
        "warning",
        "error"
    ], // ErrorLens高亮级别
    "errorLens.excludeBySource": [
        "cSpell",
        "Grammarly",
        "eslint"
    ], // ErrorLens排除来源
    "eslint.codeAction.showDocumentation": {
        "enable": true
    }, // 显示ESLint规则文档
    "eslint.quiet": true, // 只显示错误和警告，忽略提示
    "eslint.rules.customizations": [
        {
            "rule": "style/*",
            "severity": "off"
        },
        {
            "rule": "format/*",
            "severity": "off"
        },
        {
            "rule": "*-indent",
            "severity": "off"
        },
        {
            "rule": "*-spacing",
            "severity": "off"
        },
        {
            "rule": "*-spaces",
            "severity": "off"
        },
        {
            "rule": "*-order",
            "severity": "off"
        },
        {
            "rule": "*-dangle",
            "severity": "off"
        },
        {
            "rule": "*-newline",
            "severity": "off"
        },
        {
            "rule": "*quotes",
            "severity": "off"
        },
        {
            "rule": "*semi",
            "severity": "off"
        }
    ],
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        "typescript",
        "typescriptreact",
        "vue",
        "html",
        "markdown",
        "json",
        "jsonc",
        "yaml",
        "toml"
    ],
    "github.copilot.enable": {
        "*": true,
        "markdown": true,
        "plaintext": false
    }, // Copilot启用范围
    "cSpell.allowCompoundWords": true, // 拼写检查允许复合词
    "cSpell.language": "en,en-US", // 拼写检查语言
    "css.lint.hexColorLength": "ignore",
    "githubIssues.workingIssueFormatScm": "#${issueNumberLabel}",
    "githubPullRequests.fileListLayout": "tree",
    "gitlens.codeLens.authors.enabled": false,
    "gitlens.codeLens.enabled": false,
    "gitlens.codeLens.recentChange.enabled": false,
    "gitlens.menus": {
        "editor": {
            "blame": false,
            "clipboard": true,
            "compare": true,
            "history": false,
            "remote": false
        },
        "editorGroup": {
            "blame": true,
            "compare": false
        },
        "editorTab": {
            "clipboard": true,
            "compare": true,
            "history": true,
            "remote": true
        },
        "explorer": {
            "clipboard": true,
            "compare": true,
            "history": true,
            "remote": true
        },
        "scm": {
            "authors": true
        },
        "scmGroup": {
            "compare": true,
            "openClose": true,
            "stash": true
        },
        "scmGroupInline": {
            "stash": true
        },
        "scmItem": {
            "clipboard": true,
            "compare": true,
            "history": true,
            "remote": false,
            "stash": true
        }
    },
    "i18n-ally.autoDetection": false,
    "i18n-ally.displayLanguage": "en",
    "i18n-ally.ignoredLocales": [],
    "iconify.annotations": true,
    "iconify.inplace": true,
    "svg.preview.mode": "svg",
    "prettier.enable": false, // 关闭Prettier格式化
    "prettier.printWidth": 200, // Prettier单行最大长度
    "prettier.semi": false, // Prettier不加分号
    "prettier.singleQuote": true, // Prettier使用单引号
    // updated 2025-03-10 06:42
    // https://github.com/antfu/vscode-file-nesting-config
    "explorer.fileNesting.enabled": true, // 启用资源管理器文件嵌套
    "explorer.fileNesting.expand": false, // 默认不自动展开嵌套
    "explorer.fileNesting.patterns": { // 文件嵌套规则
        ".clang-tidy": ".clang-format, .clangd, compile_commands.json",
        ".env": "*.env, .env.*, .envrc, env.d.ts",
        ".gitignore": ".gitattributes, .gitmodules, .gitmessage, .lfsconfig, .mailmap, .git-blame*",
        ".project": ".classpath",
        "+layout.svelte": "+layout.ts,+layout.ts,+layout.js,+layout.server.ts,+layout.server.js,+layout.gql",
        "+page.svelte": "+page.server.ts,+page.server.js,+page.ts,+page.js,+page.gql",
        "ansible.cfg": "ansible.cfg, .ansible-lint, requirements.yml",
        "app.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "artisan": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, server.php, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, webpack.mix.js, windi.config.*",
        "astro.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "build-wrapper.log": "build-wrapper*.log, build-wrapper-dump*.json, build-wrapper-win*.exe, build-wrapper-linux*, build-wrapper-macosx*",
        "BUILD.bazel": "*.bzl, *.bazel, *.bazelrc, bazel.rc, .bazelignore, .bazelproject, .bazelversion, MODULE.bazel.lock, WORKSPACE",
        "Cargo.toml": ".clippy.toml, .rustfmt.toml, Cargo.Bazel.lock, Cargo.lock, clippy.toml, cross.toml, insta.yaml, rust-toolchain.toml, rustfmt.toml",
        "CMakeLists.txt": "*.cmake, *.cmake.in, .cmake-format.yaml, CMakePresets.json, CMakeCache.txt",
        "composer.json": ".php*.cache, composer.lock, phpunit.xml*, psalm*.xml",
        "default.nix": "shell.nix",
        "deno.json*": "*.env, .env.*, .envrc, api-extractor.json, deno.lock, env.d.ts, import-map.json, import_map.json, jsconfig.*, tsconfig.*, tsdoc.*",
        "Dockerfile": "*.dockerfile, .devcontainer.*, .dockerignore, captain-definition, compose.*, docker-compose.*, dockerfile*",
        "flake.nix": "flake.lock",
        "gatsby-config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, gatsby-browser.*, gatsby-node.*, gatsby-ssr.*, gatsby-transformer.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "gemfile": ".ruby-version, gemfile.lock",
        "go.mod": ".air*, go.sum",
        "go.work": "go.work.sum",
        "hatch.toml": ".editorconfig, .flake8, .isort.cfg, .python-version, hatch.toml, requirements*.in, requirements*.pip, requirements*.txt, tox.ini",
        "I*.cs": "$(capture).cs",
        "Makefile": "*.mk",
        "mix.exs": ".credo.exs, .dialyzer_ignore.exs, .formatter.exs, .iex.exs, .tool-versions, mix.lock",
        "next.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, next-env.d.ts, next-i18next.config.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "nuxt.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .nuxtignore, .nuxtrc, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "package.json": "*.code-workspace, .browserslist*, .circleci*, .commitlint*, .cspell*, .cursorrules, .cz-config.js, .czrc, .dlint.json, .dprint.json*, .editorconfig, .eslint*, .firebase*, .flowconfig, .github*, .gitlab*, .gitmojirc.json, .gitpod*, .huskyrc*, .jslint*, .knip.*, .lintstagedrc*, .ls-lint.yml, .markdownlint*, .node-version, .nodemon*, .npm*, .nvmrc, .pm2*, .pnp.*, .pnpm*, .prettier*, .pylintrc, .release-please*.json, .releaserc*, .ruff.toml, .sentry*, .shellcheckrc, .simple-git-hooks*, .stackblitz*, .styleci*, .stylelint*, .tazerc*, .textlint*, .tool-versions, .travis*, .versionrc*, .vscode*, .watchman*, .windsurfrules, .xo-config*, .yamllint*, .yarnrc*, Procfile, apollo.config.*, appveyor*, azure-pipelines*, biome.json*, bower.json, build.config.*, bun.lock, bun.lockb, bunfig.toml, colada.options.ts, commitlint*, crowdin*, cspell*, dangerfile*, dlint.json, dprint.json*, ec.config.*, electron-builder.*, eslint*, firebase.json, grunt*, gulp*, jenkins*, knip.*, lerna*, lint-staged*, nest-cli.*, netlify*, nixpacks*, nodemon*, npm-shrinkwrap.json, nx.*, package-lock.json, package.nls*.json, phpcs.xml, pm2.*, pnpm*, prettier*, pullapprove*, pyrightconfig.json, release-please*.json, release-tasks.sh, release.config.*, renovate*, rolldown.config.*, rollup.config.*, rspack*, ruff.toml, sentry.*.config.ts, simple-git-hooks*, sonar-project.properties, stylelint*, tsdown.config.*, tslint*, tsup.config.*, turbo*, typedoc*, unlighthouse*, vercel*, vetur.config.*, webpack*, workspace.json, wrangler.*, xo.config.*, yarn*",
        "Pipfile": ".editorconfig, .flake8, .isort.cfg, .python-version, Pipfile, Pipfile.lock, requirements*.in, requirements*.pip, requirements*.txt, tox.ini",
        "pubspec.yaml": ".metadata, .packages, all_lint_rules.yaml, analysis_options.yaml, build.yaml, pubspec.lock, pubspec_overrides.yaml",
        "pyproject.toml": ".commitlint*, .cspell*, .dlint.json, .dprint.json*, .editorconfig, .eslint*, .flake8, .flowconfig, .isort.cfg, .jslint*, .lintstagedrc*, .ls-lint.yml, .markdownlint*, .pdm-python, .pdm.toml, .prettier*, .pylintrc, .python-version, .ruff.toml, .shellcheckrc, .stylelint*, .textlint*, .xo-config*, .yamllint*, MANIFEST.in, Pipfile, Pipfile.lock, biome.json*, commitlint*, cspell*, dangerfile*, dlint.json, dprint.json*, eslint*, hatch.toml, lint-staged*, pdm.lock, phpcs.xml, poetry.lock, poetry.toml, prettier*, pyproject.toml, pyrightconfig.json, requirements*.in, requirements*.pip, requirements*.txt, ruff.toml, setup.cfg, setup.py, stylelint*, tox.ini, tslint*, uv.lock, uv.toml, xo.config.*",
        "quasar.conf.js": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, quasar.extensions.json, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "readme*": "AUTHORS, Authors, BACKERS*, Backers*, CHANGELOG*, CITATION*, CODEOWNERS, CODE_OF_CONDUCT*, CONTRIBUTING*, CONTRIBUTORS, COPYING*, CREDITS, Changelog*, Citation*, Code_Of_Conduct*, Codeowners, Contributing*, Contributors, Copying*, Credits, GOVERNANCE.MD, Governance.md, HISTORY.MD, History.md, LICENSE*, License*, MAINTAINERS, Maintainers, README-*, README_*, RELEASE_NOTES*, ROADMAP.MD, Readme-*, Readme_*, Release_Notes*, Roadmap.md, SECURITY.MD, SPONSORS*, Security.md, Sponsors*, authors, backers*, changelog*, citation*, code_of_conduct*, codeowners, contributing*, contributors, copying*, credits, governance.md, history.md, license*, maintainers, readme-*, readme_*, release_notes*, roadmap.md, security.md, sponsors*",
        "Readme*": "AUTHORS, Authors, BACKERS*, Backers*, CHANGELOG*, CITATION*, CODEOWNERS, CODE_OF_CONDUCT*, CONTRIBUTING*, CONTRIBUTORS, COPYING*, CREDITS, Changelog*, Citation*, Code_Of_Conduct*, Codeowners, Contributing*, Contributors, Copying*, Credits, GOVERNANCE.MD, Governance.md, HISTORY.MD, History.md, LICENSE*, License*, MAINTAINERS, Maintainers, README-*, README_*, RELEASE_NOTES*, ROADMAP.MD, Readme-*, Readme_*, Release_Notes*, Roadmap.md, SECURITY.MD, SPONSORS*, Security.md, Sponsors*, authors, backers*, changelog*, citation*, code_of_conduct*, codeowners, contributing*, contributors, copying*, credits, governance.md, history.md, license*, maintainers, readme-*, readme_*, release_notes*, roadmap.md, security.md, sponsors*",
        "README*": "AUTHORS, Authors, BACKERS*, Backers*, CHANGELOG*, CITATION*, CODEOWNERS, CODE_OF_CONDUCT*, CONTRIBUTING*, CONTRIBUTORS, COPYING*, CREDITS, Changelog*, Citation*, Code_Of_Conduct*, Codeowners, Contributing*, Contributors, Copying*, Credits, GOVERNANCE.MD, Governance.md, HISTORY.MD, History.md, LICENSE*, License*, MAINTAINERS, Maintainers, README-*, README_*, RELEASE_NOTES*, ROADMAP.MD, Readme-*, Readme_*, Release_Notes*, Roadmap.md, SECURITY.MD, SPONSORS*, Security.md, Sponsors*, authors, backers*, changelog*, citation*, code_of_conduct*, codeowners, contributing*, contributors, copying*, credits, governance.md, history.md, license*, maintainers, readme-*, readme_*, release_notes*, roadmap.md, security.md, sponsors*",
        "remix.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, remix.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "requirements.txt": ".editorconfig, .flake8, .isort.cfg, .python-version, requirements*.in, requirements*.pip, requirements*.txt, tox.ini",
        "rush.json": "*.code-workspace, .browserslist*, .circleci*, .commitlint*, .cspell*, .cursorrules, .cz-config.js, .czrc, .dlint.json, .dprint.json*, .editorconfig, .eslint*, .firebase*, .flowconfig, .github*, .gitlab*, .gitmojirc.json, .gitpod*, .huskyrc*, .jslint*, .knip.*, .lintstagedrc*, .ls-lint.yml, .markdownlint*, .node-version, .nodemon*, .npm*, .nvmrc, .pm2*, .pnp.*, .pnpm*, .prettier*, .pylintrc, .release-please*.json, .releaserc*, .ruff.toml, .sentry*, .shellcheckrc, .simple-git-hooks*, .stackblitz*, .styleci*, .stylelint*, .tazerc*, .textlint*, .tool-versions, .travis*, .versionrc*, .vscode*, .watchman*, .windsurfrules, .xo-config*, .yamllint*, .yarnrc*, Procfile, apollo.config.*, appveyor*, azure-pipelines*, biome.json*, bower.json, build.config.*, bun.lock, bun.lockb, bunfig.toml, colada.options.ts, commitlint*, crowdin*, cspell*, dangerfile*, dlint.json, dprint.json*, ec.config.*, electron-builder.*, eslint*, firebase.json, grunt*, gulp*, jenkins*, knip.*, lerna*, lint-staged*, nest-cli.*, netlify*, nixpacks*, nodemon*, npm-shrinkwrap.json, nx.*, package-lock.json, package.nls*.json, phpcs.xml, pm2.*, pnpm*, prettier*, pullapprove*, pyrightconfig.json, release-please*.json, release-tasks.sh, release.config.*, renovate*, rolldown.config.*, rollup.config.*, rspack*, ruff.toml, sentry.*.config.ts, simple-git-hooks*, sonar-project.properties, stylelint*, tsdown.config.*, tslint*, tsup.config.*, turbo*, typedoc*, unlighthouse*, vercel*, vetur.config.*, webpack*, workspace.json, wrangler.*, xo.config.*, yarn*",
        "sanity.config.*": "sanity.cli.*, sanity.types.ts, schema.json",
        "setup.cfg": ".editorconfig, .flake8, .isort.cfg, .python-version, MANIFEST.in, requirements*.in, requirements*.pip, requirements*.txt, setup.cfg, tox.ini",
        "setup.py": ".editorconfig, .flake8, .isort.cfg, .python-version, MANIFEST.in, requirements*.in, requirements*.pip, requirements*.txt, setup.cfg, setup.py, tox.ini",
        "shims.d.ts": "*.d.ts",
        "svelte.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, houdini.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, mdsvex.config.js, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vite.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "vite.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "vue.config.*": "*.env, .babelrc*, .codecov, .cssnanorc*, .env.*, .envrc, .htmlnanorc*, .lighthouserc.*, .mocha*, .postcssrc*, .terserrc*, api-extractor.json, ava.config.*, babel.config.*, capacitor.config.*, content.config.*, contentlayer.config.*, cssnano.config.*, cypress.*, env.d.ts, formkit.config.*, formulate.config.*, histoire.config.*, htmlnanorc.*, i18n.config.*, ionic.config.*, jasmine.*, jest.config.*, jsconfig.*, karma*, lighthouserc.*, panda.config.*, playwright.config.*, postcss.config.*, puppeteer.config.*, react-router.config.*, rspack.config.*, sst.config.*, svgo.config.*, tailwind.config.*, tsconfig.*, tsdoc.*, uno.config.*, unocss.config.*, vitest.config.*, vuetify.config.*, webpack.config.*, windi.config.*",
        "*.asax": "$(capture).*.cs, $(capture).*.vb",
        "*.ascx": "$(capture).*.cs, $(capture).*.vb",
        "*.ashx": "$(capture).*.cs, $(capture).*.vb",
        "*.aspx": "$(capture).*.cs, $(capture).*.vb",
        "*.axaml": "$(capture).axaml.cs",
        "*.bloc.dart": "$(capture).event.dart, $(capture).state.dart",
        "*.c": "$(capture).h",
        "*.cc": "$(capture).hpp, $(capture).h, $(capture).hxx, $(capture).hh",
        "*.cjs": "$(capture).cjs.map, $(capture).*.cjs, $(capture)_*.cjs",
        "*.component.ts": "$(capture).component.html, $(capture).component.spec.ts, $(capture).component.css, $(capture).component.scss, $(capture).component.sass, $(capture).component.less",
        "*.cpp": "$(capture).hpp, $(capture).h, $(capture).hxx, $(capture).hh",
        "*.cs": "$(capture).*.cs",
        "*.cshtml": "$(capture).cshtml.cs",
        "*.csproj": "*.config, *proj.user, appsettings.*, bundleconfig.json",
        "*.css": "$(capture).css.map, $(capture).*.css",
        "*.cxx": "$(capture).hpp, $(capture).h, $(capture).hxx, $(capture).hh",
        "*.dart": "$(capture).freezed.dart, $(capture).g.dart",
        "*.db": "*.db-shm, *.db-wal",
        "*.ex": "$(capture).html.eex, $(capture).html.heex, $(capture).html.leex",
        "*.fs": "$(capture).fs.js, $(capture).fs.js.map, $(capture).fs.jsx, $(capture).fs.ts, $(capture).fs.tsx, $(capture).fs.rs, $(capture).fs.php, $(capture).fs.dart",
        "*.go": "$(capture)_test.go",
        "*.java": "$(capture).class",
        "*.js": "$(capture).js.map, $(capture).*.js, $(capture)_*.js, $(capture).d.ts, $(capture).js.flow",
        "*.jsx": "$(capture).js, $(capture).*.jsx, $(capture)_*.js, $(capture)_*.jsx, $(capture).css, $(capture).module.css, $(capture).less, $(capture).module.less, $(capture).module.less.d.ts, $(capture).scss, $(capture).module.scss, $(capture).module.scss.d.ts",
        "*.master": "$(capture).*.cs, $(capture).*.vb",
        "*.md": "$(capture).*",
        "*.mjs": "$(capture).mjs.map, $(capture).*.mjs, $(capture)_*.mjs",
        "*.module.ts": "$(capture).resolver.ts, $(capture).controller.ts, $(capture).service.ts",
        "*.mts": "$(capture).mts.map, $(capture).*.mts, $(capture)_*.mts",
        "*.pubxml": "$(capture).pubxml.user",
        "*.py": "$(capture).pyi",
        "*.razor": "$(capture).razor.cs, $(capture).razor.css, $(capture).razor.scss",
        "*.resx": "$(capture).*.resx, $(capture).designer.cs, $(capture).designer.vb",
        "*.tex": "$(capture).acn, $(capture).acr, $(capture).alg, $(capture).aux, $(capture).bbl, $(capture).bbl-SAVE-ERROR, $(capture).bcf, $(capture).blg, $(capture).fdb_latexmk, $(capture).fls, $(capture).glg, $(capture).glo, $(capture).gls, $(capture).idx, $(capture).ind, $(capture).ist, $(capture).lof, $(capture).log, $(capture).lot, $(capture).nav, $(capture).out, $(capture).run.xml, $(capture).snm, $(capture).synctex.gz, $(capture).toc, $(capture).xdv",
        "*.ts": "$(capture).js, $(capture).d.ts.map, $(capture).*.ts, $(capture)_*.js, $(capture)_*.ts",
        "*.tsx": "$(capture).ts, $(capture).*.tsx, $(capture)_*.ts, $(capture)_*.tsx, $(capture).css, $(capture).module.css, $(capture).less, $(capture).module.less, $(capture).module.less.d.ts, $(capture).scss, $(capture).module.scss, $(capture).module.scss.d.ts, $(capture).css.ts",
        "*.vbproj": "*.config, *proj.user, appsettings.*, bundleconfig.json",
        "*.vue": "$(capture).*.ts, $(capture).*.js, $(capture).story.vue",
        "*.w": "$(capture).*.w, I$(capture).w",
        "*.wat": "$(capture).wasm",
        "*.xaml": "$(capture).xaml.cs"
    },
    "files.associations": {
        "*.cjson": "jsonc",
        "*.wxss": "css",
        "*.wxs": "javascript"
    },
    "emmet.includeLanguages": {
        "wxml": "html"
    },
    "minapp-vscode.disableAutoConfig": true,
    "workbench.preferredDarkColorTheme": "Palenight (Mild Contrast)", // 深色模式备用主题
    "terminal.integrated.env.osx": {
        "Q_NEW_SESSION": "1"
    },
    "cursor.cpp.disabledLanguages": [
        "plaintext"
    ],
    "update.releaseTrack": "prerelease", // 使用预发布版本通道
    "editor.accessibilitySupport": "on", // 启用辅助功能支持
    "javascript.updateImportsOnFileMove.enabled": "always", // JS文件移动时自动更新import
    "typescript.updateImportsOnFileMove.enabled": "always", // TS文件移动时自动更新import
    "cursor.cpp.enablePartialAccepts": true,
    "workbench.sideBar.location": "right", // 侧边栏显示在右侧
    "explorer.confirmPasteNative": false, // 粘贴本地文件时无需确认
    "workbench.layoutControl.enabled": false, // 关闭布局控制按钮
    "editor.linkedEditing": true, // 启用联动编辑
    "powermode.enabled": true, // 启用Power Mode特效
    "powermode.combo.counterEnabled": "hide", // 隐藏Power Mode连击计数
    "powermode.combo.timerEnabled": "hide", // 隐藏Power Mode计时器
    "powermode.presets": "fireworks", // Power Mode特效为烟花
    "powermode.shake.intensity": 0, // 关闭Power Mode抖动
    "errorLens.statusBarColorsEnabled": true, // ErrorLens启用状态栏颜色
    "editor.minimap.enabled": true, // 启用编辑器迷你地图
    "todo-tree.regex.regex": "(//|#|<!--|;|/\\*|^|^[ \\t]*(-|\\d+.))\\s*($TAGS)",
    "todo-tree.filtering.ignoreGitSubmodules": true,
    "todo-tree.tree.showCountsInTree": true,
    "todo-tree.regex.regexCaseSensitive": false,
    "todo-tree.general.statusBar": "current file",
    "todo-tree.general.tags": [
        "BUG",
        "FIXME",
        "TODO",
        "HACK",
        "XXX",
        "TAG",
        "DONE",
        "NOTE",
        "INFO",
        "OPTIMIZE"
    ],
    "todo-tree.highlights.defaultHighlight": {
        "icon": "alert",
        "type": "line",
    },
    "todo-tree.highlights.customHighlight": {
        "BUG": {
            "icon": "bug",
            "foreground": "#F56C6C",
        },
        "FIXME": {
            "icon": "flame",
            "foreground": "#FF9800",
        },
        "TODO": {
            "icon": "checklist",
            "foreground": "#FFEB38",
        },
        "HACK": {
            "icon": "versions",
            "foreground": "#E040FB",
        },
        "XXX": {
            "icon": "unverified",
            "foreground": "#E91E63",
        },
        "TAG": {
            "icon": "tag",
            "foreground": "#409EFF",
        },
        "DONE": {
            "icon": "verified",
            "foreground": "#0dff00",
        },
        "NOTE": {
            "icon": "note",
            "foreground": "#67C23A",
        },
        "INFO": {
            "icon": "info",
            "foreground": "#909399",
        },
        "OPTIMIZE": {
            "icon": "goal",
            "foreground": "#e6a23c"
        }
    },
}

```
