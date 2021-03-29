---
title: mysql主从复制
date: 2021-03-20 11:06:42
tags:
---

#### mysqld master conf
```editorconfig
log-bin=mysql-bin
#binlog_format=mixed
server-id=1
#innodb_file_per_table=on
#skip_name_resolve=on
replicate-do-db=test1
replicate-do-db=test2
```

#### mysqld slave conf
```editorconfig
server-id=2
log-bin=mysql-bin
binlog-format=mixed
replicate-do-db=test1
replicate-do-db=test2
```

```sql
# slave命令
change master to master_host='172.16.86.4',master_user='root',master_password='',master_log_file='mysql-bin.000007',master_log_pos=156;
START SLAVE;
SHOW SLAVE STATUS\G


# master命令
create user 'slave1'@'172.16.86.5' identified with mysql_native_password by 'slave1';
grant replication slave on *.* to 'slave1'@'172.16.86.5';
```

