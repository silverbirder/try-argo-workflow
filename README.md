# try-argo-workflow

## Setup

I use on Mac.

```
https://minikube.sigs.k8s.io/docs/start/
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
$ sudo install minikube-darwin-amd64 /usr/local/bin/minikube
$ brew install argoproj/tap/argo
$ minikube start
```

```
$ kubectl apply -f namespace_argo.yaml
$ kubectl apply -n argo -f https://raw.githubusercontent.com/argoproj/argo/stable/manifests/quick-start-postgres.yaml 
$ kubectl create clusterrolebinding cluster-admin-binding --clusterrole=cluster-admin
$ kubectl -n argo get deployment
$ kubectl -n argo port-forward deployment/argo-server 2746:2746
```

```
$ argo submit -n argo --watch https://raw.githubusercontent.com/argoproj/argo/master/examples/hello-world.yaml
$ argo list -n argo
$ argo get -n argo @latest
$ argo logs -n argo @latest
```

```
$ minikube stop
$ minikube delete --all --purge
```

## Link

* https://github.com/argoproj/argo/tree/master/examples
