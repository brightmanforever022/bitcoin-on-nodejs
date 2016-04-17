# Nodejs开发加密货币

**注**: 永久免费访问地址已经更新为: <http://bitcoin-on-nodejs.ebookchain.org>，收藏 <http://book.btcnodejs.com> 的小伙伴，可以更新一下。


## 关于

本书可以作为Nodejs开发加密货币的入门书籍，也可以作为Ebookchain书链（及以Crypti为核心的应用）的官方开发文档。

本书分享的源码是Ebookcoin（博客币），是Ebookchain(书链)的强大动力。与Lisk一样（成功众筹500多万美元），都是Crypti（已经不再维护）的一个独立分支，类似于以太坊具有侧链功能，可以承载多种去中心化的应用。因此，**无论您是研究Crypti、Lisk，还是Ebookcoin，或者学习Nodejs前后端开发技术，本书都值得参考。**

Ebookchain(书链)的目标是打造人人可用的去中心化软件，以加密货币为驱动，促进人类知识分享。与其他竞争币不同，我们以提供落地可用的软件为核心，力争成为人类第一个“零门槛”的加密货币产品。

本书写作，也是书链的最佳实践，从写到发布，简单、快捷。文章暂时在[github][]上免费发布，永久免费访问地址: <http://bitcoin-on-nodejs.ebookchain.org>

## 日志

- [x] 发布第12篇：Ember深“坑”浅出 2016-04-17 <当前>
- [x] 发布第11篇：一张图学会使用Async组件进行异步流程控制 2016-03-26
- [x] 发布第10篇 2016-03-17
- [x] 发布第9篇 2016-03-10
- [x] 完成1-8篇

## 使用

目录由命令行工具 [gitbook-summary][] 自动生成。自由写作、发布，搭建自出版平台的方法，请[点击这里][self-publishing]

简要介绍如下：

(1)克隆源文

```
$ git clone https://github.com/imfly/bitcoin-on-nodejs.git
```

(2)安装gitbook

```
$ npm install -g gitbook-cli
```

(3)安装依赖包

```
cd bitcoin-on-nodejs
npm install
gitbook install
```

(4)写作构建

写作，并开启服务（构建）

```
$ gitbook serve
```

通过`http://localhost:4000`实时浏览

(5)生成目录

只要修改了文章标题和文件夹，就应该重新生成目录文件

```
$ npm run summary
```

(6)一键发布

```
$ npm run deploy
```

以后，只要4-6的过程就是了。

## 反馈

随时告诉我您的阅读体验和问题，也可以直接fork修改，提交PR。

## 协议

原创作品许可 [署名-非商业性使用-禁止演绎 3.0 未本地化版本 (CC BY-NC-ND 3.0)](http://creativecommons.org/licenses/by-nc-nd/3.0/deed.zh)

版权被书链自动加密、保护、验证和追踪。

## 作者

微信：kubying

Ebookchain官方开发交流QQ群：185046161

[github]: https://github.com/imfly/bitcoin-on-nodejs
[巴比特论坛]: http://8btc.com/thread-27448-1-1.html
[gitbook-summary]: https://github.com/imfly/gitbook-summary
[self-publishing]: https://github.com/imfly/how-to-create-self-publishing-platform
