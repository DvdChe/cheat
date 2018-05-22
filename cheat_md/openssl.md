#OpenSSL Informations 

##Show certs informations :
```bash
#On standard https server :
    openssl s_client -showcerts -connect <www.domain.com_or_ip>:443 -servername www.domain.com

#Get Expiration date :
    openssl s_client -servername NAME -connect HOST:PORT 2>/dev/null | openssl x509 -noout -dates

#On a non https server :
openssl s_client -showcerts -starttls imap -connect mail.domain.com:139

#Force the version :
openssl s_client -showcerts -(ssl2|ssl3|tls1|dtls1) -connect <www.domain.com_or_ip>:443 -servername www.domain.com

#Quick check : 
openssl s_client -connect www.coliback.com:443 -showcerts -servername www.coliback.com -debug | grep error
```
