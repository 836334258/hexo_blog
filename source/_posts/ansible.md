---
title: ansible
date: 2021-03-20 10:21:06
tags:
---

### 免密登录
```shell
#生成秘钥对
ssh-keygen -t rsa -f /root/.ssh/id_rsa -N ''
#发送到要同步的服务器
ssh-copy-id 172.16.86.4
#安装mysql
ansible server -m apt -a "name=mysql-server"
重启服务
ansible server -m service -a "name=mysql state=restarted"
```