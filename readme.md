# 🐾 Cat vs Dog Voting App (Kubernetes)

A multi-stack microservices application deployed on Kubernetes.  
This project demonstrates how different technologies work together in a containerized and orchestrated environment, simulating a real-world distributed system.

---

## 🏗️ Architecture

The application consists of five loosely coupled microservices:

- Vote (Python / Flask)  
  A frontend web app where users can vote for cats 🐱 or dogs 🐶.

- Redis  
  Acts as an in-memory queue to collect incoming votes.

- Worker (.NET)  
  Consumes votes from Redis and stores them in the database.

- PostgreSQL  
  Persistent storage for vote results.

- Result (Node.js)  
  Displays real-time voting results.

---

## 🚀 Deployment Details

- Pods: 5 microservices running in Kubernetes  
- Services:
  - vote → NodePort (31000)
  - result → NodePort (31001)
  - db & redis → ClusterIP (internal services)

---

## 🛠️ How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/HarshavardhanBhosale/k8s-microservices-voting-demo.git
cd k8s-microservices-voting-demo
```

### 2. Deploy to Kubernetes
```bash
kubectl apply -f .
```

### 3. Access the Application

Voting App:
http://<node-ip>:31000

Results Dashboard:
http://<node-ip>:31001

---

## 📊 Current Cluster Status

```text
NAME                          READY   STATUS    RESTARTS   AGE
pod/db-5f4b6959b4-p4bz5       1/1     Running   0          39s
pod/redis-69f5974b5-66x5d     1/1     Running   0          39s
pod/result-5dbd594fb5-52jxw   1/1     Running   0          39s
pod/vote-8f9979fc-b9kzw       1/1     Running   0          39s
pod/worker-558876578-cmkkq    1/1     Running   0          38s
```

---

## 🎯 Key Concepts Demonstrated

- Kubernetes Pods, Deployments, and Services
- Microservices architecture with multiple languages (Python, .NET, Node.js)
- Queue-based communication using Redis
- Persistent storage using PostgreSQL
- Real-time data processing

---

## 📜 Acknowledgments

Inspired by KodeKloud Kubernetes for Beginners course.
