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

### Create a cluster with minikube

```sh
minikube start
````

### Explore cluster with minikube
```sh
kubectl cluster-info
```

### See the nodes
```sh 
kubectl get nodes
```

### Names spaces that is created by default
```sh 
kubectl get namespaces
```

### check for pods and services installed
```sh
kubectl get pods -A
```

### Check the services that is running in the claster
```sh
kubctl get services -A
```

````````````````````````````````









