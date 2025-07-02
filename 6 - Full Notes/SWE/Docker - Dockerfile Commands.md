2025-07-01 20:44

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Docker - Dockerfile Commands

| Instruction  | What it Does                                                                        |
| ------------ | ----------------------------------------------------------------------------------- |
| `FROM`       | Specifies the base image to build upon (e.g., `node:18-alpine`)                     |
| `RUN`        | Executes a shell command inside the image during build (e.g., `RUN apt-get update`) |
| `COPY`       | Copies files from your local machine into the image                                 |
| `ADD`        | Similar to COPY but can also extract archives or fetch URLs                         |
| `WORKDIR`    | Sets the working directory inside the image for following commands                  |
| `ENV`        | Sets environment variables                                                          |
| `EXPOSE`     | Documents which ports the container listens on                                      |
| `CMD`        | Sets the default command to run when a container starts                             |
| `ENTRYPOINT` | Similar to CMD but more rigid; defines executable                                   |
| `USER`       | Switches the user that runs commands inside the container                           |
| `VOLUME`     | Declares mount points for persistent data                                           |




# References

