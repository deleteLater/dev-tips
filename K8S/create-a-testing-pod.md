## Create a pod with curl

```bash
# create a custom container: alpine-with-curl
docker run -it alpine:3.14
apk add curl
docker commit <container-id> alpine-with-curl

# run alpine-with-curl image as a pod
kubectl run alpine-with-curl --image alpine-with-curl:latest --image-pull-policy Never --command -- sleep 10000
```