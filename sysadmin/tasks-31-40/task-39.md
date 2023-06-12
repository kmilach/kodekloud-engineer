## Task 39

The sysadmin is tasked with setting up an Apache Tomcat service in the `stapp02` server. The prerequisites are:
* Configure it to run on port 6200
* Make sure the webpage works directly on base URL i.e without specifying any sub-directory anything like this http://URL/ROOT

**Note:** there is a `ROOT.war` file on the jump host in the `/tmp` directory.

We first install the Tomcat package with `yum` and then configure a Connector in the `/etc/tomcat/server.xml`:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/0b59685a-2df0-43d8-85ea-fbb6fbe55664)

As we saw on the same file, files are accessed through the "webapps" folder, so we use a `find` command to locate the directory `/usr/share/tomcat/webapps`. There, we put the `ROOT.war` file and restart the Tomcat service, testing if the configuration worked with `curl`:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/c9dd6a7f-00d1-4ade-952f-56263cedbc50)

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/37c67a49-1499-4ce6-8e3d-579c9cec6c81)

**Reference:** [How to Use the autoDeploy Attribute in Apache Tomcat](https://www.webucator.com/article/how-to-use-the-autodeploy-attribute-in-apache-tomc/)
