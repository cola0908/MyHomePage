# cola0908 / MyHomePage

本项目分支于 [SimonAKing/HomePage](https://github.com/SimonAKing/HomePage.git)，是基于该项目定制开发的cola0908的个人主页。


## Introduction

> 一款现代优雅的个人主页，拥有流体动画背景、响应式设计与丝滑的页面切换效果。

想给自己的网站也装上这样一个超酷的个人主页吗？
现在就开始吧！

## Install

```sh
git clone https://github.com/cola0908/MyHomePage.git
cd HomePage
npm install
npm run dev
```

## Features

1. 页面内所有信息高度封装，易于配置修改
2. 采用 [WebGL-Fluid-Simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/) 实现流体动画背景
3. 使用 `less` 作为 `css` 预处理器
4. 使用 `pug` 作为 `html` 预处理器
5. 使用 `gulp` 作为构建工具并完成构建脚本配置
6. 舒适的动画效果与精美的UI设计
7. 响应式布局，完美适配移动端
8. 页面引用的 `css` 与 `js` 文件总大小不超过 `18.5` kb！
9. 页面切换事件做了延迟响应优化
10. 更多特性等你来探索...

## Structure

根据项目特性，整体分为两大模块：
1. `intro` 首屏模块
2. `main` 次屏模块

项目对应的功能、样式与配置均基于此标准划分。

## Basic configuration

`config.json` 配置文件中的每一个键名，均对应页面中相应的组件名称。

示例如下：

```json
{
	"head": {
		"title": "cola0908",
		"description": "Category:Personal Homepage",
		"favicon": "favicon.ico"
	}
}
```

上述配置信息，对应 `layout/head.pug` 组件中的如下内容：
```pug
head
	title #{head.title}
	meta(charset="utf-8")
	meta(name="Description" content=`${head.description}`)
	link(rel="icon" href=`${head.favicon}` type="image/x-icon")
```

## Advanced configuration

### WebGL-Fluid-Simulation

首页默认使用 [WebGL-Fluid-Simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/) 作为流体动画背景。

如需关闭该效果，将配置项 `intro.background` 设置为 `false` 即可。

### supportAuthor

配置项中的 `supportAuthor` 选项默认开启，即对原作者进行支持。
开启后包含以下内容：
1. 首页右上角将显示「章鱼猫」标识
2. 浏览器控制台将打印原作者的站点信息

如需关闭该功能，将配置项 `intro.author` 设置为 `false` 即可。

### Icon replacement

项目中使用的图标，均来自 [阿里巴巴矢量图标库](https://www.iconfont.cn)。

图标替换步骤如下：
1. 选择需要的图标，添加至项目中，并将图标颜色修改为白色
2. 选择 Font Class 方式生成代码
3. 复制生成的链接内的全部内容
4. 替换项目中 `/src/css/common/icon.less` 文件的对应内容，注意必须保留 `icon` 选择器的原有内容
5. 在 `config.json` 配置文件中，修改 `main.ul. * .icon` 对应的图标名称

```css
.icon {
	display: block;
	width: 1.5em;
	height: 1.5em;
	margin: 0 auto;
	fill: currentColor;
	font-family: 'iconfont' !important;
	font-size: inherit;
	font-style: normal;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}
```

## Deployment

在项目根目录执行 `npm run build` 命令后，项目构建产物将生成至 `dist` 目录。

你可以将 dist 目录部署至任意你使用的服务器托管服务商。

以下是 `GithubPage` 部署示例：

1. 创建名为 `userName.github.io` 的仓库
2. 执行以下命令：
   ```sh
   cd dist
   git init
   git add -A
   git commit -am"init"
   git remote add origin https://github.com/userName/userName.github.io.git
   git push -f origin master
   ```
3. 在 GitHub 中配置该仓库的 Github Page 相关选项
4. 访问 `username.github.io` 即可查看你的个人主页！

如果你的 `username.github.io` 仓库已有内容，可以新建一个其他名称的仓库（例如 `blog`），将原有内容迁移至该仓库中，并为其配置 Github Page 选项，该仓库将成为 `username.github.io/blog` 子目录，这样 `username.github.io` 仓库就可以用来部署这个个人主页了。

## Sponsor

本项目基于 SimonAKing 开源的 HomePage 项目二次开发，原作者为项目开发投入了大量的时间与精力。如果本项目对你有帮助，欢迎前往 [原项目仓库](https://github.com/SimonAKing/HomePage) 给原作者点亮 `star` 与赞助支持。

感谢你的支持！
