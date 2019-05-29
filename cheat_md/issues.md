# SSH And Logind : 

If user logout his ssh session, all related process will have mutex and semaphores wiped so killed related process.
To fix this : 

```
   # In /etc/systemd/logind.conf adding this line will fix the issue : 
   RemoveIPC=no
```
