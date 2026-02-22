<h1> Containerize a microservices-based application using Node.js, Docker, and Docker Compose.</h1>
We are provided with source code for three Node.js microservices:
User Service (Port 3000)
Product Service (Port 3001)
Gateway Service (Port 3003)
My task is to containerize these services and orchestrate them using Docker Compose.

File structure 
```
├── user-service/
│   └── Dockerfile
├── product-service/
│   └── Dockerfile
├── order-service/
│   └── Dockerfile
├── gateway-service/
│   └── Dockerfile
├── docker-compose.yml
└── README.md
```

</h2> Stage 1: Dockerfile Creation</h2>
<h3>Docker filers are creatred and pushed to Github repo.</h3>
<img width="398" height="642" alt="image" src="https://github.com/user-attachments/assets/7bd4453f-584b-45a2-a94f-6a17d7cdae01" />
<img width="702" height="435" alt="image" src="https://github.com/user-attachments/assets/e9bc6a65-8dad-4eb0-8858-a5830e630f66" />
<img width="587" height="445" alt="image" src="https://github.com/user-attachments/assets/47df2790-e52d-4ded-9855-865a53a64c70" />
<img width="657" height="450" alt="image" src="https://github.com/user-attachments/assets/58e0b272-07b0-45a1-9f30-ea5e7553eedd" />

<h2>Stage 2:Docker Compose Configuration</h2>
<h3>Docker filers are creatred and pushed to Github repo.</h3>
<img width="778" height="907" alt="image" src="https://github.com/user-attachments/assets/38e952ea-ce7e-4a55-90ed-902b7975794b" />

<h2>Stage 3: Local Testing & Validation</h2> 
</h3>All four containers are running on VM for all four microservices. Tested on webpage for all services</h3>
_Containetrs status_
<img width="1332" height="366" alt="image" src="https://github.com/user-attachments/assets/e5b3d2ef-efa2-45b1-b98a-9f83af444ae0" />

<h3>_Microservices Verification on webpage_</h3>
<h4>User Service on Port 3000 :</h4>
<img width="798" height="428" alt="image" src="https://github.com/user-attachments/assets/21ba2b3b-7143-4b4a-91ad-c4e4bb1efccb" />

<h4>Product Service on Port 3001 :</h4>
<img width="697" height="470" alt="image" src="https://github.com/user-attachments/assets/7d6b835b-e661-474c-9f0b-58e5ea65c5f9" />

<h4>Order Service on Port 3002 :</h4>
<img width="865" height="447" alt="image" src="https://github.com/user-attachments/assets/b704ec00-c84f-4833-be41-c1039ca3c312" />

<h4>gateway Service on Port 3003 :</h4>
<img width="897" height="336" alt="image" src="https://github.com/user-attachments/assets/9871d274-9950-4670-97e5-277b7b352021" />




