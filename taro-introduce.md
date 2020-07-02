---
marp: true
headingDivider: 2
backgroundColor: #32363F
color: #fff
---

## <!-- fit --> Taro

> 多端统一开发解决方案

## 如何开发/维护一个双平台产品(微信小程序&支付宝小程序)

1) 方案一: 开发一套支付宝小程序代码, 然后手动转微信小程序代码; 缺点: 手动转换效率低, 而且后期产品迭代需要保持两套代码的同步更新, 时间一长很容易出现更新不同步

1) 方案二: 开发一套支付宝小程序代码, 然后通过工具转微信小程序代码; 缺点: 每次转换后的代码都会有报错, 仍然需要手动处理, 且转换后的代码可读性可维护性大大降低

2) 方案三(目前最普遍的解决方案): 使用第三方框架开发, 然后通过框架提供的工具转为不同平台的代码, 优点: 开发者只需要维护这一套代码, 效率最高; 缺点: 学习成本稍高

## 市场上这类框架有哪些?

- Taro(京东): https://github.com/NervJS/taro
- uni-app(DCloud): https://github.com/dcloudio/uni-app
- mpvue(美团): https://github.com/Meituan-Dianping/mpvue
- chameleon(滴滴): https://github.com/didi/chameleon
- MPX(滴滴): https://github.com/didi/mpx
- megalo(网易考拉): https://github.com/kaola-fed/megalo

个人推荐: 综合各方面考虑(市场占用率, 社区活跃度, 更新频率, Issues 总量和Closed比例等因素), 比较推荐 Taro 和 uni-app

- Taro: 使用 react 语法
- uni-app: 使用 vue 语法

## Taro 介绍

- Taro 是凹凸实验室(京东)开发的多端统一开发解决方案, 可以实现前端代码一次编写，多平台运行
- 支持哪些平台? 微信小程序, 支付宝小程序, 百度小程序, 字节跳动小程序, QQ 小程序, 京东小程序, 快应用, H5, ReactNative
- 快应用: 9 大安卓手机厂商(华为、小米、OPPO、vivo、中兴、金立、联想、魅族、努比亚)共同推出的一套标准和平台, 可以在这些安卓手机上运行(免安装轻量级安卓APP)
- ReactNative: 将 React 语法转为 APP 原生语法(Android/iOS), 基本上可以认为是原生 APP

## Taro 原理

- 前面提到: Taro 可以让开发者使用 React 语法开发项目, 最终通过 Taro 提供的编译工具将源码编译为: 微信小程序语法, 支付宝小程序语法...

- 编译过程: 将项目源码解析（Parse）成抽象语法树（AST），然后根据不同插件对 AST 进行转换(Transform)（类似 DOM 树的操作），生成（generate）新的AST，根据新的 AST 生成编译后的代码(小程序/H5/ReactNative...)。

## Taro 的优点(为什么用 Taro)

- 降低开发成本: 在不使用 Taro 前如果想开发一个微信小程序一个支付宝小程序, 需要开发维护两套代码, 使用 Taro 后只需要维护一套代码即可

- 支持更多的新语法: ES6, ES7, ES8, TypeScript, React-Hooks
- 丰富的工具/类库可以选择: Less, Sass, Redux
- API 调用更方便, 扩展了更多功能: Taro 使用 Promsie 封装小程序 API, 给ajax 增加了拦截器...
- 封装好的 UI 组件: 官方和第三方开发者提供的大量的组件, 项目中可以直接引入使用, 降低了开发成本
- 良好的技术支持: 遇到技术问题可以去论坛咨询, Github 提 Issues, 官方微信群

## Taro 的缺点

- API支持度不足: 除了微信小程序外, 其他如支付宝小程序 有很多API是不支持的, 可以自己[将相似的API封装成公共方法](https://www.yuque.com/vrr9x6/tve0yz/rpyy2x)

- 平台独有API/配置/组件需要单独处理: 当使用平台独有的API或配置时, 需要单独用条件处理避免报错; 应避免使用小程序官方组件, 如果使用了支付宝官方组件, 那么在打包微信小程序的时候就会报错, 推荐Taro官方组件库
- bug 比原生小程序多: 但是还好, 基本上通过各种渠道都能找到解决办法
- 某些情况Taro性能会略低于原生小程序: [Taro对比原生开发](https://nervjs.github.io/taro/blog/2020-04-27-taro-vs-jd/)

## Taro 项目初始化&打包

![图片名称](https://i.loli.net/2020/07/02/PAtlV1M9TGZgFn8.png)
<!-- ![图片名称](./img/taro-init.png) -->

## Taro 开发注意事项

> 语雀: https://www.yuque.com/vrr9x6/tve0yz/qnyg9d

## 总结(整体感觉)

* 在进行多端开发时, 使用Taro可以提升了开发效率, 降低维护成本: 维护两套代码(微信&小程序)的成本肯定是高于维护一套代码

* 有利于开发者自身的技术提升: 可以使用 ES 新语法, Sass/Less 工具, 可以用 React, TypeScript, 以后再开发 H5 的时候也不会有生疏感

* 个人感觉: 还是比较优秀的一款框架, 需要一定的学习成本

## News 最新消息

- Taro3.0 正式版已于 7 月 1 日发布, 同时支持 React, Vue, jQuery; 
  
- 想用的小伙伴可以先熟悉熟悉, 建议等更新2~3个版本再使用, 大版本迭代肯定会有很多问题

## <!-- fit --> Thank You
