---
id: givethioinstallation
title: 安装用于本地开发的 Giveth.io
---

从“@docusaurus/useBaseUrl”导入 useBaseUrl

本指南使用 Ubuntu 20.04 LTS 记录用于开发的本地设置和运行 Giveth.io 的步骤。

**您需要几个前置条件才能开始**

 - [Redis](https://redis.io/topics/quickstart)
 - [Postgres](https://www.postgresql.org/download)
 - Bash CLI
 - [Gatsby CLI](https://www.gatsbyjs.com/docs/reference/gatsby-cli/)
 - 配置 NodeJS
      * [For Linux](https://www.gatsbyjs.com/docs/how-to/local-development/gatsby-on-linux/)
     * [For Windows](https://www.gatsbyjs.com/docs/how-to/local-development/gatsby-on-windows/)
 - 您喜欢的代码编辑器（VScode 用于代码检查预设）

### 从 GitHub 安装 impact-graph
为了进行本地开发，您需要克隆后端服务器。我们使用 https://github.com/Giveth/impact-graph 进行此操作。

- 在命令行界面使用 SSH：
    ```bash
    git clone git@github.com:Giveth/impact-graph.git
    cd impact-graph
    npm i
    cp .env.example .env
    ```


### 在 Postgres 中创建数据库和用户
按照 PSQL 的教程设置用户名并创建数据库。
https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e)

**TL;DR**
```bash
sudo -u postgres psql
postgres=# create database <databaseName>;
postgres=# create user <userName> with encrypted password '<passwordHere>';
postgres=# grant all privileges on database <databaseName> to <userName>;
```
### 克隆并安装前端
  前往 https://github.com/Giveth/giveth-2 并克隆存储库。
  - 在命令行界面：
  ```bash
  git clone git@github.com:Giveth/giveth-2.git
  cd giveth-2
  npm i
  ```

### 获取环境变量
 为了运行 Giveth.io 的本地构建，您需要获取环境变量。请前往我们的 [Contributors Discord](https://discord.giveth.io) 与开发人员联系。

### 启动开发服务器和环境
 启动 `impact-graph` 后端服务器和 Redis。 
  - 使用命令 `redis-server` 启动 Redis
  - 在 impact-graph 存储库中运行 `npm start`

 为了使用代码检查预设，请使用 **VSCODE**:
 * 选择 *File -> Open Workspace*
 * 进入 giveth-2 目录
 * 打开工作区文件 `giveth2-full-stack.code-workspace`
 * 安装推荐的扩展插件（Prettier 和 StandardJS）

 然后启动本地开发服务器。

 ```bash
 gatsby develop
 ```

### 开始编辑！

在代码编辑器中打开 giveth2 存储库。

Giveth.io 现在本地运行在 `http://localhost:8000`!

<img alt='Giveth Running Locally' src={useBaseUrl('img/content/givethlocalresized.png')} />

你还可以通过GraphQL实验查询你的数据 - 在这个链接中可以找到它 - `http://localhost:8000/___graphql`
在 [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/part-five/#introducing-graphiql) 中了解更多关于使用这个工具的信息。

  保存更改，浏览器将实时更新！

**当前构建状态**

[master](https://v2.giveth.io)

[![Netlify Status](https://api.netlify.com/api/v1/badges/f914ac7e-ce27-4909-bd3e-14d749731a52/deploy-status)](https://app.netlify.com/sites/giveth2/deploys)

[staging](https://staging.giveth.io)

[![Netlify Status](https://api.netlify.com/api/v1/badges/2f325b5b-e159-443e-bac7-c5e15f3578c0/deploy-status)](https://app.netlify.com/sites/giveth-website-staging/deploys)
<br />
