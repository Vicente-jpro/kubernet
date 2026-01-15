# kubernet
Kubernet commands and simple projects

Here’s **basic information about Kubernetes** (often shortened to **K8s**):

---

## What is Kubernetes?

**Kubernetes** is an **open-source platform** used to **deploy, manage, and scale containerized applications** automatically. It was originally developed by **Google** and is now maintained by the **Cloud Native Computing Foundation (CNCF)**.

---

## Why Kubernetes is used

Kubernetes helps you:

* Run applications in **containers** (usually Docker)
* **Automatically scale** apps up or down based on demand
* **Restart** failed containers
* **Distribute traffic** across containers (load balancing)
* **Roll out updates** with minimal downtime

---

## Key Concepts

### 1. Container

A lightweight package that includes an application and everything it needs to run.

### 2. Cluster

A Kubernetes **cluster** is a group of machines (nodes) that run your applications.

* **Master / Control Plane**: Manages the cluster
* **Worker Nodes**: Run the actual applications

---

## Core Kubernetes Components

### Control Plane

* **API Server** – Entry point for all commands
* **Scheduler** – Decides where to run containers
* **Controller Manager** – Ensures desired state
* **etcd** – Stores cluster data

### Node Components

* **kubelet** – Communicates with the control plane
* **kube-proxy** – Handles networking
* **Container Runtime** – Runs containers (Docker, containerd)

---

## Important Kubernetes Objects

* **Pod** – Smallest unit; one or more containers
* **Deployment** – Manages replicas of pods
* **Service** – Exposes pods to the network
* **Namespace** – Logical separation within a cluster
* **ConfigMap / Secret** – Store configuration and sensitive data

---

## How Kubernetes Works (Simple Flow)

1. You define what you want (YAML file)
2. Kubernetes schedules containers
3. It keeps the system in the **desired state**
4. If something fails, Kubernetes fixes it automatically

---

## Where Kubernetes is Used

* Cloud platforms (AWS, Azure, Google Cloud)
* Microservices architectures
* CI/CD pipelines
* High-availability systems

---

## Advantages

* High availability
* Scalability
* Portability across clouds
* Self-healing

## Challenges

* Steep learning curve
* Complex setup and management

---

#### Create a cluster with minikube

```sh
minikube start
````

#### Explore cluster with minikube
```sh
kubectl cluster-info
```
### Execute kubernet file.
```sh 
kubectl apply -f filename.yml
```

#### See the nodes
```sh 
kubectl get nodes
```

#### Names spaces that is created by default
```sh 
kubectl get namespaces
```

#### Show pods and services installed
```sh
kubectl get pods -A
```

#### Show extra data from pod (by preference use this comand)
```sh
kubectl get pods -n <namespace> -o wide
```
## Busybox
### Show busybox pods 
```sh 
kubectl get pods
```

### Use busybox as terminal
```sh
kubectl exec -it <busybox-pod> -- /bin/sh  
```

### Verify if pod (application)  is running `kubectl exec -it <busybox-pod> -- /bin/sh` 
```sh
wget <pod-ip-address>:<port>
```

#### Check the services that is running in the claster
```sh
kubctl get services -A
```

### Delete a pod
```sh
kubectl delete pod <pod-name> -n <namespace>

```

### Check pod logs or description. It is used to see the applications logs to identify the problems
```sh
kubectl describe pod <pod-name> -n <namespace>

```

```sh
kubectl describe pod <pod-name>

```

### Exposes LoadBalancer services
The minikube tunnel command creates a network route on your host machine to services deployed with type LoadBalancer in your minikube cluster.
```sh 
minikube tunnel
```

### The command  will list all services in the development namespace. it also shows the ip address

We are able to see the LoadBanlancer, cluster-ip external-ip and ports.
```sh 
kubectl get services -n <namespace>
```

### Used to see all the resources object
```sh
kubectl api-resouces
```

### List all pods
```sh
kubectl get pods -n kube-system
```

### etcd -> Stores all cluster state and configuration data
```sh 
kubectl get pods -n kube-system | grep etcd
```

### kube scheduler
```sh
kubectl get pods -n kube-system | grep kube-scheduler
```

---

## Kubernetes Cluster Components

A Comprehensive Glossary of Kubernetes Cluster Components

### Location in Cluster: Control Plane

* **Cloud Controller Manager**: Connects a Kubernetes cluster to a cloud provider's API, managing cloud-specific resources and ensuring proper integration with the underlying infrastructure
* **etcd**: A key-value store that saves all data about the state of the cluster; only the kube-apiserver can communicate directly with etcd
* **kube-apiserver**: The kube-apiserver is a key component of Kubernetes that exposes the Kubernetes API, handles most requests, and manages interactions with the cluster by processing and validating API requests, making it essential for the cluster's operation
* **kube-controller-manager**: Monitors the Kubernetes cluster's state, running processes to ensure the current state matches the desired state
* **kube-scheduler**: Identifies a newly created pod that has not been assigned a worker node and assigns it to a specific node

### Location in Cluster: Worker Nodes

* **Container Runtime**: Pulls container images, creates and manages containers, and ensures they run properly and securely as directed by the Kubernetes control plane
* **kube-proxy**: A network proxy that runs on each node in a Kubernetes cluster, maintaining network rules and enabling communication between pods and services within the node and the control plane, while also communicating directly with the kube-apiserver
* **kubelet**: An agent that runs on each node in a Kubernetes cluster, ensuring containers in a pod are running and healthy while communicating with the API server in the control plane to maintain the desired state of the node











