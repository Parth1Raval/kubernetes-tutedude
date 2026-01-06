🚀 Flask Frontend & Express Backend Deployment on Kubernetes (Minikube)

This project demonstrates how I deployed my previous assignment applications a Flask frontend and an Express backend on a local Kubernetes cluster using Minikube.

The goal of this assignment was to understand containerized application deployment, Kubernetes basics, and service exposure in a real, hands on way.

Everything is explained step by step in a simple and human-readable manner, along with screenshots of commands and running deployments.

🛠️ Tech Stack Used

Flask (Frontend)

Express.js (Backend)

Docker

Kubernetes

Minikube

kubectl

📌 Assignment Objective

✔️ Deploy Flask frontend and Express backend
✔️ Run both applications inside Kubernetes
✔️ Use Minikube for local cluster
✔️ Expose services and verify accessibility
✔️ Share GitHub repo + screenshots of commands and deployments

⚙️ Step 1: Start Minikube Cluster

I started a local Kubernetes cluster using Minikube.

minikube start


To verify that the cluster is running:

kubectl get nodes
minikube status

📸 Screenshot – Minikube Running

This confirms that:

Minikube VM is running

Kubernetes API server is active

kubectl is configured correctly

⚙️ Step 2: Build Docker Images

Before deploying to Kubernetes, both applications were containerized using Docker.

Flask App
docker build -t flask-app .

Express App
docker build -t express-app .


These images are used by Kubernetes deployments.

⚙️ Step 3: Create Kubernetes Deployments

I created separate deployments for Flask and Express using YAML files.

Apply Deployments
kubectl apply -f k8s/flask-deployment.yaml
kubectl apply -f k8s/express-deployment.yaml


To check deployments:

kubectl get deployments

📸 Screenshot – Kubernetes Deployments

⚙️ Step 4: Create Kubernetes Services

To expose the applications, I created NodePort services.

kubectl apply -f k8s/flask-service.yaml
kubectl apply -f k8s/express-service.yaml


Check services:

kubectl get services

📸 Screenshot – Kubernetes Services

⚙️ Step 5: Access Applications

Using Minikube service command:

minikube service flask-service
minikube service express-service

This opens the applications in the browser.

Flask Frontend → Running successfully

Express Backend → API responding correctly

🔍 Verify Pods Status
kubectl get pods

All pods are in Running state, confirming successful deployment.

📸 Kubernetes Dashboard (Optional)

I also verified everything using the Kubernetes Dashboard:

minikube dashboard

📸 Screenshot – Kubernetes Dashboard

✅ Final Outcome

✔️ Minikube cluster running locally
✔️ Flask frontend deployed on Kubernetes
✔️ Express backend deployed on Kubernetes
✔️ Services exposed and accessible
✔️ Commands and screenshots included

🧠 What I Learned

Containerizing applications with Docker

Writing Kubernetes deployment & service YAMLs

Running and managing a local Kubernetes cluster

Understanding Pods, Deployments, and Services

Debugging Kubernetes resources using kubectl
