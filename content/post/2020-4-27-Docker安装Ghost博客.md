---
title: Docker 安装 Ghost 博客指南
subtitle: Docker 安装 Ghost 博客指南
date: 2020-4-27
tags: ["docker", "ghost","博客"]
---
# Docker 安装 Ghost 博客指南

 ## 1、安装

### Docker 安装

```shell
# Docker 快速安装

curl -sSL https://get.daocloud.io/docker | sh
# docker-compose 安装

curl -L https://get.daocloud.io/docker/compose/releases/download/1.25.5/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose

```

### Ghost 安装

```shell

docker run -d --name some-ghost -p 3001:2368 -v /path/to/ghost/blog:/var/lib/ghost/content ghost

# 后台地址为 http://localhost:3001/ghost
```

推荐主题 ：liebling

Ghost 没有中文，翻译起来也有点麻烦，不折腾了