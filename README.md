# 科技企业官网 - Svelte 响应式企业网站模板

![科技企业官网](https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80)

这是一个基于 Svelte 和 Vite 构建的现代化响应式企业官网模板，适合科技公司、创业团队和各类企业使用。该模板采用了现代化的设计风格，完全响应式布局，确保在各种设备上都能提供出色的用户体验。

## 🌟 特性

- **现代化设计**：简洁优雅的界面设计，符合当代企业形象需求
- **完全响应式**：自适应各种屏幕尺寸，从手机到桌面设备均有良好表现
- **组件化架构**：基于 Svelte 组件化开发，代码结构清晰，易于维护和扩展
- **性能优化**：使用 Vite 构建工具，确保快速加载和流畅体验
- **交互动效**：适当的动画和交互效果，提升用户体验
- **易于定制**：模块化设计，可根据企业需求轻松定制内容和样式

## 📋 页面组成

- **首页**：包含醒目的标语和企业简介
- **关于我们**：展示企业历史、团队和核心价值观
- **服务**：展示企业提供的主要服务和解决方案
- **案例展示**：展示企业成功案例，可按类别筛选
- **联系我们**：包含联系表单和企业联系信息

## 🚀 快速开始

### 环境要求

- Node.js 16.0 或更高版本
- npm 或 yarn 包管理器

### 安装依赖

```bash
# 使用 npm
npm install

# 或使用 yarn
yarn
```

### 开发模式

```bash
# 使用 npm
npm run dev

# 或使用 yarn
yarn dev
```

访问 `http://localhost:5173` 查看网站。

### 构建生产版本

```bash
# 使用 npm
npm run build

# 或使用 yarn
yarn build
```

### 预览生产版本

```bash
# 使用 npm
npm run preview

# 或使用 yarn
yarn preview
```

## 📁 项目结构

```
src/
├── assets/         # 静态资源文件
├── components/     # 组件文件
│   ├── layout/     # 布局组件（导航栏、页脚等）
│   ├── home/       # 首页相关组件
│   ├── about/      # 关于我们相关组件
│   ├── services/   # 服务相关组件
│   └── contact/    # 联系我们相关组件
├── App.svelte      # 主应用组件
├── main.ts         # 应用入口文件
└── app.css         # 全局样式
```

## 🎨 自定义指南

### 修改内容

1. 编辑各组件文件中的文本内容和图片链接，替换为您的企业信息
2. 可以在 `src/components/home/Services.svelte` 中修改服务项目
3. 在 `src/components/home/Portfolio.svelte` 中更新案例展示内容
4. 在 `src/components/home/About.svelte` 中更新团队信息和公司介绍

### 修改样式

1. 全局样式在 `src/app.css` 中定义
2. 各组件的样式在其 `.svelte` 文件的 `<style>` 标签中定义
3. 主题颜色可以通过修改 CSS 变量或直接修改各组件的样式来更改

## 📱 响应式设计

该模板采用移动优先的响应式设计原则，通过媒体查询在不同屏幕尺寸下提供最佳布局：

- **移动设备**：单列布局，优化触摸交互
- **平板设备**：双列或混合布局，平衡内容密度和可读性
- **桌面设备**：多列布局，充分利用大屏空间展示内容

## 🔧 技术栈

- [Svelte](https://svelte.dev/) - 前端框架
- [Vite](https://vitejs.dev/) - 构建工具
- [TypeScript](https://www.typescriptlang.org/) - 类型检查

## 📄 许可证

MIT

# Svelte + TS + Vite

This template should help get you started developing with Svelte and TypeScript in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Svelte](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

## Need an official Svelte framework?

Check out [SvelteKit](https://github.com/sveltejs/kit#readme), which is also powered by Vite. Deploy anywhere with its serverless-first approach and adapt to various platforms, with out of the box support for TypeScript, SCSS, and Less, and easily-added support for mdsvex, GraphQL, PostCSS, Tailwind CSS, and more.

## Technical considerations

**Why use this over SvelteKit?**

- It brings its own routing solution which might not be preferable for some users.
- It is first and foremost a framework that just happens to use Vite under the hood, not a Vite app.

This template contains as little as possible to get started with Vite + TypeScript + Svelte, while taking into account the developer experience with regards to HMR and intellisense. It demonstrates capabilities on par with the other `create-vite` templates and is a good starting point for beginners dipping their toes into a Vite + Svelte project.

Should you later need the extended capabilities and extensibility provided by SvelteKit, the template has been structured similarly to SvelteKit so that it is easy to migrate.

**Why `global.d.ts` instead of `compilerOptions.types` inside `jsconfig.json` or `tsconfig.json`?**

Setting `compilerOptions.types` shuts out all other types not explicitly listed in the configuration. Using triple-slash references keeps the default TypeScript setting of accepting type information from the entire workspace, while also adding `svelte` and `vite/client` type information.

**Why include `.vscode/extensions.json`?**

Other templates indirectly recommend extensions via the README, but this file allows VS Code to prompt the user to install the recommended extension upon opening the project.

**Why enable `allowJs` in the TS template?**

While `allowJs: false` would indeed prevent the use of `.js` files in the project, it does not prevent the use of JavaScript syntax in `.svelte` files. In addition, it would force `checkJs: false`, bringing the worst of both worlds: not being able to guarantee the entire codebase is TypeScript, and also having worse typechecking for the existing JavaScript. In addition, there are valid use cases in which a mixed codebase may be relevant.

**Why is HMR not preserving my local component state?**

HMR state preservation comes with a number of gotchas! It has been disabled by default in both `svelte-hmr` and `@sveltejs/vite-plugin-svelte` due to its often surprising behavior. You can read the details [here](https://github.com/rixo/svelte-hmr#svelte-hmr).

If you have state that's important to retain within a component, consider creating an external store which would not be replaced by HMR.

```ts
// store.ts
// An extremely simple external store
import { writable } from 'svelte/store'
export default writable(0)
```
