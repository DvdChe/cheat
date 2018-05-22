# Rsync Cheat :

```bash
rsync -av -e ssh --rsync-path="/usr/bin/sudo rsync" <file_from> <path_to>
```

**file_from** and **file_to** can be local such **/home/path/to/dir** or remote such **10.5.8.6:/home/path/to/dir**
