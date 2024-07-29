# Nginx Ingress Recommended Settings

This is a recommended Nginx configuration to speed up the platform in customer deployments. A default configmap exists in the ingress-nginx namespace, typically named ingress-nginx-controller. The name may vary depending on how the ingress was installed on the cluster.

```
kubectl edit configmap ingress-nginx-controller
```

The configmap data:
```
apiVersion: v1
data:
  allow-snippet-annotations: "true"
  enable-brotli: "true"
  keep-alive: 120s
  keep-alive-requests: "10000"
  use-gzip: "true"
  use-http2: "true"
kind: ConfigMap
```


