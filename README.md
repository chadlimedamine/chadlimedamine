## Backend Engineer · Node.js / TypeScript

👋 I'm Mohamed Amine Chadli. I build backend services with **Node.js, NestJS and TypeScript** for regulated domains: healthcare, the public sector, payments and e-signatures. In these systems, correctness, audit trails and uptime matter as much as features. I also hold a **PhD in AI (computer vision)**.

### 🛠️ Tech stack

**Backend:**
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![TypeORM](https://img.shields.io/badge/TypeORM-FE0803?style=flat-square&logo=typeorm&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white)

**Infrastructure and observability:**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitLab CI/CD](https://img.shields.io/badge/GitLab_CI%2FCD-FC6D26?style=flat-square&logo=gitlab&logoColor=white)
![Jest](https://img.shields.io/badge/Jest-C21325?style=flat-square&logo=jest&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)

**AI / ML:**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)

### ⚙️ What I work on

- **APIs and services:** REST APIs, NestJS microservices, JWT authentication, role-based access control, webhook-driven integrations
- **Data:** PostgreSQL (query-plan analysis, indexing, full-text search) with TypeORM and Prisma, MongoDB, Redis caching with explicit invalidation
- **Async processing:** Redis-backed Bull queues and cron scheduling, so slow work stays off the request path
- **Observability and performance:** Prometheus metrics, Grafana dashboards, query profiling, Node.js heap diagnostics
- **Integrations:** EDI messaging (EDIFACT), national eID and e-signature flows, payment and KYC providers, scheduling APIs, LLM APIs (OpenAI, speech-to-text)
- **Delivery:** Docker, GitLab CI/CD, Jest (end-to-end and characterization tests)
- **Also:** Python, C# / .NET (EF Core, Blazor), SQL

### 🧭 How I approach backend work

- **Measure before optimizing.** Instrument first with metrics, query plans and heap profiles. Fix what the data shows, then measure again in production.
- **Keep the request path short.** Long-running work goes onto queues. A request should never wait for a background job.
- **Make failures visible.** Add global exception capture and metrics on every critical path, and keep an audit trail for anything that moves money or legal documents.
- **Refactor behind tests.** Pin the current behaviour with characterization tests before changing old code.

### 🎓 Research

PhD in Artificial Intelligence (computer vision), 2025. My research was offline recognition of handwritten Arabic text with CNN + Bi-LSTM (CRNN) models in TensorFlow/Keras, with OpenCV for image preprocessing.

- *Offline Arabic Handwritten Text Recognition for Unsegmented Words Using Convolutional Recurrent Neural Network*, Springer Nature, 2022
- *Data Augmentation for Offline Arabic Handwritten Text Recognition Using Moving Least Squares*, IIETA, 2024

### 📂 Selected repositories

| Repository | Description |
|---|---|
| [ecommerce-promo](https://github.com/chadlimedamine/ecommerce-promo) | NestJS + Prisma e-commerce API: products, carts, orders and promo-code discounts. JWT auth with Passport, DTO validation with class-validator, Winston logging. |
| [Background-Changer](https://github.com/chadlimedamine/Background-Changer) | Step-by-step notebooks that replace green-screen backgrounds in images and video automatically (OpenCV, NumPy, MoviePy). |
| [Neat-Implementation](https://github.com/chadlimedamine/Neat-Implementation) | NEAT (NeuroEvolution of Augmenting Topologies) implemented in Python. |

### 📫 Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-chadlimedamine-0A66C2?style=flat-square)](https://linkedin.com/in/chadlimedamine)
[![Email](https://img.shields.io/badge/Email-mohamed.chadli.dev%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:mohamed.chadli.dev@gmail.com)
