# Bug : processes are killed when logout if uid process == uid user.

edit the ```/etc/systemd/logind.conf``` then add   ```KillUserProcesses=no```
