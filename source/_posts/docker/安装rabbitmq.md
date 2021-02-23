---
title: 安装rabbitmq
---

```bash
docker run --name rabbitmq -d  -p 5672:5672 -p 15672:15672  --restart=always rabbitmq:3.8.2-management-alpine
```

