---
title: 创建mysql
---

```bash
docker run --name mysql81 -v D:\docker_file\mysql\mysql81\conf:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=123456 -d --restart=always -p 3309:3306  -v D:\docker_file\mysql\mysql81\data:/var/lib/mysql  mysql
```

