## Task 1

The engineer is tasked with creating a kubernetes pod in the cluster, with the following requirements:
- Pod name is `httpd-pod`
- Container name is `httpd-container`
- `httpd` image with the `latest` tag
- Requests: 15Mi (memory) and 100m (CPU)
- Limits: 20Mi (memory) and 100m (CPU)

**Note**: the `kubectl` utility on jump_host has been configured to work with the kubernetes cluster.

Except for the container name, every option is doable directly at the command line with `kubectl`. This indicates that a configuration file should be written to properly create a pod with the necessary requirements:

Taking a sample configuration file, we modify it to look like this:
```
apiVersion: v1
kind: Pod
metadata:
  name: httpd-pod
spec:
  containers:
  - name: httpd-container
    image: httpd:latest
    resources:
      requests:
        memory: "15Mi"
        cpu: "100m"
      limits:
        memory: "20Mi"
        cpu: "100m"
```

We save it as `httpd-pod.yaml` and run with `kubectl apply -f httpd-pod.yaml`. With kubectl describe pod/htppd-pod, we can confirm that the requirements were met:

![image](https://github.com/kmilach/kodekloud-engineer/assets/53876300/82ba60f4-ac35-437a-a979-df8448096ebb)

**References:**
- [K8s docs - Pods](https://kubernetes.io/docs/concepts/workloads/pods/)
- [K8s docs - Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/)
