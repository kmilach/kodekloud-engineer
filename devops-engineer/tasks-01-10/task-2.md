## Task 2

The engineer is tasked with troubleshooting a kubernetes template which fails when applying it. The engineer should not remove any component from the template.

Looking into the template file, `mysql_deplyment.yml`, we first try to run the template and check the errors in stdout:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/2732e011-2e00-4b61-9cd3-2e2403dfe52c)

So we first correct the spelling errors, correct the apiVersion to v1 in the PersistentVolume and PersistentVolumeClaim components (and apps/v1 in Deployment), and checked for the 'app' field in the Service component, which should be under 'labels':
```
apiVersion: v1
kind: Service
metadata:
  name: mysql
  labels:
    app: mysql-app
spec:
  type: NodePort
```

Trying to apply the template a second time yields:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/5c943b8e-2941-411f-a1b1-8842f2358a40)

With this, we then check the the documentation on PersistentVolume and PersistentVolumeClaim components, checking for more syntax:
```
spec:
  storageClassName: standard
  capacity:
    storage: 250Mi
  accessModes: 
    - ReadWriteOnce
  hostPath:
    path: "/mnt/data"
  persistentVolumeReclaimPolicy: Retain
```
We also change the 'storage' field value in the PersistentVolumeClaim from 250MB to 250Mi. Finally, there were extra spaces which were removed.

Still, there was an error about YAML to JSON conversion. Since the `kubectl apply` command is not user-friendly when troubleshooting which part of the template is actually failing, a new file deploy.yml is created with the Deployment component template, which shows it was this component that was giving off the error:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/4fd952e9-d7f1-4144-b82c-ae38a90db6b6)

With this, the template is checked again and we notice that the 'name' key in the environment variables should has the wrong syntax:
```
- name: MYSQL_ROOT_PASSWORD
  valueFrom:
    secretKeyRef:
      name: mysql-root-pass
      key: password
- name: MYSQL_DATABASE
  valueFrom:
    secretKeyRef:
      name: mysql-db-url
      key: database
- name: MYSQL_USER
  valueFrom:
    secretKeyRef:
      name: mysql-user-pass
      key: username
- name: MYSQL_PASSWORD
  valueFrom:
    secretKeyRef:
      name: mysql-user-pass
      key: password
```
