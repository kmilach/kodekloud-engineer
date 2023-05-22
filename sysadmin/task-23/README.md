## Task 23

The sysadmin is tasked with modifying the Apache HTTP headers sent for a response on the `stapp03` server. The Apache server must also be configured to run on port 5003, instead of the default one.

The necessary headers are:
- X-XSS-Protection header with value 1; mode=block
- X-Frame-Options header with value SAMEORIGIN
- X-Content-Type-Options header with value nosniff

There must also be an index.html file under the default path /var/www/html with the content Welcome to the xFusionCorp Industries! written in it.

After installing and enabling the service, we edit the /etc/httpd/conf/httpd.conf file, modifying where necessary:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/82bf896a-81bc-4333-9995-3ddaca2dd961)

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/ee170632-6bfd-4cc5-9185-31084985622d)

And using curl to test the application:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/9b652251-6fc4-46f6-a346-75e7d6aea996)
