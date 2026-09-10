# 10 — 🔑 Unit 01 Keywords Cheat Sheet

> [!TIP]
> ## ⚡ Interview Revision
> Is page ko vocabulary flash-sheet ki tarah use karo.

| Keyword | One-Line Memory |
|---|---|
| **Internet** | Network of networks |
| **Web** | HTTP/HTTPS-based service ecosystem on the internet |
| **Client** | Request initiate karta hai |
| **Server** | Requests/services serve karta hai |
| **IP Address** | Network addressing/destination |
| **Port** | Machine par network service endpoint |
| **localhost** | This machine / loopback |
| **HTTP** | Web request/response protocol |
| **HTTPS** | HTTP protected by TLS |
| **GET** | Retrieve/read resource |
| **POST** | Create/submit |
| **PUT** | Replace/update |
| **PATCH** | Partial update |
| **DELETE** | Delete |
| **200** | OK |
| **201** | Created |
| **301/302** | Redirect |
| **400** | Bad request |
| **401** | Not authenticated / auth required |
| **403** | Forbidden |
| **404** | Not found |
| **500** | Server-side internal error |
| **502** | Gateway/proxy upstream failure |
| **503** | Service unavailable |
| **TCP** | Reliable ordered byte-stream transport |
| **UDP** | Datagram transport, fewer built-in guarantees |
| **QUIC** | Modern transport over UDP used by HTTP/3 |
| **DNS** | Domain/hostname resolution |
| **Domain** | Human-friendly name |
| **Hostname** | Network-facing name such as `api.example.com` |
| **A Record** | Hostname → IPv4 |
| **AAAA Record** | Hostname → IPv6 |
| **CNAME** | Hostname → another hostname |
| **URL** | Protocol + host + path + query etc. |
| **Public IP** | Internet-routable address |
| **Private IP** | Internal/private network address |
| **Router** | Forwards packets between networks |
| **NAT** | Address/connection translation/mapping |
| **Firewall** | Allow/block traffic using rules |
| **Frontend** | User-facing client application/assets |
| **Backend** | Server-side application logic/API |
| **Database** | Persistent data system |
| **Static Asset** | HTML/CSS/JS/image etc. served as file |
| **Nginx** | Web server, proxy, TLS termination, load balancer |
| **Web Server** | Serves HTTP content/requests |
| **Reverse Proxy** | Server-side intermediary forwarding requests |
| **Forward Proxy** | Client-side intermediary |
| **Upstream** | Backend service a proxy forwards to |
| **Load Balancer** | Distributes traffic across instances |
| **TLS** | Secure transport protocol |
| **Certificate** | Helps authenticate server identity |
| **CA** | Certificate Authority |
| **TLS Handshake** | Establishes authenticated secure session |
| **TLS Termination** | Front layer handles incoming TLS |
| **CDN** | Content closer to geographically distributed users |
| **Cache** | Fast temporary storage for repeated access |
| **Redis** | Common in-memory cache/state system |
| **Queue** | Buffer/decouple asynchronous work |
| **Horizontal Scaling** | Add more instances instead of only bigger machine |
| **Reverse Proxy Routing** | Route requests by host/path to backends |
| **API** | Programmatic application interface |
| **SSR** | Server-side rendering |
| **CSR** | Client-side rendering |
| **SSG** | Static site generation |

---

## 🔴 Common Confusions

| Don't Confuse | Correct Difference |
|---|---|
| Internet vs Web | Internet = network; Web = HTTP/HTTPS service |
| Domain vs Server | Name vs workload infrastructure |
| DNS vs Domain | Resolution system vs name |
| IP vs Port | Machine/network destination vs service endpoint |
| HTTP vs TCP | App protocol vs transport |
| HTTPS vs HTTP | HTTP protected by TLS vs unprotected HTTP |
| Forward vs Reverse Proxy | Client-side vs server-side intermediary |
| Nginx vs Node | Infrastructure/web layer vs application runtime |
| React SPA vs Next.js | Mostly client runtime vs mixed server/client possibilities |
| TLS vs Full Security | Secure transport vs complete application security |

---

## ⚡ Absolute Pareto 15

If you remember only 15 terms:

```text
DNS
IP
Port
HTTP
HTTPS
TCP
Public IP
Private IP
Firewall
Nginx
Reverse Proxy
TLS
Certificate
Backend
Database
```
