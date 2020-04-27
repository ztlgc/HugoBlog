---
title: Docker搭建WordPress博客
subtitle: Docker搭建WordPress博客
date: 2020-04-17
categories: ["博客"]
tags: ["docker", "wordpress","博客"]
---
# Docker搭建WordPress博客

## 1、安装

```shell
# 1、镜像下载
docker pull mariadb
docker pull wordpress

# 2、docker 内安装
docker run --name mariadb-db -p 3306:3306 -v /data/mariadb:/var/lib/mariadb -d -e MYSQL_ROOT_PASSWORD=123456 mariadb:latest
docker run -v /data/wordpress/wp-content:/var/www/html/wp-content --name my-wordpress --link mariadb-db:db -p 80:80 -d wordpress

# 3、mariadb 建立一个 wordpress 数据库
# 4、运行
# 5、权限问题
# 在wordpress容器内执行,两个内有一个起作用
chown -R www-data:www-data wp-content/*
chown -R www-data:www-data /var/www/
```

## 2、可能遇到的问题

#### 上传文件超过 php.ini  规定的 upload_max_filesize 最大值

- 如果找不到 php.ini 文件，建议直接新建一个（容器内编辑文件太不方便了）

```shell
vi php.ini
# 添加
upload_max_filesize = 720M
post_max_size = 64M
memory_limit = 1024M
max_execution_time = 180

```

- 将 php.ini 文件移动到该到的目录

``` shell
# 可能是这两个
docker cp ./php.ini 容器ID:/usr/local/php/
docker cp ./php.ini 容器ID:/var/www/html/wp-admin

```

- 弄完之后重启容器才能知道是否成功

``` shell
docker restart 容器ID
```

