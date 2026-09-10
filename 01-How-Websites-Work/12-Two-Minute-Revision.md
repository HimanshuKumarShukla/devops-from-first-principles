# 12 — ⚡ Unit 01 — 2-Minute Revision

> [!TIP]
> Is page ko interview, quiz ya next chunk se pehle read karo.

## 🌐 Master Flow

```text
Domain
  ↓
DNS
  ↓
IP / destination
  ↓
Internet routing
  ↓
TCP / QUIC
  ↓
TLS
  ↓
HTTP
  ↓
Firewall
  ↓
Nginx / Reverse Proxy
  ↓
Backend
  ↓
Database
  ↓
Response
  ↓
Browser UI
```

## 🔑 Fast Definitions

**Internet** → network of networks  
**Web** → HTTP/HTTPS-based ecosystem  
**IP** → network destination/address  
**Port** → network service endpoint  
**DNS** → domain/hostname resolution  
**HTTP** → request/response protocol  
**HTTPS** → HTTP protected by TLS  
**TCP** → reliable ordered byte stream  
**UDP** → datagrams, fewer built-in guarantees  
**Public IP** → internet-routable  
**Private IP** → internal/private network  
**Router** → packets between networks  
**NAT** → address/connection translation  
**Firewall** → allow/block traffic  
**Nginx** → web server/proxy/load balancer/TLS endpoint  
**Reverse Proxy** → front door forwarding to backend  
**TLS** → encrypted/authenticated transport  
**Certificate** → helps verify server identity  
**A** → hostname → IPv4  
**AAAA** → hostname → IPv6  
**CNAME** → hostname → hostname  
**Frontend** → browser-facing UI/assets  
**Backend** → server-side logic/API  
**Database** → persistent data store  
**Load Balancer** → distribute requests  
**CDN** → content closer to users  
**Cache** → fast repeated access  
**Queue** → asynchronous work buffer

## 🔴 Five Confusions to Avoid

1. **Internet ≠ Web**
2. **Domain ≠ Server**
3. **IP ≠ Port**
4. **HTTP ≠ TCP**
5. **Nginx ≠ Node**

## ⚡ Nginx Pareto

```text
Static serving
Reverse proxy
TLS termination
Load balancing
```

## 🔒 TLS Pareto

```text
Confidentiality
Integrity
Authentication
```

## 🧠 One-Line Architecture

> **DNS finds the destination, networking reaches it, TLS secures it, Nginx routes it, backend processes it, database supplies data, browser renders the result.**
