---
title: php记录
date: 2021-03-13 10:36:53
tags:
---

## 设置session的储存路径为redis
```php
ini_set('session.save_handler','redis');
ini_set('session.save_path','tcp://127.0.0.1:6379');
```

## redis互斥锁
```php
function get($key){
    $val=$redis->get($key);
    if (empty($val)){
        if ($redis->setnx($key_mutex,1,3*60)==1){
            $val=$redis->get($key);
            $redis->set($key,$val,$expire_secs);
            $redis->del($key_mutex);
        }else{
            sleep(1);
            get($key);
        }
        
    }else{
        return $val;
    }
}
```