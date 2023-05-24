## Task 33

The sysadmin is tasked with installing and configuring `nginx` in the `stapp02` server. There will be a self-signed certificate and the certificate and key files are at `/tmp/nautilus.crt` and `/tmp/nautilus.key` respectively.
The files should be moved to some appropriate location and deploy the same in Nginx. Create an `index.html` file with content "Welcome!" under Nginx document root.

To install nginx in a CentOS server, we first need to install the epel-release software repository. After that, we create a directory, /etc/pki/nginx/ and move the certificate files there.

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/37ec16c1-f236-4356-8383-c536d645308d)

We also create the index.html file with the message in the full path /usr/share/nginx/html/index.html, after removing the previous one (which is actually a soft link to another file):

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/93f345c2-9128-4add-8542-47fc6d7f9968)

Finally, we configure the /etc/nginx/nginx.conf file, in order to setup the server, changing from non-SSL to SSL as shown below:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/87b45fbc-57f1-4742-b3a5-cdf6b6e9fc85)

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/2c5f1753-d99d-415c-9c4c-2c7c94115a82)

And finally, testing it from the jump server:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/ffa12498-f240-400f-82d6-e134a27c3c1c)

References:
- [How To Install Nginx on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-centos-7)
- [Nginx - Configuring HTTPS servers](https://nginx.org/en/docs/http/configuring_https_servers.html)
