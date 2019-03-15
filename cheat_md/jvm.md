## Importing public cert in keytool: 

```bash

openssl s_client -connect google.com:443 –servername google.com:443 < /dev/null | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > public.crt

<JAVA_HOME>/bin/keytool -import -alias <server_name> -keystore <JAVA_HOME>/jre/lib/security/cacerts -file public.crt
# Default password : Changeit

``` 
