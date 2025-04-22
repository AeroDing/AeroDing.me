---
tags:
  - react
  - theme
  - css-in-js
  - antd
---

# React 主题方案切换

### 1. 基于CSS变量（CSS Custom Properties）的主题切换

#### 实现原理
- 在全局CSS（通常是`:root`选择器）中定义一组CSS变量，如`--theme-color`、`--background-color`等，表示主题相关的颜色和样式值。
- 针对不同主题（如"light"和"dark"），通过给根元素（如`<html>`或`<body>`）添加不同的类名（如`.dark`）或`data-theme`属性，覆盖这些CSS变量的值。
- 组件样式中使用`var(--theme-color)`等CSS变量引用颜色，实现样式的动态响应。
- 切换主题时，只需动态修改根元素的类名或属性，浏览器自动应用对应的CSS变量值，无需刷新页面。

#### 代码示例
```css
/* 定义默认主题变量 */
:root {
  --theme-color: #333;
  --theme-background-color: #fff;
}

/* 黑暗主题覆盖变量 */
.dark {
  --theme-color: #fff;
  --theme-background-color: #333;
}

/* 组件样式使用变量 */
.box {
  color: var(--theme-color);
  background-color: var(--theme-background-color);
}
```

```js
// 切换主题示例
function switchTheme(isDark) {
  if (isDark) {
    document.documentElement.classList.add('dark');
  } else {
    document.documentElement.classList.remove('dark');
  }
}
```

#### 优点
- 性能好，浏览器原生支持CSS变量，切换流畅无闪烁。
- 代码结构清晰，样式与逻辑分离。
- 兼容主流浏览器，易于维护。
- 支持系统偏好色彩自动切换（`prefers-color-scheme`媒体查询）。

#### 缺点
- 需要预先定义好所有主题变量，主题扩展灵活度有限。
- 纯CSS变量方案对复杂样式逻辑支持有限。

---

### 2. 基于CSS-in-JS（如styled-components、emotion）的主题切换

#### 实现原理
- 使用CSS-in-JS库将样式写在JavaScript中，样式可以根据React组件的props动态变化。
- 通过库提供的`ThemeProvider`组件，将主题对象（包含颜色、字体等变量）传递给子组件。
- 组件内样式通过props访问当前主题变量，实现样式动态切换。
- 切换主题时，更新传给`ThemeProvider`的主题对象，触发组件重渲染，样式自动更新。

#### 代码示例（emotion）
```jsx
import { ThemeProvider } from '@emotion/react';

const lightTheme = {
  color: '#333',
  backgroundColor: '#fff',
};

const darkTheme = {
  color: '#fff',
  backgroundColor: '#333',
};

const Box = styled.div`
  color: ${props => props.theme.color};
  background-color: ${props => props.theme.backgroundColor};
`;

function App() {
  const [theme, setTheme] = React.useState(lightTheme);

  return (
    <ThemeProvider theme={theme}>
      <Box>内容</Box>
      <button onClick={() => setTheme(theme === lightTheme ? darkTheme : lightTheme)}>
        切换主题
      </button>
    </ThemeProvider>
  );
}
```

#### 优点
- 样式与组件逻辑高度耦合，方便动态控制复杂样式。
- 主题对象灵活，支持任意复杂的样式配置。
- 支持条件样式、响应式设计等高级特性。
- 生态丰富，社区支持好。

#### 缺点
- 运行时生成样式，可能带来一定性能开销。
- 依赖第三方库，增加项目体积。
- 需要学习和维护CSS-in-JS写法。

---

## 3. React中结合Ant Design的主题切换

- Ant Design 5.x版本弃用Less，改用CSS-in-JS方案，推荐使用`ConfigProvider`的`theme`属性动态切换主题（默认主题、暗色主题、紧凑主题）。
- 通过修改`ConfigProvider`的`theme.algorithm`属性为`theme.defaultAlgorithm`或`theme.darkAlgorithm`实现主题切换，代码简洁且性能优良。
- 示例：
```jsx
import { ConfigProvider, theme } from 'antd';
const [isDark, setIsDark] = React.useState(false);

<ConfigProvider theme={{ algorithm: isDark ? theme.darkAlgorithm : theme.defaultAlgorithm }}>
  {/* 你的应用 */}
</ConfigProvider>
```

---

## 4. 总结对比

