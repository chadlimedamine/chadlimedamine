## Backend Engineer · Node.js / TypeScript

I'm Mohamed Amine Chadli. I build backend services with **Node.js, NestJS and TypeScript** for regulated domains: healthcare, the public sector, payments and e-signatures. In these systems, correctness, audit trails and uptime matter as much as features. I also hold a **PhD in AI (computer vision)**.

### What I work on

- **APIs and services:** REST APIs, NestJS microservices, JWT authentication, role-based access control, webhook-driven integrations
- **Data:** PostgreSQL (query-plan analysis, indexing, full-text search) with TypeORM and Prisma, MongoDB, Redis caching with explicit invalidation
- **Async processing:** Redis-backed Bull queues and cron scheduling, so slow work stays off the request path
- **Observability and performance:** Prometheus metrics, Grafana dashboards, query profiling, Node.js heap diagnostics
- **Integrations:** EDI messaging (EDIFACT), national eID and e-signature flows, payment and KYC providers, scheduling APIs, LLM APIs (OpenAI, speech-to-text)
- **Delivery:** Docker, GitLab CI/CD, Jest (end-to-end and characterization tests)
- **Also:** Python, C# / .NET (EF Core, Blazor), SQL

### How I approach backend work

- **Measure before optimizing.** Instrument first with metrics, query plans and heap profiles. Fix what the data shows, then measure again in production.
- **Keep the request path short.** Long-running work goes onto queues. A request should never wait for a background job.
- **Make failures visible.** Add global exception capture and metrics on every critical path, and keep an audit trail for anything that moves money or legal documents.
- **Refactor behind tests.** Pin the current behaviour with characterization tests before changing old code.

### Research

PhD in Artificial Intelligence (computer vision), 2025. My research was offline recognition of handwritten Arabic text with CNN + Bi-LSTM (CRNN) models in TensorFlow/Keras, with OpenCV for image preprocessing.

- *Offline Arabic Handwritten Text Recognition for Unsegmented Words Using Convolutional Recurrent Neural Network*, Springer Nature, 2022
- *Data Augmentation for Offline Arabic Handwritten Text Recognition Using Moving Least Squares*, IIETA, 2024

### Selected repositories

| Repository | Description |
|---|---|
| [ecommerce-promo](https://github.com/chadlimedamine/ecommerce-promo) | NestJS + Prisma e-commerce API: products, carts, orders and promo-code discounts. JWT auth with Passport, DTO validation with class-validator, Winston logging. |
| [Background-Changer](https://github.com/chadlimedamine/Background-Changer) | Step-by-step notebooks that replace green-screen backgrounds in images and video automatically (OpenCV, NumPy, MoviePy). |
| [Neat-Implementation](https://github.com/chadlimedamine/Neat-Implementation) | NEAT (NeuroEvolution of Augmenting Topologies) implemented in Python. |

### Contact

[LinkedIn](https://linkedin.com/in/chadlimedamine) · mohamed.chadli.dev@gmail.com
