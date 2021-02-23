---
title: docker
---

## 创建一个容器

```markdown
docker run -it -v /d/php/hyperf:/hyperf-skeleton -p 9501:9501 --name hyperf-mysql-redis --link mysql --link redis --entrypoint /bin/sh hyperf/hyperf:7.2-alpine-cli
```

## 定义容器的执行体

```dockerfile
 --entrypoint='bash'
```



## [镜像加速器](https://y6789umw.mirror.aliyuncs.com)





## 运行mysql

```dockerfile
docker run --name mysql8 -v D:\docker_test\mysql\conf:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=836334258 -p 3307:3306 -d mysql --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
```



## 添加镜像（linux）

```bash
vim /etc/docker/daemon.json
{
  "registry-mirrors": ["http://hub-mirror.c.163.com"]
}

sudo systemctl daemon-reload 

sudo systemctl restart docker
```

