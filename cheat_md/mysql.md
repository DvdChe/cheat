# Mysql Cheat :


# ----------Tunning Mysql--------------
## Get Buffer size
```mysql
SELECT @@innodb_buffer_pool_size/1024/1024/1024;
```
## Set Buffer size : 
```bash
mysqld --innodb_buffer_pool_size=9G --innodb_buffer_pool_instances=16
```
##Show Running queries :
```mysql
mysql> show processlist;
```

##Check locked tables :
```mysql
mysql> show open tables where in_use >0;
```

##Check max_connection_error  :
```mysql
mysql> select @@global.max_connect_errors;
mysql> show variables like "max_connections";
mysql> show global status like '%max_connection%';
mysql> flush status;
```
## Get mysql activity in real time :
```
mysqladmin ext -ri <time in seconds>
```

Max connection = apache max client x 2

# -----------User management----------
## New User :
```mysql
CREATE USER '<user>'@'<host>' IDENTIFIED BY '<password>';
GRANT ALL PRIVILEGES ON <database> .<table> TO '<user>'@'<host>';
```

##Show grants for user :
```mysql
mysql> show grants for '<user>'@'<host>';
```

# -----------Logs management --------
##Show binary logs :
```mysql
mysql> show binary logs;
```

##Purge binary logs :
```mysql
mysql> purge binary logs to 'mysql-bin.xxxxxx';
```

# -----------Slave management ----------
##Show Slave Status :
```mysql
mysql> show slave status \G
```

## Troubleshouting slave errors :

### Stop and start slave :

```
stop slave; SET GLOBAL sql_slave_skip_counter =1; start slave;
```

If it does not fix use Xtra-Backup

##Restore slave server:
```mysql
1 : Dump Master
2 : Stop slave
3 : Reset slave (?)
4 : Drop slave
5 : Import from dump
6 : Start slave status
```

## tmp table

```mysql

#Get vars about tmp 
mysql>show global status like '%tmp%';

Created_tmp_disk_tables : The number of internal on-disk temporary tables
Created_tmp_files       : How many temporary files mysqld has created. 
Created_tmp_tables      : The number of internal temporary tables created 

```

Get top 3 of queries which has the biggest ammount of io on disk :

```mysql

SELECT * FROM performance_schema.events_statements_summary_by_digest ORDER BY SUM_CREATED_TMP_DISK_TABLES DESC LIMIT 3\G
```


