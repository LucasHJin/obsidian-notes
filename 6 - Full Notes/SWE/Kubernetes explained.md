2025-07-01 19:55

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Kubernetes explained

**Kubernetes (K8):** pen-source system for automating the deployment, scaling, and management of [[Docker explained|containerized applications]] 
- Manages clusters of containers at scale (a lot of containers on many different machines)
	- Keeps all containers healthy, balanced, and running smoothly in production

**Analogy:** 
- **Docker** → Like making individual meals (containers).
- **Kubernetes** → Like running a restaurant kitchen managing hundreds of meals, cooks, orders, inventory, and backups.

**Useful if:** 
- You have many services or microservices.
- You need auto-scaling, self-healing, and rolling updates.
- You’re deploying to cloud providers at scale (AWS, GCP, Azure).
- Your system needs high availability or load balancing across multiple machines.

**Cluster:** group of computers (or virtual machines) that work together to run applications
- **Master (control plane):** brain of cluster
	- Scheduling, scaling, health checks (*what to run, where, how*)
- **Worker nodes:** machines that run your containers (i.e. app, database, etc.)
	- Each node runs:
		- Docker/container runtime
		- Kubelet (talks to the master)
		- Pods (groups of containers)

# References

