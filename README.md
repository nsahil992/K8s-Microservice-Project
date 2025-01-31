# **Go Microservices on Kubernetes 🚢📦📦📦**  

This project demonstrates deploying **Go-based microservices** (Auth, Payment, and Streaming services) on **Kubernetes** using **Pods, ReplicaSets, Deployments, and Services**.  

## **📌 Features**  
✅ Auth Service – Handles user authentication  
✅ Payment Service – Simulates payment processing  
✅ Streaming Service – Provides streaming functionality  
✅ Dockerized services with individual `Dockerfile`  
✅ Kubernetes YAML configurations for deployment  

---

## **📁 Project Structure**  

```
├── auth-service/
│   ├── main.go
│   ├── Dockerfile
│   ├── auth-deployment.yaml
│   ├── auth-service.yaml
│   ├── auth-replicaset.yaml
│
├── payment-service/
│   ├── main.go
│   ├── Dockerfile
│   ├── payment-deployment.yaml
│   ├── payment-service.yaml
│   ├── payment-replicaset.yaml
│
├── streaming-service/
│   ├── main.go
│   ├── Dockerfile
│   ├── streaming-deployment.yaml
│   ├── streaming-service.yaml
│   ├── streaming-replicaset.yaml
│
├── README.md
└── .gitignore
```

---

## **📦 Setting Up the Project**  

### **1️⃣ Build & Push Docker Images**  
Replace `your-dockerhub-username` with your **Docker Hub** username.  

```sh
docker build -t your-dockerhub-username/auth-service:latest ./auth-service
docker build -t your-dockerhub-username/payment-service:latest ./payment-service
docker build -t your-dockerhub-username/streaming-service:latest ./streaming-service

docker push your-dockerhub-username/auth-service:latest
docker push your-dockerhub-username/payment-service:latest
docker push your-dockerhub-username/streaming-service:latest
```

---

### **2️⃣ Deploy to Kubernetes**  

#### **Create a Namespace (Optional)**
```sh
kubectl apply -f k8s/namespace.yaml
```

#### **Deploy Microservices**  
```sh
kubectl apply -f auth-service/auth-deployment.yaml
kubectl apply -f payment-service/payment-deployment.yaml
kubectl apply -f streaming-service/streaming-deployment.yaml
```

#### **Apply Services**  
```sh
kubectl apply -f auth-service/auth-service.yaml
kubectl apply -f payment-service/payment-service.yaml
kubectl apply -f streaming-service/streaming-service.yaml
```

#### **Verify Deployment**  
```sh
kubectl get pods
kubectl get services
```

---

## **🌍 Accessing the Services**  

- **Inside the cluster** → Use `ClusterIP` (default).  
- **Outside the cluster** → Use `NodePort` or an `Ingress Controller`.  

---

## **📌 Useful Commands**  

### **Check Logs**
```sh
kubectl logs -f <pod-name>
```

### **Delete All Resources**
```sh
kubectl delete -f auth-service/
kubectl delete -f payment-service/
kubectl delete -f streaming-service/
kubectl delete -f k8s/
```

---


## **📢 Connect with Me**  
📌 **Blog**: [https://sahilnaik.hashnode.dev/kubernetes-the-start](#)  
📌 **LinkedIn**: [https://www.linkedin.com/in/nsahil992](#)  

---

🚀 Happy Deploying! **#Kubernetes #GoLang #Microservices #DevOps** 🎯
