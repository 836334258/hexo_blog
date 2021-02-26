---
title: 配置免费的https
date: 2021-02-26 19:28:19
tags:
---

```shell
#安装软件
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:certbot/certbot
sudo apt-get update
sudo apt-get install -y python-certbot-nginx

#申请证书
certbot --nginx -d www.jinhaitao.com -n --email help@fundebug.com --agree-tos

#certbot 会自动修改 nginx 配置文件：
```