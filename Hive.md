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
   FIELDS TERMINATED BY '\001'
   COLLECTION ITEMS TERMINATED BY '\002'
   MAP KEYS TERMINATED BY '\003'
 STORED AS TEXTFILE;

```

