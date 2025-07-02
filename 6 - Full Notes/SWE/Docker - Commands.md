2025-06-30 10:59

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Docker - Commands

**Alternative** → use a [[Docker - Desktop|GUI]] 

`docker --help` → gives list of all possible Docker commands

`docker run X` → runs an instance of X if it already exists on the Docker host
- Else, it goes out to Docker Hub to pull the image down (only first time)
- *Note* → when running this, it will go into an exited state afterwards
	- There is nothing to keep the process running
	- This is because containers are used to run a specific task/process (i.e. host instance of web server or database) and the image is just a base image for other applications (not those actual applications by default)
- Can also append commands
	- I.e. `docker run X sleep 100` → keeps it running for 100 seconds
`docker pull X` → only pull the image (and not run the container)
`docker exec X Y` → run command Y on container X

`-d` → detached mode
- Runs container in the background
`--name` → lets you name the container
`-it` → allows you to interact with a container’s shell
- I.e. use `bash` or `sh` in a contianer

`docker ps` → lists all running containers with some basic info
- Use `-a` to use all current and past containers
`docker images` → list of downloaded images + sizes

`docker stop X` → stops instance of X
- X is name or ID 
`docker rm X` → removes container permanently (not taking up space in background)
`docker rmi X` → removes image that you are no longer planning to use
- *You must delete all dependent containers before* 



# References