| 方案               | 优点                               | 缺点                             | 适用场景                         |
|--------------------|----------------------------------|--------------------------------|--------------------------------|
| CSS变量切换         | 性能好，原生支持，简单易维护       | 主题变量需预定义，灵活性有限     | 轻量项目、需要系统色彩适配       |
| CSS-in-JS切换       | 灵活，样式与逻辑耦合，支持复杂样式 | 运行时开销，依赖库               | 复杂UI、需要动态样式和响应式设计 |
| Antd 5.x ConfigProvider | 简洁，官方支持，性能优             | 仅限Antd生态                    | 使用Antd组件库的中大型项目       |

---

## 5. 参考资料与实践建议

- 推荐先用CSS变量方案快速实现基础主题切换，满足大部分需求。
- 需要更灵活复杂的样式控制时，采用CSS-in-JS方案（emotion或styled-components）。
- 使用Ant Design时，优先考虑`ConfigProvider`的主题切换API，兼顾性能与体验。
- 可结合`prefers-color-scheme`自动适配系统主题，提升用户体验。
- 参考开源项目和文章：
  - 稀土掘金React主题切换方案分享[1]
  - Antd 5.x主题切换实战[4]
  - Emotion深色主题实现[3]
  - CSS Theme Change轻量库[7]

---

通过以上方案解析，你可以根据项目需求和技术栈选择合适的React主题切换实现方式，提升应用的用户体验和视觉一致性。需要示例代码或具体实现细节也可以继续交流。

## 参考资料

:::details 点击展开全部参考链接
| 序号 | 标题 | 链接 |
|:---:|:-----------------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| 1   | React 主题切换（方案分享 ） - 稀土掘金 | [查看](https://juejin.cn/post/7302624942046429224) |
| 2   | YvonneZh128/SwitchTheme: react结合antD，实现线上环境切换主题 | [查看](https://github.com/YvonneZh128/SwitchTheme) |
| 3   | 4-6 使用emotion 實作深色主題 | [查看](https://pjchender.github.io/react-bootcamp/docs/book/ch4/4-6) |
| 4   | react + antd实现动态切换主题功能（适用于antd5.x版本） 原创 | [查看](https://blog.csdn.net/m0_58016522/article/details/131168634) |
| 5   | 前端通用主题切换(React) 原创 - CSDN博客 | [查看](https://blog.csdn.net/GXSmile/article/details/137380205) |
| 6   | Styled-Components 丝滑实现React 主题切换 - 稀土掘金 | [查看](https://juejin.cn/post/7102406632692252679) |
| 7   | 探索优雅的CSS主题切换- CSS Theme Change - CSDN博客 | [查看](https://blog.csdn.net/gitblog_00061/article/details/138894091) |
| 8   | 前端多主题实现及切换方案 - ShyMean | [查看](https://www.shymean.com/article/%E5%89%8D%E7%AB%AF%E5%A4%9A%E4%B8%BB%E9%A2%98%E5%AE%9E%E7%8E%B0%E5%8F%8A%E5%88%87%E6%8D%A2%E6%96%B9%E6%A1%88) |
| 9   | React使用css变量动态改变主题 - 稀土掘金 | [查看](https://juejin.cn/post/7162119559145750564) |
| 10  | 前端主题切换策略 - 稀土掘金 | [查看](https://juejin.cn/post/7327825616773464064) |
| 11  | 如何在React中使用CSS变量实现主题切换 - 亿速云 | [查看](https://www.yisu.com/zixun/842977.html) |
| 12  | emotion/css + react+动态主题切换原创 - CSDN博客 | [查看](https://blog.csdn.net/m0_56590688/article/details/146577628) |
| 13  | （简单有案例）前端实现主题切换、动态换肤的两种简单方式原创 | [查看](https://blog.csdn.net/qq_59747594/article/details/136079700) |
| 14  | 『Ant Design』主题定制-腾讯云开发者社区 | [查看](https://cloud.tencent.com/developer/article/2384239) |
| 15  | 使用CSS 变量- Ant Design | [查看](https://ant.design/docs/react/css-variables-cn/) |
| 16  | Css方案之主题切换功能设计#27 - GitHub | [查看](https://github.com/lio-mengxiang/mx-design/issues/27) |
| 17  | 使用styled-components控制主题切换(有手就行) 原创 - CSDN博客 | [查看](https://blog.csdn.net/Dongfang_project/article/details/129955559) |
| 18  | React + Antd实现动态切换主题功能之二（默认主题与暗黑色主题切换 ... | [查看](https://blog.csdn.net/m0_58016522/article/details/122067153) |
| 19  | 动态主题（实验性） - Ant Design | [查看](https://4x.ant.design/docs/react/customize-theme-variable-cn) |
| 20  | 个人实践几种React在线主题切换方案#36 - GitHub | [查看](https://github.com/DaodaoW/huluntuntao/issues/36) |
:::
