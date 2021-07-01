# cheat


Because searching your reminder in an external app is so boring, I made a little script to retrieve my reminders easily. 
The reminders are written in markdown and are parsed by a python script (see requirements).

E/G :
```bash
cheat mysql
```

**Note :** Tons of md are from https://github.com/cirosantilli/linux-kernel-module-cheat 

## New Feature : cheat.sh

If you have no markdown but you want a cheat anyway, the script will automatically check on cheat.sh

You can also bypass your local markdown with **-b** or **--bypass** option :

```
  #If mysql.md exists, it will display its content :
  cheat mysql 

  #To bypass your local markdown and check directly on cheat.sh, just add the -b or --bypass option :
  cheat -b mysql

```

## Disclaimer
The cheat sheet are made for myself, and they will not surely fit for in your needs. It's up to you to make it as you want :)

## Installation :

### Requirement :
You need to install the (https://github.com/charmbracelet/glow)[Glow] cli tool. Refer to the readme : https://github.com/charmbracelet/glow#installation

Make sure glow is in your PATH var :

```bash
which glow
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

