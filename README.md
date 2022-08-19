# docs.giveth.io
[![Action Status](https://github.com/giveth/giveth-docs/workflows/deploy-docs/badge.svg)](https://github.com/giveth/giveth-docs/actions)

访问 [Giveth 文档](https://docs.giveth.io/)

*这个网站是用[Docusaurus 2](https://v2.docusaurus.io/)建立的，一个现代的静态网站生成器。*

---


## Installation

```console
yarn
```

## Local Development

```console
yarn start
```

这个命令启动一个本地开发服务器并打开一个浏览器窗口。大多数更改都可以在不重启服务器的情况下实时反映。

## Translations

当您开始运行并想要翻译时，请查看 docusaurus.io 中关于 i18n 的文档。使用您所贡献的语言的适当文件夹，并注意在您的语言中运行应用程序是非常重要的，因为每个翻译都会生成它自己的 Single page 应用程序。

`yarn start --locale es` (这是在本地运行西班牙语版本的示例)

## Build

```console
yarn run build
```

这个命令生成静态内容到 “build” 目录中，可以使用任何静态内容托管服务。

## Deployment

```console
GIT_USER=<Your GitHub username> USE_SSH=true npm run deploy
```

如果您使用 GitHub 页面进行托管，则此命令是构建网站并推送到“gh pages”分支的一种便捷方法。
