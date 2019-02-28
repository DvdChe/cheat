#OpenSSL Informations 

# Show certs informations :

## On standard https server :

```bash
    openssl s_client -showcerts -connect <www.domain.com_or_ip>:443 -servername www.domain.com
```
## Get Expiration date :

```bash
openssl s_client -servername NAME -connect HOST:PORT 2>/dev/null | openssl x509 -noout -dates
```
## On a non https server :
```bash
openssl s_client -showcerts -starttls imap -connect mail.domain.com:139
```
## Force the version :
```bash
openssl s_client -showcerts -(ssl2|ssl3|tls1|dtls1) -connect <www.domain.com_or_ip>:443 -servername www.domain.com
```

## Quick check : 
```bash
openssl s_client -connect www.xxx:443 -showcerts -servername xxx.com -debug | grep error
```

## Check cert and key :
```
(openssl rsa -noout -modulus -in private.key | openssl md5 ; openssl x509 -noout -modulus -in certificate.crt | openssl md5) | uniq
```

## Inspect cert
```
   openssl x509 -in certificate.crt -text -noout
```
