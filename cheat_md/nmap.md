# Nmap tricks


```
  # quick scan subnet :$
  nmap -sn 192.168.1.0/24

  # check if specific tcp port is opened:
  nmap -p 443 <server_addr>

  # scanning from list file of host and out to xml
  nmap -iL hostlist.txt -p 443 -oX out.xml
  
  # Intense scan
  nmap -T4 -A -v 

  # Intense scan plus UDP
  nmap -sS -sU -T4 -A -v

  # Intense scan All ports !! - verry slow 
  nmap -p 1-65535 -T4 -A -v 

```
