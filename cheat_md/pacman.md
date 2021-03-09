# Pacman :

## Debian dpkg transposition :
```bash
dpkg -L 
# <=>
pacman -Qo


dpkg -l 
# <=>
pacman -Qqei <packagename>
```

# Get package name from file
```
   sudo pacman -Fy
   pacman -F $filename
   pacman -Fx $regex
```

# Remove package and its deps : 
```
   pacman -Rns package
```
