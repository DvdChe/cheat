# Postgres tricks

## Meta commands :

```
   show databases:  \l
   use database:    \c database
   show tables:     \dt
   show privileges: \du
```


## Create Database and its user with full privileges : 
```
postgres=# CREATE DATABASE <DB>
postgres=# CREATE USER myuser WITH ENCRYPTED PASSWORD 'mypass';
postgres=# GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;
```
