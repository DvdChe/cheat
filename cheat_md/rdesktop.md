# Rdesktop tricks


## Auth to kerberos :


### First, create kerberos ticket :
```
   kinit user@DOMAIN.COM 
```

### Check if ticket is correctely created:

```
   klist
```

### If needed, revoke ticket :
```
   kdestroy
```

### Open resktop session :

```
rdesktop server.domain.com:3389 -u "user" -v -r clipboard:CLIPBOARD -p - 
```
