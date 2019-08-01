## Hive create table


### simple version

```
create table table_name (
  id                int,
  dtDontQuery       string,
  name              string
)

```

### table with partition
```
create table table_name (
  id                int,
  dtDontQuery       string,
  name              string
)
partitioned by (date string)
```

### defalut table 
```
CREATE TABLE page_view(
     viewTime INT, 
     userid BIGINT,
     page_url STRING, 
     referrer_url STRING,
     ip STRING COMMENT 'IP Address of the User')
 COMMENT 'This is the page view table'
 PARTITIONED BY(dt STRING, country STRING)
 ROW FORMAT DELIMITED 
## 关键字，用来设置创建表在加载数据时的列分隔符，
## 不同列之间用一个 '\001' 分割，集合的元素之间用 '\002'，map 重的 key 和 value 用 '\003' 分割。
   FIELDS TERMINATED BY '\001'
   COLLECTION ITEMS TERMINATED BY '\002'
   MAP KEYS TERMINATED BY '\003'
 STORED AS TEXTFILE; ## 关键字是用来设置加载数据的数据类型，默认是 textfile，如果数据是纯文本，就是使用 stored as textfile。

```



