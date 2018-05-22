# SED Cheat :

Few sed tricks very helpful : 

## Print VHost server names (nginx) :

```bash
cat file.conf | sed -n '/server_name/ , /;/p'
```

## Find and replace :
```bash
sed 's/search/replace/g'
```
## Put content after pattern :
```bash
sed '/pattern/ r insert.txt' file.txt
```
vars such ~ does not works !!

