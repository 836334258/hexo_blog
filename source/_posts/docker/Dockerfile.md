---
title: dockerfile
---

```dockerfile
FROM mysql
LABEL author king
RUN apt-get update && apt-get install -y vim
RUN mkdir /king
WORKDIR /king
ADD test.txt test.txt
COPY test1.txt test1.txt
EXPOSE 3306
ENV MYSQL_ROOT_PASSWORD 836334258

```

