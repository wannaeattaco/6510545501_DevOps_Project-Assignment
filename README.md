# Microservices Deployment with Consul Service Mesh on Kubernetes (GKE)

## Overview
This project demonstrates the deployment of a cloud-native microservices application on Google Kubernetes Engine (GKE) with Consul Service Mesh integration.

The objective is to show how microservices can be deployed, managed, and enhanced using a service mesh to enable service discovery, secure communication, and traffic control.

---

## Architecture

The application consists of the following microservices:

- frontend  
- productcatalogservice  
- recommendationservice  
- cartservice  
- checkoutservice  
- paymentservice  
- shippingservice  
- currencyservice  
- emailservice  
- redis-cart  

Each service runs in its own container and communicates over the network.

After integrating Consul:
- Each pod contains two containers:
  - Application container  
  - Consul sidecar proxy  

---

## Technologies Used

- Kubernetes (GKE)  
- Docker  
- Consul  
- kubectl  
- Google Cloud Platform (GCP)

## Repository Contents

This repository includes the following components:

### Microservices Application (Google Microservices Demo)

Source code adapted from the GoogleCloudPlatform microservices-demo project:

- **adservice** – Generates contextual advertisements based on keywords from user activity.  
- **cartservice** – Stores and retrieves user shopping cart data using Redis.  
- **checkoutservice** – Orchestrates the checkout process, including cart retrieval, payment processing, shipping, and order confirmation.  
- **currencyservice** – Converts monetary values between currencies using exchange rate data.  
- **emailservice** – Sends order confirmation emails (mock implementation for demonstration purposes).  
- **frontend** – Provides the web-based user interface and handles user interactions without requiring authentication.  
- **paymentservice** – Simulates payment processing and returns a mock transaction result.  
- **productcatalogservice** – Manages product listings and supports product search and detail queries.  
- **recommendationservice** – Recommends additional products based on the contents of the user’s cart.  
- **shippingservice** – Calculates shipping costs and generates mock shipment data.  
- **redis-cart** – Backend data store used by the cart service.  

---

### Kubernetes Configuration Files

These files define how the application is deployed and managed within the Kubernetes cluster:

- **kubernetes-manifests.yaml** – Contains Deployment and Service definitions for all microservices in the application.  
- **Service resources** – Expose each microservice internally within the cluster and externally where required.  
- **Deployment configurations** – Define container images, replicas, and runtime settings for each service.  

---

### Consul Service Mesh Configuration

These configurations enable service mesh functionality using Consul:

- **Consul Helm installation** – Deploys Consul into the Kubernetes cluster with Connect (service mesh) enabled.  
- **Sidecar injection annotations** – Added to each deployment to automatically inject Consul proxy containers.  
- **Namespace labeling** – Enables automatic sidecar injection at the namespace level.  


### Scripts and Commands

The following commands are used to manage and configure the system:

- Cluster setup commands – Create and connect to the GKE cluster using gcloud.
- Deployment commands – Apply Kubernetes manifests using kubectl apply.
- Patch commands – Add Consul annotations dynamically to deployments.
- Verification commands – Check pod status and ensure sidecar containers are running.
