# cheat

Because searching your reminder in an external app is so boring, I made a little script to retrieve my reminders easily. 
The reminders are written in markdown and are parsed by a python script (see requirements).

E/G :
```bash
cheat mysql
```

## Installation :

### Requirement :
You need to install the mdv command via pip :

```bash
pip install --user mdv
```

Make sure mdv is in your PATH var :

```bash
which mdv
```

Add cheat command in your path var too :

```bash
export PATH=$PATH":/location/of/cheat/repository/"
```
That's it !

## Additionnal informations

### Add new cheat sheet :

Just create a .md file in the cheat_md directory :

```bash
touch new_cheat_sheet.md
```

and that's it :
```bash
cheat new_cheat_sheet
```
