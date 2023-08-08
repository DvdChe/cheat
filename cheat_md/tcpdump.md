# TCPDump cheat sheet


## Some usefull args : 
```bash
tcpdump -n [...]  # No dns resolution
tcpdump -nn [...] # no dns and port resolution
tcpdump -p [...] # promiscuous mode 
tcpdump -D # List interfaces
```

## Dump to pcap : 

```
tcpdump -i <interface> -nn -C <size (Mb) of pcap file> -w <filename> 
```

