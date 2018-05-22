# varnish Cheat :

Few varnish tricks very helpful : 

## Check if Varnish cache is full: 

```bash
ps -aux |grep varnish
varnishstat -1 |grep {lru|s0.g_space|s0.g_byte}

```
LRU Nuked is the number of swapping since varnish is running.
