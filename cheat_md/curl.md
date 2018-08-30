# authentication with curl on modern web

You might need to call guy from curl one day

(ie. with cookies)

Create a variable with your guy password : (so you won't have your guy password in history... This is not satisfying if you're not the only admin on the box)

```bash
$ pass=`/lib/cryptsetup/askpass "pass:"`
[type your password here]
$
(hit Ctrl+L to empty your screen)
```

Call the authentication page : 

```bash
$ curl --data-raw "username=login&password=$pass" -X POST -c cookie.txt \
https://guy.nbs-system.com/login
```

Delete the environment variable as you wont need it anymore : `unset pass`
You can now use `cookie.txt` to browse Guy : 

```bash 
$ curl -b cookie.txt https://guy.nbs-system.com/client/
```

The cookie carry your authentication to Guy for several hours. Treat it like your password.
Don't share it, and delete it when you're done.

```
rm cookie.txt
```

I'm using this on Guy as an example. Such a process will work on a lot of sites.
