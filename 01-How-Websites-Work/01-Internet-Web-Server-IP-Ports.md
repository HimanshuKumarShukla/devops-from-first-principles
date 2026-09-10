# 01 — 🌍 Internet, Web, Server, IP & Ports

> [!IMPORTANT]
> ## 🔵 Core Idea
> A website is fundamentally a client sending network requests to infrastructure that runs software and returns responses.

## ⚡ Pareto — Remember This

```text
Internet = network of networks
Web      = HTTP/HTTPS-based service on top of the internet
Server   = computer/software serving requests
IP       = where the destination is
Port     = which service on that machine
```

---

## 1. Internet ≠ Web

### Internet

Internet ko simple mental model mein samjho:

> **Networks ka giant network.**

```text
Laptop ─┐
Phone ──┤
Server ─┼──── INTERNET
Router ─┤
Cloud ──┘
```

### Web

Web internet ke upar chalne wali ek service hai.

```text
Internet
│
├── Web → HTTP / HTTPS
├── Email
├── SSH
├── DNS
└── many other protocols
```

> [!WARNING]
> ## 🔴 Don't Confuse
> **Internet ≠ Web**  
> Internet underlying network infrastructure hai.  
> Web us infrastructure par chalne wali HTTP/HTTPS-based service hai.

---

## 2. Client & Server

### Client

Client request initiate karta hai.

Examples:

- Browser
- Mobile app
- CLI tool like `curl`
- Another backend service

### Server

Server fundamentally koi magical cloud object nahi hai.

```text
┌────────────────────────────┐
│          COMPUTER          │
│                            │
│ CPU                        │
│ RAM                        │
│ SSD                        │
│ Network Interface          │
│ Operating System           │
│                            │
│ Running application        │
└────────────────────────────┘
```

> [!TIP]
> Tumhara laptop bhi server ban sakta hai if it runs software that listens for network requests.

Example:

```js
app.listen(3000);
```

This means the Node application is listening on **port 3000**.

---

## 3. IP Address

IP address ka basic job:

> Network ko destination identify/address karne mein help karna.

Mental analogy:

```text
House address → IP address
Room number   → Port
```

Example:

```text
192.168.1.10:3000
│             │
│             └── Service / port
└──────────────── Machine/network address
```

---

## 4. Ports

Ek machine par multiple services run kar sakti hain:

```text
               SERVER
            IP: 10.0.0.5

     ┌─────────────────────┐
:22  │ SSH                 │
:80  │ HTTP                │
:443 │ HTTPS               │
:3000│ Node App            │
:6379│ Redis               │
     └─────────────────────┘
```

> [!IMPORTANT]
> **IP tells you the machine/network destination.**  
> **Port helps identify the network service endpoint on that machine.**

### Common Ports — Pareto Set

| Port | Typical Service |
|---:|---|
| `22` | SSH |
| `80` | HTTP |
| `443` | HTTPS |
| `3000` | Common local Node dev/app port |
| `6379` | Redis default |
| `27017` | MongoDB default |

> [!CAUTION]
> Port numbers do not magically define a service. They are conventions/defaults. Applications can often be configured to listen elsewhere.

---

## 5. `localhost`

When you use:

```text
http://localhost:3000
```

Break it down:

```text
http:// localhost : 3000
  │        │          │
  │        │          └── Port
  │        └───────────── This computer
  └────────────────────── Protocol
```

Meaning:

> Apni machine par port `3000` par listening service se HTTP ke through communicate karo.

### Loopback

`localhost` generally resolves to loopback addresses such as:

```text
127.0.0.1   → IPv4 loopback
::1         → IPv6 loopback
```

Pareto level par bas yaad rakho:

> `localhost` = **this machine itself**

---

## 6. DevOps Connection

Developer:

```text
Node application ready ✅
```

Infrastructure questions:

```text
Where does it run?
Which IP?
Which port?
Can internet reach it?
Should internet reach it?
Who handles HTTPS?
What happens if it crashes?
```

Yehi questions aage Nginx, firewall, cloud, Docker, load balancer aur Kubernetes tak le jaate hain.

---

## 🔑 Keywords

`Internet` — network of networks  
`Web` — HTTP/HTTPS-based web ecosystem  
`Client` — initiates a request  
`Server` — serves requests/services  
`IP Address` — network addressing/destination  
`Port` — service endpoint identifier  
`localhost` — local machine / loopback

---

## 🧠 Active Recall — Short Answers

**Q1. Internet aur Web same hain?**  
No. Internet underlying network hai; Web uske upar chalne wali service hai.

**Q2. Server fundamentally kya hai?**  
A computer/software system that listens for and serves requests.

**Q3. IP address ka role?**  
Network destination ko address/locate karna.

**Q4. Port kyun chahiye?**  
Same machine par correct network service endpoint identify karne ke liye.

**Q5. `localhost:3000` ka matlab?**  
Apni machine par port 3000 wali service.

**Q6. HTTP ka common port?**  
80.

**Q7. HTTPS ka common port?**  
443.
