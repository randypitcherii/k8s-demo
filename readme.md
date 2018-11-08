# Kubernetes Demo
The purpose of this repo is to provide a jumping-off point for cool kubernetes projects.

## Definitions
Let's check out some terminology below.

### Basic Objects
- `pod` -> container / set of containers + storage resources + unique IP + local options
- `service` -> abstraction layer on top of a set of ephemeral pods (think of this as the 'face' of a set of pods)
- `volume` -> sometimes-shared, persistent storage
- `namespace` -> virtual cluster on top of an underlying physical cluster

### Controllers
- `replicaSet` -> ensures a certain number of pods are running
- `deployment` -> declaritively manages a `replicaSet`
- `statefulSet` -> like a deployment, but for non-interchangeable (or stateful) underlying pods
- `daemonSet` -> manages pods that need to run on all/some nodes
- `job` -> manages a set of pods that run to completion and tracks the overall progress

### Control Plane
- `master` -> entity responsible for managing cluster state
    - `kube-apiserver` -> exposes cluster control and state
    - `kube-controller-manager` -> this is where the 'brain' of controllers live
    - `kube-scheduler` -> matches resources to work
- `node` -> individual machine/vm that make up the cluster
    - `kubelet` -> service that communicates with the master
    - `kube-proxy` -> proxy for connecting to the cluster network
