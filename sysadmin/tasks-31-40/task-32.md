## Task 32

The sysadmin is tasked with finding all files with a `.css` extension on the `/var/www/html/ecommerce` directory. These files should be copied to the `/ecommerce` directory, while also preserving the parent directory structure. Take note that the sysadmin should not copy all of `/var/www/html/ecommerce` directory's contents.

This task is quite similar to task #14 and can be accomplished with the following command:

`find /var/www/html/ecommerce -type f -name *.css -exec cp --parents {} /ecommerce \;`
