# AWK Cheat :

Few awk tricks very helpful : 

## Display entries only once :

```bash
awk '!seen[$0] {print}{++seen[$0]}' file.txt
```

## Get top 10 ip in apache log : 
```bash
awk '{ print $1}' <logfile> | sort | uniq -c | sort -nr | head -n 10
```

## Summarize Column $1
```
awk '{s+=$1} END {print s}'
```
