## Task 14

The sysadmin is tasked with find all files with the `mariyam` owner and copying them to the `/official` directory. There is also a requirement that the files should maintain the same folder structure, preserving the full paths.
This makes it an excellent use case for the `cpio` command, which can be used together with the `find` command to get the files which belong to the user

<img width="497" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/4df929fb-84ae-4595-9e87-d18ad4f0639f">

See `cpio` man page [here](https://linux.die.net/man/1/cpio).

This task can also be accomplished with the `-exec` flag for the `find` command, as in:

`find /home/userdata -type f -user mariyam -exec cp --parents {} /official \;`
