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

### All Deployments are created.
<img width="1848" height="912" alt="image" src="https://github.com/user-attachments/assets/10fbd333-5d8a-48f9-b184-3b207ca9de35" />

### User Service deployment
<img width="1210" height="800" alt="image" src="https://github.com/user-attachments/assets/6d461ca9-2b68-4567-bd6b-28aeb5d72d6e" />

### Product Service deployment
<img width="1250" height="842" alt="image" src="https://github.com/user-attachments/assets/e8b3b305-3ce8-401e-9025-4dc2873bb82a" />

### Order Service deployment
<img width="1184" height="881" alt="image" src="https://github.com/user-attachments/assets/58cef8ff-387d-492d-94a2-0b429444c160" />

### Gateway Service deployment  (includes additional proxy handling setup if required)
<img width="1165" height="870" alt="image" src="https://github.com/user-attachments/assets/8bbce106-74ed-4b40-9ad7-50571d4166ba" />

# Create corresponding Service resources

### All Service files are created.
<img width="1241" height="736" alt="image" src="https://github.com/user-attachments/assets/58e3d1f3-ddb5-4b89-918c-8ebc4ed87378" />
<img width="866" height="381" alt="image" src="https://github.com/user-attachments/assets/0e606fbc-16b2-4e23-bf6d-19ed38786215" />
<img width="910" height="405" alt="image" src="https://github.com/user-attachments/assets/7e885ba8-2590-4d61-8049-156bb3d00db5" />
<img width="905" height="441" alt="image" src="https://github.com/user-attachments/assets/d37c284d-9164-4f5f-9df8-4fb28bd1972d" />

# Minikube Setup and Validation
---
## Initialize and configure Minikube
Minikube started and initialized and in running stage.
<img width="888" height="307" alt="image" src="https://github.com/user-attachments/assets/d98df351-3035-4370-8101-44f85f934df0" />

## Deployed all components as per below
``` bash
Deploying all Deployments using kubectl
kubectl apply -f gateway-deployments.yaml  
kubectl apply -f namespace.yaml  
kubectl apply -f order-deployment.yaml  
kubectl apply -f product-deployment.yaml  
kubectl apply -f user-deployment.yaml

Deploying all Services using kubectl
kubectl apply -f gateway-service.yaml  
kubectl apply -f order-service.yaml  
kubectl apply -f product-service.yaml  
kubectl apply -f user-service.yaml

```

### All Services and deployments are healty 
<img width="1056" height="425" alt="image" src="https://github.com/user-attachments/assets/9a5f08bd-b20c-46b5-9bd1-450e17240eee" />









