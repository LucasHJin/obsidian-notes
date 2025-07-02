2025-06-30 23:36

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Docker - Desktop

**What is it?** 
- GUI application that helps you build, manage, and run Docker containers and images on your local machine (no need for CLI)
- *Includes:* 
	- Docker Engine (container runtime)
	- Docker CLI
	- [[Docker - Docker Compose|Docker Compose]] 
	- Kubernetes
	- Dashboard (view containers, images, volumes)

**Lifecycle summary:** 
1. Launches a Linux VM (==Same one each time==) 
2. Starts Docker engine inside the VM
	1. All containers are in the same VM
3. Can now use GUI / CLI to use Docker
	1. Everything is stored in the Linux VM (but DD abstracts it)

*Note:* 
- You need to run Docker Desktop to use Docker on MacOS and Windows
	- Not on Linux → it uses a Linux based environment (VM) under the hood

# References

