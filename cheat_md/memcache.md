# Memcached  Info :

Few Memcached tricks very helpful : 


## Get Memcached console : 
```
telnet  <ip> port
```

## Get stats

```
   
   #General statistics :
   stats 

```

Value to check :
evictions : amount of evictions
cmd_get             : Number of memcache is used
get_hits            : Successfull hit
get_misses          : Unsuccessfull hit
listen_disabled_num : kind of max_client   ( must stay to 0 )
conn_yields         : Amount of killed connections ( must stay to 0 )
bytes               : size of cache


## stats sizes :

```

#Sizes statistics. 
   stats sizes     
                     
```
First column = size in byte
Second column = number of objects of this size that are cached

## eviction cache behaviour 

