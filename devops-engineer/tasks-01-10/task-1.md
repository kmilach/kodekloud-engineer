## Task 1

The engineer is tasked with creating a kubernetes pod in the cluster, with the following requirements:
- Pod name is `httpd-pod`
- Container name is `httpd-container`
- `httpd` image with the `latest` tag
- Requests: 15Mi (memory) and 100m (CPU)
- Limits: 20Mi (memory) and 100m (CPU)

**Note**: the `kubectl` utility on jump_host has been configured to work with the kubernetes cluster.
