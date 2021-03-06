# webpack4 + ejs + express 服务端渲染多页应用项目架构

#### 介绍

webpack4 + ejs + express 服务端渲染多页应用项目架构

#### 软件架构

1. 打包工具：`webpack 4.16.5`
2. 模板语言：`ejs 2.6.1`
3. 服务端框架：`express 4.16.4`

#### 使用说明

1. 安装依赖：`npm install`
2. 开发环境：`npm run dev` 浏览器访问 `http://localhost:8888`
3. 打包构建：`npm run build`
4. 生产环境：`npm run server`
5. 一键部署：`npm run deploy`

#### 功能介绍：
1. 基于 `ejs` 模板语言开发，支持服务端渲染。
2. 开发环境一键启动本地服务和 `webpack` 编译，同步监听服务端和客户端代码。支持内存读取资源，不生成额外目录，快捷方便。
3. 全面支持热更新，监听所有文件修改，实时渲染，实时响应，无需刷新。
4. 编译报错机制完善，集成 `overlay` webpack 原生报错插件。

#### 适用场景
1. 适用于强依赖 SEO 的项目，比如公司官网。
2. 适用于以 `node` 做为服务端 / 中间层服务的项目架构，前后端分离式开发，由前端提供统一的数据组装和模板渲染。

#### 关于热更新

目前项目已全面支持热更新（`js/css/less/ejs` 文件修改均可热替换），关于热更新，有几点需要注意：
1. 开发环境下，不要使用 `extract-text-webpack-plugin` 来做样式文件的抽离，否则 `webpack` 无法监听样式文件变化，样式热加载就不会生效。
2. `webpack` 原生没有提供视图文件的热更新支持，原因是视图文件不是通过 `require/import` 方式引入的，webpack 无法监听其变化，这边我提供了一个扩展方式来支持视图热更新，具体实现可以看代码。

#### 改造使用

1. 如果使用别的模板文件，例如 `jade`，可能需要将 `ejs` 的相关 `loader` 替换为对应模板文件的 `loader`，其他代码基本相同，无需改动。
2. 如果不需要使用模板文件，只需将项目中的 `.ejs` 后缀改成 `.html` 即可，这些文件涉及 webpack 构建文件和服务端文件，如果使用了 `.html` 格式的静态文件，那么和后端的数据交互就只能通过 `ajax` 了。

#### 参与贡献

喜欢的话给个 Star，多谢多谢 😃😃，如果有问题提到 issue 里我来修复~

#### 相关细节以及更多注意事项
[掘金传送门](https://juejin.im/post/5cb1aabdf265da037b6101d3)

