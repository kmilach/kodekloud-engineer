## Task 5

The engineer is tasked with creating a file, `cluster.pp`, under the directory `/etc/puppetlabs/code/environments/production/manifests`, directly on the master node, which is the jump server itself.
Make sure the package `httpd` is installed on app server 2 (puppet agent node 2) with the `package` Puppet resource.

**Note:** Please make sure to run the puppet agent test using `sudo` on agent nodes, otherwise you can face certificate issues. In that case you will have to clean the certificates first and then you will be able to run the puppet agent test.

After checking that the puppet service is working in both assets (`puppetserver.service` and `puppet.service`), we start by creating the aforementioned file, with the following configuration:

```
package { 'httpd':
  ensure  => installed,
}
```

We then apply this new configuration with the command `puppet agent -t` in the app server 2, which gives us:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/80e74f58-21a5-414f-8d4b-890e50ae8c70)

We then use the same command with `sudo`:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/7280a5d9-fce0-4f0d-96c8-d888209ed205)

Checking for the httpd package in the server:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/5575b813-fb70-4c41-8a3c-1381f4c326e6)

**References:**
- [Resource Type: package](https://www.puppet.com/docs/puppet/7/types/package.html#package-attribute-ensure)
