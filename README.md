# deployment-with-sleep infinity

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: rbac
spec:
  replicas: 1
  selector:
    matchLabels:
      app: rbac
  template:
    metadata:
      labels:
        app: rbac
    spec:
      serviceAccountName: pod-list-sa
      containers:
      - name: kubectl
        image: bitnami/kubectl:latest
        command: ["/bin/sh"]
        args: ["-c", "sleep infinity"]
```
