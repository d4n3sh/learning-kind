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

Build a simple 4 node cluster.
1 control-plane, 4 workers

Create a cluster config file 

* 4-node-cluster.yaml

```
# 1 control-plane, 4 workers
---
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
- role: worker
```
Build the cluster
```
❯ kind create cluster --name "cluster-1" --config 4-node-cluster.yaml --wait 60s
```

[Official kind quickstart](https://kind.sigs.k8s.io/docs/user/quick-start/)