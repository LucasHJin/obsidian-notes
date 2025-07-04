2025-06-30 11:39

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Docker - Docker Compose

**Docker Compose:** tool for defining and running multi-container Docker applications using a simple YAML file (`docker-compose.yml`)
- Can manage multiple containers (i.e. web app, database, cache, etc.) with one command instead of multiple `docker run`
	- Can define container configurations in one place
	- Can set up networks, volumes, env variables easily
	- Useful for development, testing, and CI environments

**Workflow:** 
1. Define services (containers) in `docker-compose.yml` 
2. Run `docker compose up` to start all services
3. Run `docker compose down` to stop and remove services

**Terminology:** 
- `version` → compose file version (i.e. 3.8, 3, 2)
- `services` → defines containers
	- Each key in a service is a separate container
- Inside services:
	- `image` → docker image to use
	- `build` → path to a `Dockerfile` if you're building the image manually
	- `ports` → map host ports to container ports (`HOST:CONTAINER`)
	- `volumes` → mount volumes (`HOST_PATH:CONTAINER_PATH`)
	- `environment` → set environment variables
	- `depends_on` → set startup order (when starting up)
	- `networks` → custom/default network
	- `command` → override default container command

**Compose commands summary:** 

| Command                                   | Description                            |
| ----------------------------------------- | -------------------------------------- |
| `docker-compose up`                       | Start services                         |
| `docker-compose down`                     | Stop and remove services               |
| `docker-compose build`                    | Build images                           |
| `docker-compose ps`                       | List running services                  |
| `docker-compose exec <service> <command>` | Run command inside a running container |
| `docker-compose logs`                     | View logs                              |
- `-d` → run it detached 
- `docker compose up --build` → combines the up and build commands
	- Only need `--build` when you changed something that goes into the image
	- I.e. Dockerfile, dependencies, `.env`, etc.

*Example:* PERN stack (docker compose file points towards the Dockerfiles and follows the instructions in there)
```yaml
#docker-compose.yaml
version: '3.8'

services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000" #take traffic that comes on port X on computer and send to port Y in container
    environment:
      - NEXT_PUBLIC_API_URL=http://localhost:4000
    depends_on:
      - backend

  backend:
    build: ./backend
    ports:
      - "4000:4000"
    environment:
      - DATABASE_URL=postgres://postgres:password@db:5432/mydb
    depends_on:
      - db

  db:
    image: postgres:16
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      POSTGRES_DB: mydb
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```

```Dockerfile
# frontend/Dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000
CMD ["npm", "run", "dev"]
```

```Dockerfile
# backend/Dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 4000
CMD ["node", "index.js"]
```


# References

