🚀 Microservices-Based Voting Application on Azure Container Apps

A cloud-native, real-time voting system built using microservices architecture, containerization, and Azure infrastructure.

This project demonstrates the end-to-end design, containerization, and deployment of a distributed voting system using modern DevOps and cloud-native principles. The application is architected for scalability, fault isolation, asynchronous processing, and real-time result aggregation.

🏗 Architecture Overview

The system is composed of independently deployable microservices:

Vote Service – Collects user votes via HTTP

Worker Service – Processes votes asynchronously

Result Service – Displays real-time aggregated results

Redis – Acts as both message queue and in-memory datastore

PostgreSQL (Local version) – Persistent storage layer

Azure Container Apps (Cloud deployment) – Managed container runtime

🔁 Data Flow

User submits vote via Vote Service

Vote is pushed into Redis queue

Worker Service consumes vote asynchronously

Vote counts are updated atomically

Result Service retrieves and displays live results

This event-driven architecture ensures:

Loose coupling

Non-blocking UI

Horizontal scalability

Fault isolation

🗂 Project Structure
azure-voting-microservices/
│
├── docker-compose.yml
├── README.md
│
└── src/
    ├── vote/
    │   ├── app.py
    │   ├── Dockerfile
    │   └── requirements.txt
    │
    ├── result/
    │   ├── app.py
    │   ├── Dockerfile
    │   └── requirements.txt
    │
    └── worker/
        ├── app.py / worker.csproj
        ├── Dockerfile
        └── dependencies
⚙️ Technologies Used

Docker & Docker Compose

Azure Container Apps

Azure Container Registry

Azure Log Analytics

Python (Flask-based services)

.NET Worker Service

Redis (Message Queue + Data Store)

PostgreSQL

Microservices Architecture

Distributed Systems

Event-Driven Design

DevOps & Containerization

▶️ Run Locally (Docker Compose)
Prerequisites

Docker

Docker Compose

Start Application
docker-compose up --build
Access Services

Voting App → http://localhost:5000

Results Dashboard → http://localhost:5001

☁️ Azure Deployment Architecture

The cloud deployment uses:

Azure Container Apps Environment

Azure Container Registry (ACR) for secure image storage

Internal Service Networking (FQDN-based communication)

Ingress Configuration for public services

Log Analytics Workspace for centralized monitoring

Security Design

Worker and Redis run on internal network only

Vote and Result services exposed via controlled ingress

Environment variables used for secure service discovery

📊 Engineering Concepts Demonstrated

Microservices decomposition

Asynchronous workload processing

Message queue-based communication

Atomic counter updates

Container-based deployments

Cloud-native service discovery

Horizontal autoscaling

Observability and log monitoring

Infrastructure troubleshooting in distributed environments

📈 Performance & Scalability

Redis ensures sub-millisecond operations

Azure Container Apps supports automatic scaling based on traffic

Worker service processes votes independently from frontend

System can handle high-throughput workloads without UI degradation

🧠 Challenges & Lessons Learned

Resolving internal FQDN networking issues

Handling Redis hostname misconfigurations

Managing Azure Container Apps revisions

Ensuring architecture compatibility (amd64 builds)

Debugging distributed services using Log Analytics

This project strengthened practical knowledge of cloud infrastructure, distributed systems debugging, and real-world DevOps workflows.

🚀 Future Enhancements

Kubernetes migration

CI/CD pipeline integration (GitHub Actions)

Advanced monitoring dashboards

Load balancing strategies

Machine learning-based vote pattern analysis

Integration with advanced message brokers (e.g., Kafka)

👨‍💻 Authors

Pradeepsinh Chavda

Isit Thakkar

⭐ Why This Project Stands Out

This project elevates a simple voting application into a scalable, production-ready, cloud-native distributed system. It mirrors real-world backend architectures used in:

Live polling platforms

Audience engagement dashboards

Event tracking systems

Real-time analytics pipelines

It showcases hands-on experience in:

✔ Cloud-native engineering
✔ Container orchestration
✔ Distributed systems design
✔ DevOps practices
✔ Azure infrastructure
