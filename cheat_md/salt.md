# Salt Cheat :

Few test tricks very helpful : 

## salt usual commands

```
   # List of states related to a module :
   salt-call <module_name> -d 

   # Get grains of a minion :
   salt-call grains.items

```

## Salt specific functions :

```bash
salt-call grains.setval database_ip xxx.xxx.xxx.xxx
salt-call state.sls generic.php.phpmyadmin
```
