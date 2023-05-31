## Task 26

The sysadmin is tasked with configuring the Apache web server on `stapp0s`, fixing security issues found during an audit. The security settings below should be applied:
- It was identified that the Apache web server is exposing the version number. Ensure this server has the appropriate settings to hide the version number of the Apache web server.
- There is a website hosted under /var/www/html/media on the server. It was detected that the directory /media lists all of its contents while browsing the URL. Disable the directory browser listing in Apache config.
- Also make sure to restart the Apache service after making the changes.

We first modify the /etc/httpd/conf/httpd.conf file like whis:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/2ceb25fa-580a-41ff-a93a-7a67b4404340)

And finally check for the access on the /media directory:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/76b3ad17-21fb-4877-afe0-5c428ef84920)

We then remove the Indexes in Options:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/707dfc63-d8d0-4654-ad9a-6e35d13a7aa4)

Testing for /media again:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/47fac5e6-531c-4b29-9bbf-b8c355743db1)

**References:**
- [How to Hide Apache Version Number and Other Sensitive Info](https://www.tecmint.com/hide-apache-web-server-version-information/)
- [ConfluenceWiki for Apache - DirectoryListings](https://cwiki.apache.org/confluence/display/HTTPD/DirectoryListings)
