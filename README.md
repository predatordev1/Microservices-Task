<h1>Assignment | Skill Test 2 _ Container Orchestration</h1>
<h2>Objective: <h3>Deploy a microservices application on Kubernetes using Minikube, ensuring proper service communication and configuration.</h3></h2>

```
File structure 

.
├── K8s manifests
│   ├── Deployments
│   │   ├── gateway-deployments.yaml
│   │   ├── namespace.yaml
│   │   ├── order-deployment.yaml
│   │   ├── product-deployment.yaml
│   │   └── user-deployment.yaml
│   └── Services
│       ├── gateway-service.yaml
│       ├── order-service.yaml
│       ├── product-service.yaml
│       └── user-service.yaml
├── LICENSE
├── Microservices
│   ├── docker-compose.yml
│   ├── gateway-service
│   │   ├── app.js
│   │   ├── Dockerfile
│   │   └── package.json
│   ├── order-service
│   │   ├── app.js
│   │   ├── Dockerfile
│   │   └── package.json
│   ├── product-service
│   │   ├── app.js
│   │   ├── Dockerfile
│   │   └── package.json
│   ├── README.md
│   └── user-service
│       ├── app.js
│       ├── Dockerfile
│       └── package.json
├── README.md

```
---

## Architecture

| Service | Port |  |
| --- | --- | --- |
| `User Service` | 3000 |
| `Product Service` | 3001|
| `Order Service` | 3002 | 
| `Gateway Service` | 3003 | 

---

# Dockerfile Creation
<h3>Docker filers are creatred and pushed to Github repo.</h3>
<img width="398" height="642" alt="image" src="https://github.com/user-attachments/assets/7bd4453f-584b-45a2-a94f-6a17d7cdae01" />
<img width="702" height="435" alt="image" src="https://github.com/user-attachments/assets/e9bc6a65-8dad-4eb0-8858-a5830e630f66" />
<img width="587" height="445" alt="image" src="https://github.com/user-attachments/assets/47df2790-e52d-4ded-9855-865a53a64c70" />
<img width="657" height="450" alt="image" src="https://github.com/user-attachments/assets/58e0b272-07b0-45a1-9f30-ea5e7553eedd" />

# Docker Compose Configuration
<h3>Docker filers are creatred and pushed to Github repo.</h3>
<img width="778" height="907" alt="image" src="https://github.com/user-attachments/assets/38e952ea-ce7e-4a55-90ed-902b7975794b" />

# Docker Images creation,tagging and pushing to Dockerhub.
``` bash
__Docker Images creation__
docker compose build
docker images

__Docker Images creation__
docker tag  microservices-gateway-service:latest dev8182/dockerfiles:microservice-gateway-V0.1
docker tag microservices-order-service:latest dev8182/dockerfiles:microservice-order-v0.1
docker tag microservices-product-service:latest dev8182/dockerfiles:microservice-product-v0.1
docker tag microservices-user-service:latest dev8182/dockerfiles:microservice-user-v0.1

__Docker Images Pushing into Docker Hub__
docker push dev8182/dockerfiles:microservice-gateway-V0.1
docker push dev8182/dockerfiles:microservice-order-V0.1
docker push dev8182/dockerfiles:microservice-order-v0.1
docker push dev8182/dockerfiles:microservice-product-v0.1
docker push dev8182/dockerfiles:microservice-user-v0.1

```

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

---

# Troubleshooting
### Issue 1: Pods was crashing after containers creation due to HTTP probe failed: 404 error.
<img width="1467" height="572" alt="image" src="https://github.com/user-attachments/assets/f3a50682-bd39-4c92-a1c5-7bfbcc6cb143" />

  Solu: Made changes in Deployment file as per below. After changes all PODS become healty and stable.
  ``` bash
  FROM 
  httpGet:
    path: /api/health

  with
    tcpSocket:

```
<img width="1056" height="425" alt="image" src="https://github.com/user-attachments/assets/9a5f08bd-b20c-46b5-9bd1-450e17240eee" />

### Issue 2: Aftre all pods abd services were healty but still was not able to access to Services.
<img width="1022" height="813" alt="image" src="https://github.com/user-attachments/assets/0de0fd40-470a-4d00-a7e6-644ffa8dbc42" />

Solu: Made changes in Service file as per below. After changes all Services are accessable.
  ``` bash
  FROM 
  type: ClusterIP

  with
  type: NodePort

  
   ```
 also added Default node port for all services based on main service ports as
| Service | Node Port |  |
| --- | --- | --- |
| `User Service` | 30000 |
| `Product Service` | 30001|
| `Order Service` | 30002 | 
| `Gateway Service` | 30003 | 

<img width="832" height="381" alt="image" src="https://github.com/user-attachments/assets/4663eb91-ff28-4ff0-89c0-29be9cce95ee" />
<img width="907" height="407" alt="image" src="https://github.com/user-attachments/assets/c3cfd306-ee12-43ca-8593-61995898aab5" />
<img width="871" height="247" alt="image" src="https://github.com/user-attachments/assets/7e09ca38-43b8-482f-87d5-bf38593df3a9" />






