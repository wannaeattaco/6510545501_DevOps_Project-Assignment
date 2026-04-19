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
