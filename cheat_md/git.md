# Git tricks : 

## Look for deleted file :

```bash
  git log --all --full-history -- <relative path of file>
```

## get repo URL

```bash
  git config --get remote.origin.url
```


# ~/.gitconfig :
```
[alias]
    lg = log --graph --pretty=tformat:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%an %ai)%Creset'

[gc]
    auto = 1000
    autopacklimit = 10
```

# Renaming branch :
```bash
git checkout <old_name>
git branch -m <new_name>
git push origin --delete <old_name>
git push origin -u <new_name>
```

# Removing all untracked files and folders : 

```bash
   # See what's gonna happens :
   git clean -nxd

   # Removing untracked files ( beware !! ): 
   git clean -fxd
```

# Prune branches

```
   git remote prune origin [ --dry-run ]
```

# Tags :

```bash
# tag locally 
git tag <mytag>
git push origin --tags
```
