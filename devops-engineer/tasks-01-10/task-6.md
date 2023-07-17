## Task 6

The engineer is tasked with the following:

- Create a `PersistentVolume` named as `pv-nautilus`. Configure the `spec` as storage class should be `manual`, set capacity to `5Gi`, set access mode to `ReadWriteOnce`, volume type should be `hostPath` and set path to `/mnt/finance` (this directory is already created and it might not be directly accessible, so no need to worry).
- Create a `PersistentVolumeClaim` named as `pvc-nautilus`. Configure the `spec` as storage class should be `manual`, request `3Gi` of the storage, set access mode to `ReadWriteOnce`.
- Create a `pod` named as `pod-nautilus`, mount the persistent volume you created with claim name `pvc-nautilus` at document root of the web server, the container within the pod should be named as `container-nautilus` using image `httpd` with `latest` tag only (remember to mention the tag i.e `httpd:latest`).
- Create a node port type service named `web-nautilus` using node port `30008` to expose the web server running within the pod.

Since we have 4 tasks, we will be creating 4 different definitions in a YML file (`nautilus.yml`), each detailed below:

```yaml
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-nautilus
spec:
  storageClassName: manual
  capacity:
    storage: 5Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/mnt/finance"

---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-nautilus
spec:
  storageClassName: manual
  resources:
    requests:
      storage: 3Gi
  accessModes:
    - ReadWriteOnce

---
apiVersion: v1
kind: Pod
metadata:
  name: pod-nautilus
  labels:
    app: nautilus
spec:
  containers:
    - name: container-nautilus
      image: httpd:latest
      ports:
        - containerPort: 80
          name: "http-server"
      volumeMounts:
        - mountPath: "/var/www/html"
          name: storage-nautilus
  volumes:
    - name: storage-nautilus
      persistentVolumeClaim:
        claimName: pvc-nautilus

---
apiVersion: v1
kind: Service
metadata:
  name: web-nautilus
spec:
  type: NodePort
  selector:
    app: nautilus
  ports:
    - port: 80
      targetPort: 80
      nodePort: 30008
```
