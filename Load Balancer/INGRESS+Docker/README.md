# NGINX Load Balancer with Docker

This project demonstrates basic load balancing using NGINX and Docker Compose.
It runs two backend services and a load balancer that distributes incoming traffic between them using round-robin.

Each backend server is a small Flask app responding with different text.

## Running the Project

1. Start all the containers
``` docker
docker compose up
```

2. Test Load Balancing
``` browser
http://localhost:8080
```
3. Refresh multiple times - you should see alternating responses