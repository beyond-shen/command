## 1.本地数据库备份与恢复
##### 1.1 本地docker数据库

- 备份

```
mongodump -d testdb -o testdb
```


- 恢复

```
mongorestore -d testdb --drop testdb
```


##### 1.2 本地meteor运行数据库
meteor运行时，默认在3000端口，可以使用meteor mongo查看数据库

- 备份

```
mongodump -h 127.0.0.1:3001 -d meteor -o testdb
```

- 恢复

```
mongorestore -h 127.0.0.1:81 -d testdb --drop testdb
```

**需要注意，restore的数据库collecton文件夹名和collection名要一直**

## 2.远程数据库备份与恢复
##### 2.1 compose.io数据库

- 备份

```
mongodump -h lighthouse.5.mongolayer.com:10367 -u root -p Password -d testdb -o testdb
```

- 恢复

```
mongorestore --host lighthouse.5.mongolayer.com --port 10367 -u root -p Password -d testdb --drop testdb
```


##### 2.2 aliyun mongo数据库
**注意，阿里云的mongo只能阿里云主机才能连接**

- 备份

```
mongodump -h dds-2ze04b800265f5b42.mongodb.rds.aliyuncs.com:3717 -u maodou -p password -d testdb -o testdb
```

- 恢复

```
mongorestore -h dds-2ze021cc656a02141.mongodb.rds.aliyuncs.com:3717 --authenticationDatabase admin -u root -p password -d testdb --drop testdb
```

## Faq
1. 出现错误
 
```
terminate called after throwing an instance of 'std::runtime_error'
  what():  locale::facet::_S_create_c_locale name not valid
```

解决办法

```
export LC_ALL="C"
```
