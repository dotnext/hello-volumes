# hello-volumes
Simple code to test Kubernetes volumes

Just create this deployment on your Kubernetes cluster with:

```
kubectl create -f .\hello-volumes.yaml
```

This will create two containers and a volume mounted to both containers in different mount points.

We will now create a new file in that mount from one container and then "ls" from the other to check that the file is visible:

```
kubectl exec -ti busybox2-volumes -c busybox-1 -- touch /mount-1/fabio

kubectl exec -ti busybox2-volumes -c busybox-2 -- ls -l /mount-2
```

