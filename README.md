# weapp-runtime
实验性质的小程序web运行时

## 简介
传统解决方案中, 小程序相关的跨端解决方案主要有两种模式
- 将web代码运行在小程序上, 低成本的比如webview, 高级的比如kbone
- 将web代码编译成小程序原生, 比如taro

webview调用原生方法比较困难, 只能使用cover-view实现组件覆盖

kbone的性能和体积都是个问题, 复杂度比较高

taro之类的性能比较好, 但是编译出来的小程序体积巨大, 项目大了以后很难优化, 对小程序原生接口的适配也不够及时, 跨大版本升级非常痛苦

以上几种方式比较适合现有大量的web页面的情况下来降低开发成本, 或者考虑的更多是跨平台

针对我们现有的业务场景, 更加在意小程序侧的性能以及用户体验, 大部分的页面都是从0开始, 小程序作为web子集, 到web端的适配也会更容易

## 解决什么问题
在浏览器中运行小程序的页面, 在保证web/小程序都能获得原生体验的同时无需投入太多额外开发成本

期望能用 1.1的成本解决1+1的问题

本项目适合: 
- 新项目 或者愿意接受从小程序开始开发的成本
- 或者: 已有小程序, 想低成本提供一些web页面
- [暂时]没有太多复杂的web需求, 比如动画, 对dom的操作(需要写额外的代码来支持)

## Roadmap
- [ ] `技术验证` 将小程序页面在浏览器中跑起来
  - [ ] 页面级渲染
  - [ ] 组件化支持
  - [ ] 原生api降级
  - [ ] 基本的样式支持
  - [ ] 小程序自带组件样式
- [ ] `生产环境可用` 提供完善的页面级解决方案 
  - [ ] 组件替代方案
  - [ ] 组件异步加载解决方案
  - [ ] 样式隔离
  - [ ] cli工具
  - [ ] 代码维护的最佳实践
- [ ] `进一步` 完善的解决方案
  - [ ] 响应式支持
  - [ ] 路由支持以实现整个小程序的渲染 
  - [ ] 预编译
  - [ ] SSR支持
- [ ] 更多适配器
  - [ ] 百度小程序
  - [ ] 支付宝小程序
  - [ ] 小程序互相编译解决方案

## License
基于[AGPL-3.0](/blob/main/LICENSE)分发

例外情况: 
  - 使用了本项目源码作为自有服务

你可以使用本项目开发/基于本项目提供自有服务, 但是如果在此基础上二次开发/包装后直接作为商业服务, 则需要开源/取得商业授权
