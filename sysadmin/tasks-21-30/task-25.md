## Task 25

The sysadmin is tasked with configuring Apache in the `stapp03` server. It should listen on port 8087 and with the following redirects:
- Redirect `http://stapp02.stratos.xfusioncorp.com:8084/` to `http://www.stapp02.stratos.xfusioncorp.com:8084/`. This must be a permanent redirect i.e 301
- Redirect `http://www.stapp02.stratos.xfusioncorp.com:8084/blog/` to `http://www.stapp02.stratos.xfusioncorp.com:8084/news/`. This must be a temporary redirect i.e 302

First we change the port:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/be68a370-0474-415a-a049-e1ac36d091d9)

And finally, we add the required redirects in a new file /etc/httpd/conf/d/redirect.conf:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/a3d201c6-f3b4-4f5e-af24-588fd9017a94)

And finally we can test these redirections after restarting the httpd service:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/637181e4-83bc-4138-b58c-07b96c135105)

**Reference:** [How To Create Temporary and Permanent Redirects with Apache and Nginx](https://www.digitalocean.com/community/tutorials/how-to-create-temporary-and-permanent-redirects-with-apache-and-nginx)
