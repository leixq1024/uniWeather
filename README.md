# uni天气预报 项目说明

## 项目简介
本项目基于 uni-app 框架开发，支持多端运行，主要实现天气预报功能。可打包为微信小程序、App等。

## 目录结构说明

```
├── index.html                # 项目入口 HTML 文件
├── package.json              # 项目依赖及脚本配置
├── pnpm-lock.yaml            # pnpm 包管理锁定文件
├── shims-uni.d.ts            # uni-app 类型声明文件
├── tsconfig.json             # TypeScript 配置文件
├── vite.config.ts            # Vite 构建工具配置
├── src/                      # 源码目录
│   ├── App.vue               # 应用主组件
│   ├── env.d.ts              # 环境类型声明
│   ├── main.ts               # 应用入口文件
│   ├── manifest.json         # 项目配置文件（包含多端打包信息）
│   ├── pages.json            # 页面路由及窗口配置
│   ├── shime-uni.d.ts        # uni-app 类型声明文件
│   ├── uni.scss              # 全局样式文件
│   ├── pages/                # 页面文件夹
│   │   └── index/            # 首页页面文件夹
│   │       └── index.vue     # 首页页面组件
│   └── static/               # 静态资源文件夹
│       └── logo.png          # 项目 logo
```

### 主要文件说明
- **index.html**：Web 端入口文件。
- **package.json**：项目依赖、脚本及元信息。
- **vite.config.ts**：Vite 构建配置。
- **src/App.vue**：应用主组件，控制全局布局。
- **src/main.ts**：应用入口，初始化 Vue 实例。
- **src/manifest.json**：项目配置，包含打包、权限、平台信息。
- **src/pages.json**：页面路由及窗口配置。
- **src/pages/index/index.vue**：首页页面组件。
- **src/static/**：存放静态资源，如图片等。
- **src/uni.scss**：全局样式文件。

## 微信小程序运行与打包

### 1. 运行到微信小程序
1. 在命令行执行：
   ```
   pnpm install
   pnpm run dev:mp-weixin
   ```
2. 构建完成后，会在 `dist/dev/mp-weixin` 目录生成微信小程序代码。

### 2. 在微信开发者工具中预览
1. 打开微信开发者工具。
2. 选择“导入项目”，目录选择 `dist/dev/mp-weixin`。
3. 填写 AppID（可用测试号），导入后即可预览和调试。

### 3. 打包发布
1. 在命令行执行：
   ```
   pnpm run build:mp-weixin
   ```
2. 构建完成后，会在 `dist/build/mp-weixin` 目录生成用于发布的小程序代码。
3. 在微信开发者工具中上传代码，提交审核并发布。

## 其他说明
- 项目基于 Vue3 + TypeScript + uni-app，支持多端开发。
- 如需打包 App，可参考 `src/manifest.json` 配置。
- 详细开发文档可参考 [uni-app 官方文档](https://uniapp.dcloud.io/).
