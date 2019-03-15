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

## Print block starting with a parttern and finishing with another :

```bash
sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' 
```
e/g : in order to get TLS certificate 
