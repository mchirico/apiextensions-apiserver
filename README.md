# apiextensions-apiserver


Reference:
https://github.com/kubernetes/sample-apiserver

```bash

CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -o artifacts/simple-image/apiextensions-apiserver


docker build -t quay.io/mchirico/apiextensions-apiserver:v1 ./artifacts/simple-image

docker push quay.io/mchirico/apiextensions-apiserver:v1



```

# Deploy to kubernetes

```bash

kubectl apply -f artifacts/example
```









Implements: https://github.com/kubernetes/community/blob/master/contributors/design-proposals/api-machinery/thirdpartyresources.md

It provides an API for registering `CustomResourceDefinitions`.

## Purpose

This API server provides the implementation for `CustomResourceDefinitions` which is included as
delegate server inside of `kube-apiserver`.


## Compatibility

HEAD of this repo will match HEAD of k8s.io/apiserver, k8s.io/apimachinery, and k8s.io/client-go.

## Where does it come from?

`apiextensions-apiserver` is synced from https://github.com/kubernetes/kubernetes/blob/master/staging/src/k8s.io/apiextensions-apiserver.
Code changes are made in that location, merged into `k8s.io/kubernetes` and later synced here.
