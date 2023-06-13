## Task 40

The sysadmin is tasked with creating a bash script, `media_backup.sh` on `stapp01`, with the following requirements:
* Create a `xfusioncorp_media.zip` file of the `/var/www/html/media` directory and its contents;
* Save the ZIP file to `/backups/`;
* Copy the file to the backup server `stbkp01` in the `/backup/` location as well;
* Make sure no password is needed for this operation.

We first write the following script:
```
#!/bin/bash

zip -r /backup/xfusioncorp_media.zip /var/www/html/media
scp /backup/xfusioncorp_media.zip clint@stbkp01:/backup/
```

We the create a SSH key pair, copy it into the backup server with ssh-copy-id and test the script:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/e8a5b83c-4bf5-4473-8190-fe6a5360536a)
