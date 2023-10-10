# Postgres tricks

## Meta commands :

```
   show databases:                     \l
   use database:                       \c database
   show tables:                        \dt
   show privileges:                    \du
   show privileges on specific table : \z <database>
```


## Create Database and its user with full privileges : 
```
postgres=# CREATE DATABASE <DB>
postgres=# CREATE USER myuser WITH ENCRYPTED PASSWORD 'mypass';
postgres=# GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;
```

## Show running queries :
```
postgres=# select * from pg_stat_activity;

SELECT pid, age(clock_timestamp(), query_start), usename, query 
FROM pg_stat_activity 
WHERE query != '<IDLE>' AND query NOT ILIKE '%pg_stat_activity%' 
ORDER BY query_start desc;
```

## Kill running query
```
SELECT pg_cancel_backend(procpid);
```

## kill idle query
```
SELECT pg_terminate_backend(procpid);
```

## WAL bckup : 

Force wal backup manually in spilo/patroni
```
su - postgres
envdir "/run/etc/wal-e.d/env" /scripts/postgres_backup.sh "/home/postgres/pgdata/pgroot/data"
```
