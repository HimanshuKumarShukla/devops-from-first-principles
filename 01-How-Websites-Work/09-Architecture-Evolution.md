# 09 — 🏗️ Architecture Evolution

> [!IMPORTANT]
> ## 🔵 Core Idea
> Large systems ko giant diagram ki tarah memorize mat karo.  
> **Har new box ek problem solve karta hai.**

---

## Version 0 — One Machine

```text
User
 ↓
Server
```

Good for:

- Small demo
- Learning
- Tiny workloads

Problem:

- No separation
- Single point of failure
- Hard to scale

---

## Version 1 — Full-Stack App

```text
User
 ↓
Node
 ↓
Database
```

Now application logic and persistent data exist.

Problem:

- Public backend exposure
- TLS/static routing concerns
- Single backend instance

---

## Version 2 — Nginx Front Door

```mermaid
flowchart TD
    U[User] --> N[Nginx]
    N --> F[Frontend]
    N --> B[Node]
    B --> DB[(Database)]
```

Nginx adds:

- Static serving
- Reverse proxy
- TLS termination
- Central public entry

---

## Version 3 — Multiple Backend Instances

```mermaid
flowchart TD
    U[Users] --> LB[Load Balancer]
    LB --> B1[API-1]
    LB --> B2[API-2]
    LB --> B3[API-3]
    B1 --> DB[(Database)]
    B2 --> DB
    B3 --> DB
```

Problem solved:

> One backend is not enough.

Concept introduced:

> **Horizontal scaling**

---

## Version 4 — Cache

```mermaid
flowchart TD
    U[Users] --> LB[Load Balancer]
    LB --> API[Backend Pool]
    API --> R[(Redis / Cache)]
    API --> DB[(Database)]
```

Why cache?

- Repeated expensive reads
- Reduce DB pressure
- Faster responses for hot data

---

## Version 5 — CDN

```mermaid
flowchart TD
    U[Global Users] --> CDN[CDN / Edge]
    CDN --> LB[Load Balancer]
    LB --> API[Backend Pool]
    API --> DB[(Database)]
```

Why CDN?

- Users geographically distributed
- Static/media content closer to users
- Reduce origin load

---

## Version 6 — Service-Oriented / Microservice Shape

```mermaid
flowchart TD
    U[Users] --> G[API Gateway / Entry]
    G --> A[Auth Service]
    G --> P[Product Service]
    G --> C[Cart Service]
    G --> O[Order Service]
    A --> ADB[(Auth Data)]
    P --> PDB[(Product Data)]
    C --> CDB[(Cart Data)]
    O --> ODB[(Order Data)]
```

Why split?

Possible reasons include:

- Independent scaling
- Team ownership
- Different data models
- Deployment isolation
- Domain boundaries

> [!WARNING]
> Microservices are not automatically better. They add operational complexity.

---

## Version 7 — Event-Driven Work

```mermaid
flowchart LR
    O[Order Service] --> Q[Queue / Event Bus]
    Q --> P[Payment Worker]
    Q --> E[Email Worker]
    Q --> A[Analytics Worker]
```

Why queue/events?

- Work need not happen synchronously
- Decouple services
- Buffer bursts
- Retry background work

---

## Amazon-ish Mental Model

```mermaid
flowchart TD
    U[Users] --> DNS[DNS]
    DNS --> CDN[CDN]
    CDN --> LB[Load Balancer]
    LB --> G[API Gateway / Routing]
    G --> AUTH[Auth]
    G --> PROD[Products]
    G --> CART[Cart]
    G --> ORD[Orders]
    PROD --> CACHE[(Cache)]
    PROD --> SEARCH[(Search Index)]
    AUTH --> ADB[(Auth DB)]
    CART --> CDB[(Cart DB)]
    ORD --> ODB[(Order DB)]
```

Not actual Amazon internals—this is a **learning model**.

---

## Netflix-ish Difference

Streaming systems care heavily about:

```text
Video storage
Encoding
CDN / edge delivery
Playback
Recommendations
Profiles
Subscriptions
Analytics
```

A simplified split:

```mermaid
flowchart LR
    U[User] --> API[Netflix-like APIs]
    U --> CDN[CDN / Video Edge]
    API --> REC[Recommendations]
    API --> PROF[Profile]
    API --> AUTH[Auth]
    CDN --> VID[Video Stream]
```

Key insight:

> API data and massive media delivery may take very different paths.

---

## 🧠 Architecture Reasoning Table

| New Box | Problem It Solves |
|---|---|
| DNS | Human-friendly discovery |
| Nginx / Reverse Proxy | Front door, routing, TLS, static serving |
| Load Balancer | Multiple backend instances |
| Cache / Redis | Repeated expensive access |
| CDN | Geographic content delivery |
| Queue | Async/background work |
| Multiple services | Independent domains/scaling/ownership |
| Monitoring | Understand system health |
| Kubernetes | Manage containerized workloads at scale |
| Terraform | Reproducible infrastructure as code |

---

## 🧠 Active Recall — Short Answers

**Q1. Large architecture kaise learn karni chahiye?**  
Har new component ko us problem se connect karke jo woh solve karta hai.

**Q2. Load balancer kyun?**  
Traffic multiple backend instances mein distribute karne ke liye.

**Q3. Cache kyun?**  
Repeated expensive access ko faster aur cheaper banane ke liye.

**Q4. CDN kyun?**  
Content ko geographically users ke closer serve karne ke liye.

**Q5. Queue kyun?**  
Async/background work ko decouple and buffer karne ke liye.

**Q6. Microservices always better?**  
No. They add significant operational complexity.
