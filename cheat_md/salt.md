# Salt Cheat :

Few test tricks very helpful : 

## Salt usual commands

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

salt-call -d grains
```

## Usefull files and directories:

```
   /etc/salt/
   /data/salt
```

## Targetting :

```
   salt -L 'comp1,conp2,comp3' grains.item kernelrelease
   salt -G 'acme_client:<clientid>' ...
   salt -C 'G@nbs_client:mnf and nbs'
```

## Dry run :

```
   salt <command> test=True

```


