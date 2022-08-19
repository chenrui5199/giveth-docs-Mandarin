---
id: givethioinstallation
title: 安装用于本地开发的 Giveth.io
---

从“@docusaurus/useBaseUrl”导入 useBaseUrl

本指南使用 Ubuntu 20.04 LTS 记录用于开发的本地设置和运行 Giveth.io 的步骤。

**您需要几个先决条件才能开始。**

 - [Redis](https://redis.io/topics/quickstart)
 - [Postgres](https://www.postgresql.org/download)
 - Bash CLI
 - [Gatsby CLI](https://www.gatsbyjs.com/docs/reference/gatsby-cli/)
 - Configure NodeJS
      * [For Linux](https://www.gatsbyjs.com/docs/how-to/local-development/gatsby-on-linux/)
     * [For Windows](https://www.gatsbyjs.com/docs/how-to/local-development/gatsby-on-windows/)
 - Your Favourite Code Editor (VScode for linting presets)

### Install impact-graph from GitHub
In order to develop locally you need to clone the backend server as well. We are using https://github.com/Giveth/impact-graph for this.

- via SSH on the CLI:
    ```bash
    git clone git@github.com:Giveth/impact-graph.git
    cd impact-graph
    npm i
    cp .env.example .env
    ```


### Create a Database and User in Postgres using psql
Follow this tutorial on PSQL to setup your username and create the database.
https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e)

**TL;DR**
```bash
sudo -u postgres psql
postgres=# create database <databaseName>;
postgres=# create user <userName> with encrypted password '<passwordHere>';
postgres=# grant all privileges on database <databaseName> to <userName>;
```
### Clone and Install the Frontend
  Head on over to https://github.com/Giveth/giveth-2 and clone the repo.
  - via the CLI:
  ```bash
  git clone git@github.com:Giveth/giveth-2.git
  cd giveth-2
  npm i
  ```

### Get the Environment Variables
 In order to run the local build for Giveth.io you'll need to ask for the environment variables. Head on over to our [Contributors Discord](https://discord.giveth.io) say Hi and get in touch with one of the developers.

### Launch the Development Server and Environment
 Start up the `impact-graph` backend server and redis.
  - Run redis by using the command `redis-server`
  - From the impact-graph repo start with `npm start`

 To take advantage of linting presets, please use **VSCODE**:
 * Select *File -> Open Workspace*
 * Navigate into the giveth-2 directory
 * Open the workspace file `giveth2-full-stack.code-workspace`
 * Install recommended extensions (Prettier and StandardJS plugins)

 Then fire up the local development server.

 ```bash
 gatsby develop
 ```

### Start Editing!

Open up the giveth2 repo on your code editor.

Giveth.io is now running locally at `http://localhost:8000`!

<img alt='Giveth Running Locally' src={useBaseUrl('img/content/givethlocalresized.png')} />

You can also expiremnt with querying your data via GraphQL - you'll find it at this link here - `http://localhost:8000/___graphql`
Learn more about using this tool in the [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/part-five/#introducing-graphiql).

  Save your changes and the browser will update in real time!

**Current Build Statuses**

[master](https://v2.giveth.io)

[![Netlify Status](https://api.netlify.com/api/v1/badges/f914ac7e-ce27-4909-bd3e-14d749731a52/deploy-status)](https://app.netlify.com/sites/giveth2/deploys)

[staging](https://staging.giveth.io)

[![Netlify Status](https://api.netlify.com/api/v1/badges/2f325b5b-e159-443e-bac7-c5e15f3578c0/deploy-status)](https://app.netlify.com/sites/giveth-website-staging/deploys)
<br />
