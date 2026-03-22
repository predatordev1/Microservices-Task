<h1>Assignment | Skill Test 2 _ Container Orchestration</h1>
<h2>Objective: <h3>Deploy a microservices application on Kubernetes using Minikube, ensuring proper service communication and configuration.</h3></h2>

## Architecture

| Service | Port | Description |
| --- | --- | --- |
| `User Service` | 3000 | User authentication, registration, JWT issuance |
| `Product Service` | 3001 | Video catalogue, S3 playback endpoints, public APIs |
| `Order Service` | 3002 | Dedicated admin microservice for asset management and uploads |
| `Gateway Service` | 3003 | Websocket + REST chat for live watch parties |

---

# Create Kubernetes Deployment manifests for all services
``` bash
Each deployment included:
Correct container image reference
Resource limits and requests
Environment variables
Liveness and readiness probes
Proper labels and selectors
```

User Service deployment

Product Service deployment

Order Service deployment

Gateway Service deployment  (includes additional proxy handling setup if required)

