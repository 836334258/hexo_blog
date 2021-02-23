---
title: 创建php
---

## 创建三个文件夹

![1573385154293](C:\Users\83633\Desktop\工作文档\images\1573385154293.png)

## nginx 配置文件

```nginx
server {
    listen       80;
    server_name  localhost;

    location / {
        root   /usr/share/nginx/html;
        index  index.html index.htm index.php;
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   /usr/share/nginx/html;
    }

    location ~ \.php$ {
        fastcgi_pass   php:9000;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME  /www/$fastcgi_script_name;
        include        fastcgi_params;
    }
}
```



## docker命令

```dockerfile
docker run --name php -v D:\dockerFile\nginx\www:/www -d phpdockerio/php73-fpm
docker run --name nginx -p 8000:80 -v D:\dockerFile\nginx\www:/usr/share/nginx/html -v D:\dockerFile\nginx\conf:/etc/nginx/conf.d --link php nginx
```

