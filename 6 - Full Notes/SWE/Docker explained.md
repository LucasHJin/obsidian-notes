2025-06-29 21:21

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Docker explained

**Docker:** open-source platform designed to automate the deployment, scaling, and management of applications using containerization (allows code to run the same across different environments)
- *Simply put* → Docker can create containers that house all the information to run your app (provides a high level way of managing containers)
- Each software is a container built from the image (i.e. Next.js, Express, PostgresSQL)
	- You can define and run multiple containers together by:
		- Using multiple separate `docker run` commands
		- Use [[Docker Compose|Docker - Docker Compose]] to describe all services, networks, and volumes, and then bring them all up with one command

**Benefits:** 
- *Portability* → Runs on any system with Docker installed (Windows, Mac, Linux, servers)
- *Consistency* → Same behavior in development, testing, and production
- *Isolation* → Apps run in separate containers, so they don't conflict
- *Efficiency* → Uses fewer resources than virtual machines (shares OS kernel)
____
### Key Terms
**Image** → The blueprint/template for a container (like a recipe)
- Read-only template of everything needed to run an application (i.e. code, dependencies, runtime, env, configs, etc.)

**Containers** → A running instance of an image (like a meal made from a recipe)
- Completely isolated environment (just like VM)
	- *BUT* → all share the same OS kernel
	- Operating systems only differ based on the software on top of them (Underlying kernel works with all OSS above)
	- Is essentially actually using that image to run the application
- *Containers vs VMs:* 
	- Each VM has it’s own OS → higher utilization, disc space, slower boot up
	- ![[Screenshot 2025-06-30 at 10.54.03 AM.png|400]] 

**Dockerfile** → A script (plain text file) with instructions to build a Docker image
- Can define base image + layer on commands (i.e. installing packages, copying files, setting up env, etc.)
```
FROM node:18-alpine      # Base image
WORKDIR /app             # Working directory inside container
COPY . .                 # Copy local files to container
RUN npm install          # Install dependencies
CMD ["npm", "start"]     # Default command to run
```

**Docker Hub** → A public repository to share and download Docker images
- Like an app store where you can upload or download other’s Docker images

___
**How it works:** 
- There are public containerized versions of most software (i.e. databases + services) on Docker Hub (==in the form of images==) 
	- You can use `Docker run X` to run those software through docker
	- You can use load balancer to run these software multiple times
- [[Docker - Commands]] 

____




Useful concepts:




# References

