# learning-kind

Quickly build a single node k8s cluster with the name "cluster-1".

Use `--wait <time>` to wait for control-plane to become ready.

```
kind create cluster --name "cluster-1"
kind create cluster --name "cluster-1" --wait 30s
kind create cluster --name "cluster-1" --wait 1m
```

List running clusters
```
kind get clusters
```

List nodes in the "cluster-1" cluster
```
kind get nodes --name "cluster-1"
```

Delete the "cluster-1" cluster
```
kind delete cluster --name "cluster-1"
```

[Official kind quickstart](https://kind.sigs.k8s.io/docs/user/quick-start/)