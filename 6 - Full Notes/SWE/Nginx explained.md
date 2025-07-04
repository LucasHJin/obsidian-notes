2025-07-03 19:22

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Nginx explained

**Nginx (engine-x):** a [[HTTP explained|web server]] → piece of software that handles incoming requests to your website or app and sends back the right content
- Commonly used for:
	- Reverse proxy (for routing traffic to backend servers)
	- Load balancer (to distribute traffic across servers)
	- Static file server (for things like images, CSS, JS)
	- SSL terminator (handling HTTPS)

Uses for full stack:
- Use alongside docker compose for managing containers (and their ports)
- On production server (i.e. AWS)
- To expose your app to the internet (80 → HTTP, 443 → HTTPS) 

**Reverse proxy:** a server that sits in front of your backend services (frontend app, backend API, etc.) and forwards incoming client requests to the appropriate service on behalf of the client 
- Opposite of forward proxy → forwards outgoing requests from clients to the internet 
- Instead of the user sending their requests to `localhost:3000` and `localhost:3001`
	- The user sends it to `localhost:80` (proxy) → which forwards it to the frontend or backend
	- ![[Screenshot 2025-07-03 at 7.27.24 PM.png]] 
**Example:** In `/nginx/nginx.conf`:
```nginx
location /api {
    proxy_pass http://localhost:3001/;
}

location / {
    proxy_pass http://localhost:3000/;
}
```

*NOTE:* Avoids [[CORS explained|CORS]] problems (everything accessed from same origin)
- And SSL is handled by nginx
- Can scale by routing to multiple backend instances

# References

