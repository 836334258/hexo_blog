---
title: 创建nginx
---

```ba
 docker run --name nginx_slave1 --restart=always -v D:\code\docker\nginx\slave1\www:/usr/share/nginx/html -p 7601:80 -v D:\code\docker\nginx\slave1\conf:/etc/nginx/conf.d -d --link php74 nginx
```



## nginx.conf

```nginx
server {
    listen       80;
    autoindex on;
    server_name  localhost;
    # 解决乱码
    charset utf-8;
    

    location / {
        root   /usr/share/nginx/html;
        index  index.php index.html index.htm;
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   /usr/share/nginx/html;
    }

    location ~ \.php$ {
        root   /usr/share/nginx/html;
        fastcgi_pass   php74:9000;
         fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME  /www/$fastcgi_script_name;
        include        fastcgi_params;
    }
}
```

