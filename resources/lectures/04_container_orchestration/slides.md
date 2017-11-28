<!-- Start -->
## Today's lecture
* Container Orchestration
  * Kubernetes
  * Demo - Kubernetes in OpenStack

Note:
These are the topics for todays lecture.




## Container Orchestration
Orchestration includes a number of features:
* Provisioning hosts
* Instantiating a set of containers
* Rescheduling failed containers
* Linking containers together through agreed interfaces
* Exposing services to machines outside of the cluster
* Scaling out or down the cluster by adding or removing containers
* Load balancing


--
## Container Orchestration
Kubernetes
* created by Google 
* one of the most feature-rich and widely used orchestration frameworks
* key features include:
  - Automated deployment and replication of containers
  - Online scale-in or scale-out of container clusters
  - Load balancing over groups of containers
  - Rolling upgrades of application containers
  - Resilience, with automated rescheduling of failed containers
  - Controlled exposure of network ports to systems outside of the cluster


--
## Container Orchestration
Kubernetes core components:

* Cluster 
  - one or more bare-metal servers or virtual machines (referred to as nodes)
  - providing the resources used by Kubernetes to run one or more applications
* Node
  - a worker machine, previously known as a minion
  - has the services necessary to run pods
  - managed by the Master-Nodes
* Pods 
  - groups of containers and volumes co-located on the same host
  - containers in the same Pod share the same network namespace - `localhost`
  - pods are considered to be ephemeral


--
## Container Orchestration
Kubernetes core components:
* Labels 
  - tags assigned to entities such as containers
  - allow them to be managed as a group
  - e.g.
    - `"release" : "stable", "release" : "canary"`
    - `"environment" : "dev", "environment" : "qa", "environment" : "production"`
* Replication Controller
  - ensures that a specified number of pod replicas are running at any one time
* Services
  - act as basic load balancers and ambassadors for pods
  - exposing them to the outside world
  - pods targeted by a Service is (usually) determined by a Label Selector 


---
## Demo
* Create a Cluster
* 