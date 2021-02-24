A bit from kubernetes.io

```
kubectl run php-apache --image=k8s.gcr.io/hpa-example --requests=cpu=200m --expose --port=80
```

```
kubectl autoscale deployment php-apache --cpu-percent=50 --min=1 --max=10
```

```
kubectl get hpa
```

CMD+D

```
kubectl run --rm -it load-generator --image=busybox /bin/sh
while true; do wget -q -O- http://php-apache.default.svc.cluster.local; done
```

On Left:
```
kubectl get hpa
```

Target should be above 50%

```
kubectl get deployment php-apache
```