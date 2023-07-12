## Task 3

The engineer is tasked with creating a namespace called `datacenter` and create a deployment under it. The deployment has the following requirements:
- Name: `httpd-deploy`
- Container named `httpd`, with image `httpd:2.4.27` and 3 replicas
- Deployment should use the `RollingUpdate` strategy with `maxSurge=1` and `maxUnavailable=2`
- Create a `NodePort` service named `httpd-service` and expose deployment on `nodePort: 30008`

After created, update the deployment to version `httpd:2.4.43` and then rollback to the previous version.

We first created the required namespace with the following file `namespace-datacenter.yml`:
```
apiVersion: v1
kind: Namespace
metadata:
  name: datacenter
  labels:
    name: datacenter
```

We create the following file, `deployment.yml`, for the entire deployment:
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: httpd-deploy
  labels:
    app: httpd
spec:
  selector:
    matchLabels:
      app: httpd
  replicas: 3
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 1
      maxUnavailable: 2
  template:
    metadata:
      labels:
        app: httpd
    spec:
      containers:
        - name: httpd
          image: httpd:2.4.27
          ports:
            - containerPort: 80
```
and then for the service, `service-nodeport.yml`:
```
apiVersion: v1
kind: Service
metadata:
  name: httpd-service
spec:
  type: NodePort
  selector:
    app: httpd
  ports:
    – port: 80
      targetPort: 80
      nodePort: 30008
```

Applying all of these files (remember to use the flag `--namespace=datacenter` after creating the namespace), we deploy all specified resources. Now, editing the `deployment.yml` configuration file, we change the container image to the specified version and change the deployment.

After that we use these `kubectl rollout` commands to verify the revisions and rollback the image version.

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/420f99ea-e6bf-4d42-a981-78b7f13f710f)
