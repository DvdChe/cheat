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


# Advanced tip and tricks

```
git contig --global alias.staash 'stash --all'

git config --global alias.bb !better-branch.sh

```


## Git confing
```
[includeIf]
```

## oldies but goodies
```
git blame -L 15,26:/path/of/file  #blame range of file
# works with log, show

git blame -w -C -C
# Ignore whitespaces
# detect lines moved or copied in the same commit 
# x2 or the commit that created te file
# x3 or or any commit at all 

git log -S <regex> file -p


git diff # by line

git diff --word-diff


git config --global rerere.enabled true

# REuse REcorded REsolution. when rebase and fix confllict once ! 

```

## New stuff
```
git branch --column 
# or
git config --global column.ui auto


git config --global branch.sort -commiterdate

git push --force-with-lease
# Will push only if local last ref == remote last ref 

#sign commit with ssh
git config gpg.format ssh 
git config user.signingkey = ~/.ssh/key.pub

git push --signed

git maintenance start # creates job that will fetch/pull incrementally. Usefull for big repo

```


## Big repo/monorepo stuff

```
# partial cloning
git clone --filter=tree:0

# sparse-checkout
git sparse-checkout <folder1> <folder2>

```


