# AI-Powered Microservice Architecture

 # 🛒 AI-Powered E-Shop Microservices Architecture with .NET Aspire & GenAI

This project demonstrates the development of a **cloud-native, AI-powered E-Commerce platform** using the **.NET Aspire framework**, integrating **Generative AI** capabilities with **Microsoft.Extensions.AI**, **Semantic Kernel**, and **Ollama's Llama/Phi models**.

The system is composed of modular microservices such as **Catalog** and **Basket**, powered by PostgreSQL, Redis, and RabbitMQ, and secured with **Keycloak**. It also features intelligent product discovery through **semantic search** and **Q&A chatbots**, enabled by **RAG (Retrieval-Augmented Generation)** flows.

---

## 🚀 What You'll Learn

- Build **cloud-native distributed architectures** with .NET Aspire
- Implement microservices using **PostgreSQL**, **Redis**, **RabbitMQ**
- Architect **event-driven communication** using **MassTransit** and RabbitMQ
- Secure endpoints using **Keycloak** with **JWT Bearer Authentication**
- Containerize and deploy services to **Azure Container Apps**
- Power intelligent features with **GenAI**, **Semantic Kernel**, and **VectorDB**
- Integrate **Q&A Chatbot** and **Semantic Product Search** using **Ollama**

---

## 🧩 Architecture Overview

- **Catalog Microservice**
  - Stores product data in PostgreSQL
  - Publishes events like `ProductPriceChanged` to RabbitMQ

- **Basket Microservice**
  - Uses Redis to manage session-based shopping cart data
  - Subscribes to Catalog events via RabbitMQ to sync basket prices
  - Secured using Keycloak + JWT

- **Client Application**
  - Built using **Blazor WebAssembly**
  - Communicates with backend services via REST and messaging

- **Messaging**
  - Pub/Sub with RabbitMQ
  - Resilient error handling, retries, and routing logic via MassTransit

- **Generative AI**
  - Embedded Q&A chatbot powered by **Semantic Kernel + Ollama**
  - RAG-based product semantic search using **Vector Store** and **All-MiniLM embeddings**

---

## 🧠 AI Capabilities

### 🔍 Semantic Product Search (RAG Flow)
- Generate embeddings for product descriptions using **Ollama's All-MiniLM**
- Store and query a **VectorDB** to enable real-time semantic product matching

### 💬 Q&A Chatbot
- Use **Semantic Kernel** to create prompt workflows
- Integrate **Ollama (Llama/Phi)** to answer contextual queries from users

---

## 🔒 Security

- Integrated **Keycloak** for identity management
- JWT Bearer tokens used to protect endpoints in the Basket service

---

## 🐳 Deployment

- All services are containerized using **Docker**
- Deploy to **Azure Container Apps** using:
  ```bash
  azd up     # Deploy
  azd down   # Teardown

