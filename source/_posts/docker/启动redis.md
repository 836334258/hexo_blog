---
title: 启动redis
---

```bash
 docker run --privileged=true -p 6393:6379 -v D:\docker_file\redis\redis3\data:/data -v D:\docker_file\redis\redis3\redis.conf:/etc/redis/redis.conf  --name redis3 -d redis redis-server /etc/redis/redis.conf
```

