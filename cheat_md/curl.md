i# authentication with curl on modern-ish websites

You might need to auth to a nice forum from curl one day

(ie. with cookies)

Create a variable with your password : (so you won't have your password in history... This is not satisfying if you're not the only admin on the box)

```bash
$ pass=`/lib/cryptsetup/askpass "pass:"`
[type your password here]
$
(hit Ctrl+L to empty your screen)
```

Call the authentication page : 

```bash
$ curl --data-raw "username=login&password=$pass" -X POST -c cookie.txt \
https://dogeblog.org/login
```

Delete the environment variable as you wont need it anymore : `unset pass`
You can now use `cookie.txt` to browse the site : 

```bash 
$ curl -b cookie.txt https://dogeblog.org/client/
```

The cookie carry your authentication to dogeblog for several hours. Treat it like your password.
Don't share it, and delete it when you're done.

```
rm cookie.txt
```

Such a process will work on a lot of sites.

